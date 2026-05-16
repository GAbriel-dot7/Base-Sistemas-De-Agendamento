# Fase 3 - Migração do LocalStorage para Backend (template Supabase)

Objetivo: substituir gradualmente as chamadas ao `DB` local por `RemoteDB`, mantendo fallback local enquanto não houver configuração Supabase.

Passos pequenos:

1. Criar `js/remote-db.js` (feito) que detecta config em `DB.getConfig().supabase` e usa a REST API do Supabase.
2. Substituir chamadas críticas em páginas por `await RemoteDB.get...` começando por leitura (GET) de `clientes` e `servicos`.
3. Substituir salvamentos (POST/PATCH) por `RemoteDB.save...`, mantendo o comportamento local se remoto não configurado.
4. Implementar sincronização manual: botão "Baixar backup" que chama `RemoteDB.pullAndImportAll()`.
5. Testar conflitos simples: editar local sem push e depois fazer pull.
6. Criar instruções no README para criar projeto Supabase e aplicar `supabase/schema.sql`.

Critérios de aceitação:

- Ao acessar sem Supabase configurado, app se comporta como antes (fallback para LocalStorage)
- Se Supabase configurado, leituras/escritas usam o backend e `pullAndImportAll` consegue importar os dados locais
- Export/Import via `js/sync.js` continua funcionando para backup manual

Próximos passos: começar substituindo as leituras do frontend por `RemoteDB.getClientes()` e `RemoteDB.getServicos()`, testar páginas `clientes.html` e `servicos.html`.
