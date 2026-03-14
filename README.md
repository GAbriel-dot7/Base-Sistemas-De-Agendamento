# SGCM — Sistema de Gerenciamento Comercial Modular

Sistema profissional para pequenos negócios. Desenvolvido com HTML, CSS e JavaScript puro. Funciona imediatamente ao abrir o `index.html`, sem servidor ou instalação.

---

## 🚀 Como usar

1. Abra o arquivo `index.html` em qualquer navegador moderno
2. Os dados de demonstração serão carregados automaticamente
3. Navegue pelas seções pelo menu lateral

---

## 📁 Estrutura do Projeto

```
/sistema
  index.html              → Dashboard principal
  /css
    main.css              → Design system completo (variáveis, componentes)
  /js
    db.js                 → Banco de dados (LocalStorage) + lógica de negócio
    ui.js                 → Utilitários, notificações, formatadores
  /pages
    clientes.html         → Cadastro e gestão de clientes
    servicos.html         → Cadastro de serviços/produtos
    agendamentos.html     → Agenda e controle de atendimentos
    historico.html        → Histórico de atendimentos com relatórios
    config.html           → Configurações visuais e do negócio
  /components
    sidebar.html          → Componente de referência (sidebar)
```

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

### Mudar o nome do negócio
Em `config.html`, campo **Nome do Estabelecimento**. Atualiza automaticamente todo o sistema.

### Ativar/Desativar módulos
Em `config.html`, seção **Módulos Ativos**:
- **Duração dos Serviços** → útil para barbearias, esmalterias, etc.
- **Histórico** → para estabelecimentos que precisam de relatórios

---

## 🏪 Adaptações por tipo de negócio

| Negócio | Módulo Duração | Módulo Histórico |
|---------|---------------|-----------------|
| Barbearia | ✅ Ativo | ✅ Ativo |
| Esmalteria | ✅ Ativo | ✅ Ativo |
| Lava-Rápido | ❌ Opcional | ✅ Ativo |
| Pet Shop | ✅ Ativo | ✅ Ativo |
| Restaurante | ❌ Desativo | ✅ Ativo |

---

## 🔧 Funcionalidades

### Dashboard
- Cards com totais: clientes, agendamentos, receita do mês
- Agenda do dia com horários e status
- Top serviços mais realizados (com barra de progresso)
- Progresso do dia em tempo real

### Clientes
- Cadastro completo (nome, telefone, email, observações)
- Busca em tempo real
- Editar e excluir com confirmação
- Ver histórico individual do cliente
- Avatar colorido gerado automaticamente

### Serviços
- Cards visuais por serviço
- Preço, duração e descrição
- Emoji automático por nome
- Módulo de duração configurável

### Agendamentos
- Criar agendamento com cliente + serviço + data/hora
- Filtros: Hoje / Amanhã / Esta Semana / Todos / Data específica
- Marcar como concluído (envia para histórico automaticamente)
- Status: Agendado / Concluído / Cancelado

### Histórico
- Todos os atendimentos concluídos
- Filtros por período (de/até)
- Métricas: Receita Total, Total de Atendimentos, Ticket Médio, Receita do Mês
- Exportação de dados em JSON

### Configurações
- Nome e emoji do estabelecimento
- Cor principal (10 cores predefinidas + seletor livre)
- Módulos on/off
- Exportar backup JSON
- Restaurar dados demo

---

## 💾 Armazenamento de Dados

Os dados são salvos no **LocalStorage** do navegador. Para cada negócio (cada computador), os dados ficam separados.

Chaves utilizadas:
- `sgcm_config` — configurações do sistema
- `sgcm_clientes` — lista de clientes
- `sgcm_servicos` — lista de serviços
- `sgcm_agendamentos` — agendamentos
- `sgcm_historico` — histórico de atendimentos

---

## 📱 Responsividade

O sistema é responsivo para tablets e desktops. Em telas menores (< 768px), a sidebar é ocultada. Para uso em smartphones, recomenda-se ampliar o suporte mobile adicionando um botão hamburguer.

---

## 🛠 Tecnologias

- HTML5 semântico
- CSS3 com variáveis customizáveis
- JavaScript ES6+ (sem frameworks)
- Google Fonts: Sora + JetBrains Mono
- LocalStorage para persistência

---

## 📋 Roadmap (Futuras Melhorias)

- [ ] Backup automático / sincronização com nuvem
- [ ] Sistema de relatórios com gráficos
- [ ] Notificações por WhatsApp
- [ ] App mobile (PWA)
- [ ] Múltiplos usuários / funcionários
- [ ] Integração com pagamentos

---

*SGCM — Desenvolvido para pequenos negócios que querem profissionalismo sem complexidade.*
