# CLAUDE.md

Site público **"Trabalhe Conosco"** (`vagas.cantinaemcasa.com`) da Cantina em Casa / Lumar
Alimentos. Página estática única (`index.html`, ~23 KB), GitHub Pages (`CNAME`), sem build.
Português (BR). Branch padrão: `master`.

- **Repositório público**: só a chave `anon` do Supabase pode ficar no HTML; nada de segredos.
- Usa o projeto Supabase compartilhado (`taicaxtjtikdajmhtsxc`, mesmo do RH/CRM/Compras/Portal),
  como usuário **anônimo**: lê `formulario_config` (campos/vagas do formulário), insere em
  `candidatos` e sobe currículos no bucket `curriculos` do Storage.
- Quem consome esses dados é o módulo **Recrutamento** do `rh-app` (`RecrutamentoPage`). Mudou o
  formato de `candidatos` ou `formulario_config`? Ajuste os dois repositórios juntos. As tabelas
  são do domínio RH — não altere políticas de outros domínios, e lembre que policies para `anon`
  afetam o mundo todo: revise RLS antes de abrir qualquer permissão.
- Fora do SSO do Portal (público por natureza). Banner e ícones na raiz; `banner.png` tem 1,2 MB —
  não abra a imagem sem necessidade.
