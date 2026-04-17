# SGCM — Sistema de Gerenciamento Comercial Modular

Sistema profissional para pequenos negócios. Desenvolvido com HTML, CSS e JavaScript puro. Funciona imediatamente ao abrir o `index.html`, sem servidor ou instalação.

---

## 📋 Pré-requisitos

- Navegador moderno (Chrome, Firefox, Edge, Safari)
- Conexão com internet (apenas para carregar fontes e Chart.js)
- Sem necessidade de servidor, banco de dados ou instalação

---

## 🆕 Novidades (2026)

### Fase 1
- Paginação avançada em serviços, clientes e agendamentos
- Exportação de clientes para PDF
- Sincronização global do modo escuro

### Fase 2
- **Dashboard com gráficos (Chart.js):** Receita mensal e serviços mais vendidos
- **Múltiplos funcionários:** Login, níveis de acesso (admin/atendente), página de funcionários
- **Comissões:** Relatório de comissões por funcionário, exportação PDF
- **WhatsApp integrado:** Botão para contato direto com clientes
- **Sidebar dinâmica:** Menus diferentes para admin/atendente
- **Ajustes gerais:** Campos de funcionário em agendamentos, melhorias de segurança e usabilidade

---

## 🔐 Acesso ao Sistema

Após implementar o módulo de funcionários, use as credenciais:

| Perfil | Email | Senha |
|--------|-------|-------|
| **Administrador** | admin@sistema.com | admin123 |
| **Atendente** | atendente@sistema.com | atendente123 |

> ⚠️ **Importante:** Altere a senha do administrador após o primeiro acesso.

---

## 🚀 Como usar

1. Abra o arquivo `index.html` em qualquer navegador moderno
2. Você será redirecionado para a tela de **Login**
3. Use as credenciais padrão acima
4. Os dados de demonstração serão carregados automaticamente
5. Navegue pelas seções pelo menu lateral (varia conforme perfil)

---

## 📁 Estrutura do Projeto

/sistema
index.html → Dashboard principal
/css
main.css → Design system completo (variáveis, componentes)
/js
db.js → Banco de dados (LocalStorage)
ui.js → Utilitários, notificações, formatadores
mobile.js → Menu responsivo (hamburguer)
auth.js → 🔐 Autenticação e funcionários (NOVO)
charts.js → 📊 Gráficos com Chart.js (NOVO)
/pages
login.html → 🔐 Tela de acesso (NOVO)
clientes.html → Cadastro e gestão de clientes
servicos.html → Cadastro de serviços/produtos
agendamentos.html → Agenda e controle de atendimentos
historico.html → Histórico de atendimentos com relatórios
funcionarios.html → 👥 Gestão de funcionários (NOVO)
comissoes.html → 💰 Relatório de comissões (NOVO)
config.html → Configurações visuais e do negócio

---

## 🎨 Personalização

### Mudar as cores
Em `config.html`, vá em **Cor Principal** e selecione uma cor ou insira um HEX personalizado.

Ou edite diretamente no CSS (`css/main.css`):
```css
:root {
  --primary: #2563EB; /* Sua cor aqui */
}
```

Mudar o nome do negócio

Em config.html, campo Nome do Estabelecimento. Atualiza automaticamente todo o sistema.
Ativar/Desativar módulos

Em config.html, seção Módulos Ativos:

    Duração dos Serviços → útil para barbearias, esmalterias, etc.

    Histórico → para estabelecimentos que precisam de relatórios

🏪 Adaptações por tipo de negócio
Negócio	Módulo Duração	Módulo Histórico
Barbearia	✅ Ativo	✅ Ativo
Esmalteria	✅ Ativo	✅ Ativo
Lava-Rápido	❌ Opcional	✅ Ativo
Pet Shop	✅ Ativo	✅ Ativo
Restaurante	❌ Desativo	✅ Ativo
🔧 Funcionalidades
Dashboard

    Cards com totais: clientes, agendamentos, receita do mês

    Agenda do dia com horários e status

    Top serviços mais realizados (com barra de progresso)

    Progresso do dia em tempo real

    Gráficos de receita mensal e serviços mais vendidos (Chart.js)

