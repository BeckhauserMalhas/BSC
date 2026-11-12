# Guia: colocando o BSC no ar, de graça

Você vai usar 3 serviços gratuitos: **Supabase** (banco de dados), **GitHub** (guardar os arquivos) e **Vercel** (publicar o site).

## Parte 1 – Banco de dados (Supabase)
1. Acesse https://supabase.com → **Start your project** → entre com Google/GitHub.
2. **New project**: dê um nome (ex.: `bsc`), crie uma senha de banco (guarde), escolha a região mais próxima (ex.: *South America – São Paulo*) e clique em **Create**. Aguarde ~2 minutos.
3. No menu da esquerda, abra **SQL Editor → New query**.
4. Abra o arquivo `schema.sql`, copie **todo** o conteúdo, cole no editor e clique em **Run**. Deve aparecer "Success". (As tabelas aparecem em **Table Editor**.)
5. Vá em **Project Settings (engrenagem) → API** e copie:
   - **Project URL**
   - **anon public** key (a chave longa marcada como `anon`/`public`). *Nunca use a `service_role`.*

## Parte 2 – Colocar as chaves no app
1. Abra `index.html` em um editor de texto (Bloco de Notas serve).
2. No topo, troque os dois textos:
   ```js
   const SUPABASE_URL = "COLE_AQUI_A_PROJECT_URL";
   const SUPABASE_KEY = "COLE_AQUI_A_ANON_PUBLIC_KEY";
   ```
   Mantenha as aspas. Salve.
3. Teste: dê duplo clique no `index.html`. Se abrir e você conseguir salvar a Missão, está funcionando.

## Parte 3 – Publicar (Vercel)
1. Crie conta em https://github.com → **New repository** → nome `bsc` → **Create**.
2. Clique em **uploading an existing file**, arraste o `index.html` (e, se quiser, `schema.sql`/`GUIA.md`) → **Commit changes**.
3. Acesse https://vercel.com → **Sign up with GitHub** → **Add New → Project** → escolha o repositório `bsc` → **Deploy** (não precisa mudar nada).
4. Em ~1 minuto você recebe um link `https://bsc-xxxx.vercel.app`. Funciona em computador e celular.

Para atualizar o app depois: edite o arquivo no GitHub (lápis ✏️) e salve; a Vercel republica sozinha.

## Como usar (ordem sugerida)
1. **Identidade**: preencha Missão, Visão, Valores e crie 3–4 Temas.
2. **Perspectivas**: em cada uma, **+ Objetivo** → **+ KPI** (meta e valor atual; % e semáforo são automáticos) → **+ Iniciativa**.
   Semáforo: 🟢 ≥ 90% · 🟡 70–89% · 🔴 < 70%. Para indicadores "quanto menor, melhor" (custos, retrabalho), escolha *Menor é melhor*.
3. **🔗 em cada objetivo**: marque quais objetivos ele impacta → o **Mapa Estratégico** desenha as setas de causa e efeito.
4. **Acompanhamento**: filtre por responsável/perspectiva e use **Imprimir / PDF** nas reuniões.

## ⚠️ Segurança (importante)
Esta versão inicial não tem login: **quem tiver o link do site pode ver e editar os dados**. Não divulgue o link e não coloque informações sigilosas. Um próximo passo recomendado é adicionar login com o Supabase Auth.

## Custos
Supabase Free (500 MB) e Vercel Hobby são gratuitos. Obs.: projetos Supabase gratuitos são pausados após ~1 semana sem uso; basta clicar em **Restore** no painel.
