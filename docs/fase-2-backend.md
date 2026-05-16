# Fase 2 - Modelo de backend

Objetivo: transformar a base local do SGCM em uma aplicação com dados centralizados, pronta para sincronizar dispositivos, manter cópias por cliente e publicar no Vercel.

## Escolha do backend

Stack recomendada para esta base:

- Frontend estático atual
- Supabase como backend
- PostgreSQL como banco
- Supabase Auth para login
- Supabase Storage para backups e arquivos futuros

Motivos:

- combina com HTML, CSS e JS puro
- reduz manutenção por cliente
- facilita deploy do frontend no Vercel
- permite copiar a base inteira como template

## Entidades do sistema

O código atual trabalha com estas entidades principais:

- usuarios
- clientes
- servicos
- agendamentos
- historico
- configuracoes

## Modelo sugerido

### usuarios

Guarda os funcionários autenticados e seus dados de acesso.

Campos principais:

- id
- auth_user_id
- nome
- email
- role
- comissao
- ativo
- created_at
- updated_at

### clientes

Cadastro de clientes do negócio.

Campos principais:

- id
- nome
- telefone
- email
- obs
- created_at
- updated_at
- deleted_at

### servicos

Serviços ou produtos vendidos no sistema.

Campos principais:

- id
- nome
- preco
- duracao
- descricao
- ativo
- created_at
- updated_at
- deleted_at

### agendamentos

Agenda operacional do dia a dia.

Campos principais:

- id
- cliente_id
- servico_id
- funcionario_id
- data
- hora
- valor
- status
- observacao
- created_at
- updated_at
- deleted_at

### historico

Registro dos atendimentos concluídos para relatórios e comissões.

Campos principais:

- id
- cliente_id
- servico_id
- funcionario_id
- agendamento_id
- valor
- data
- hora
- observacao
- registrado_em

### configuracoes

Aparência e comportamento da instalação.

Campos principais:

- nome
- slogan
- cor
- owner
- emoji
- modulos

## Estratégia para copiar e vender

Cada cliente deve ter sua própria cópia do repositório e seu próprio projeto Supabase. Isso evita mistura de dados e simplifica o suporte.

Fluxo sugerido:

1. copiar o repositório
2. criar um novo projeto Supabase
3. aplicar o schema SQL
4. criar o primeiro admin
5. configurar variáveis de ambiente
6. publicar o frontend no Vercel

Observação importante:

- a instalação é pensada como uma cópia por cliente, então as políticas do banco podem ser mais simples do que num sistema multi-tenant
- os perfis de funcionário ficam em `usuarios` e podem ser vinculados ao usuário do Supabase Auth por `auth_user_id`

## Próxima implementação

Na Fase 3, o objetivo é trocar o `LocalStorage` por uma camada de persistência com a mesma estrutura lógica do sistema atual, começando por leitura e escrita de clientes, serviços, agendamentos, histórico e configurações.