Clientes

    Cadastro completo (nome, telefone, email, observações)

    Busca em tempo real

    Editar e excluir com confirmação

    Ver histórico individual do cliente

    Avatar colorido gerado automaticamente

    Botão WhatsApp integrado para contato rápido

Serviços

    Cards visuais por serviço

    Preço, duração e descrição

    Emoji automático por nome

    Módulo de duração configurável

    Paginação avançada

Agendamentos

    Criar agendamento com cliente + serviço + data/hora

    Seleção de funcionário responsável

    Filtros: Hoje / Amanhã / Esta Semana / Todos / Data específica

    Marcar como concluído (envia para histórico automaticamente)

    Status: Agendado / Concluído / Cancelado

Histórico

    Todos os atendimentos concluídos

    Filtros por período (de/até)

    Métricas: Receita Total, Total de Atendimentos, Ticket Médio, Receita do Mês

    Exportação de dados em JSON

Funcionários (Admin)

    Cadastro de funcionários (nome, email, senha, cargo)

    Definição de comissão (%) por funcionário

    Ativar/Inativar usuários

    Níveis de acesso: Administrador / Atendente

Comissões

    Relatório de comissões por funcionário

    Filtros por período (data inicial e final)

    Cálculo automático baseado na receita gerada

    Exportação para PDF com layout profissional

Configurações

    Nome e emoji do estabelecimento

    Cor principal (10 cores predefinidas + seletor livre)

    Módulos on/off

    Exportar backup JSON

    Restaurar dados demo

    Sidebar dinâmica por perfil de usuário

🔒 Segurança

    Autenticação: Login com email e senha (hash simples)

    Níveis de acesso: Admin (total) / Atendente (restrito)

    Sessão: Mantida enquanto o navegador não for fechado

    Dados: Armazenados localmente no dispositivo do usuário

    ⚠️ Aviso para produção: Troque a senha padrão do administrador e não compartilhe credenciais entre funcionários.

💾 Armazenamento de Dados

Os dados são salvos no LocalStorage do navegador. Para cada negócio (cada computador), os dados ficam separados.

Chaves utilizadas:

    sgcm_config — configurações do sistema

    sgcm_clientes — lista de clientes

    sgcm_servicos — lista de serviços

    sgcm_agendamentos — agendamentos

    sgcm_historico — histórico de atendimentos

    sgcm_usuarios — funcionários (NOVO)

    sgcm_session — sessão do usuário logado (NOVO)

📦 Dependências Externas

    Chart.js v4.4.0 - Biblioteca de gráficos (CDN)

    Google Fonts - Fontes Sora e JetBrains Mono

Todas são carregadas automaticamente via CDN, sem necessidade de instalação.
📱 Responsividade

O sistema é responsivo para tablets e desktops. Em telas menores (< 768px):

    Sidebar se transforma em drawer (gaveta lateral)

    Botão hamburguer para abrir/fechar o menu

    Overlay escuro ao fundo quando menu aberto

    Modais se comportam como bottom sheet

🛠 Tecnologias

    HTML5 semântico

    CSS3 com variáveis customizáveis e Dark Mode

    JavaScript ES6+ (sem frameworks)

    Google Fonts: Sora + JetBrains Mono

    Chart.js para gráficos interativos

    LocalStorage para persistência

📋 Roadmap (Próximas Versões)
Fase 3 (Preparação para Venda)

    Script de deploy automático

    Documentação comercial (guia do usuário)

    Contrato de licenciamento

Fase 4 (Opcional - Sob consulta)

    Sincronização com Google Sheets (multi-dispositivo)

    Backup automático na nuvem

    App mobile (PWA)

    Integração com WhatsApp API (envio de lembretes)

    Relatórios em Excel/CSV

    Pagamentos integrados (Mercado Pago, Stripe)

📞 Suporte

Para dúvidas, sugestões ou contratempos, entre em contato com o desenvolvedor.
