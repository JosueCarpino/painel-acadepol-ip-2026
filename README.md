# Painel ACADEPOL IP 2026/2027

Dashboard interativo para organizar disciplinas, acompanhamento de horas/aula, avaliações, calendário, diário de atividades e comparações com a matriz de 2024.

## Acessar online

Depois de ativar o GitHub Pages nas configurações do repositório, o painel estará disponível em:

**https://josuecarpino.github.io/painel-acadepol-ip-2026/**

## Publicação com GitHub Pages

1. No GitHub, acesse **Settings → Pages**.
2. Em **Build and deployment**, escolha **Deploy from a branch**.
3. Escolha a branch **main**, pasta **/(root)** e salve.
4. O `index.html` é a página inicial. Não há dependências, servidor ou build.

## Privacidade e armazenamento

- O conteúdo do `index.html`, incluindo a matriz e nomes de docentes que aparecem no painel, fica publicamente acessível após a publicação.
- Não publique a planilha Excel original ou dados pessoais/administrativos sigilosos.
- As alterações (aulas, notas, observações, datas, status) são guardadas em **localStorage**, no navegador em que o painel foi usado. **Não há sincronização entre aparelhos.**
- Para backup e transferência entre navegadores, exporte o JSON no painel e importe no outro navegador.
- A marcação `noindex` pede aos buscadores que não indexem o site, mas **não protege sua privacidade**.

## Observações sobre os dados

- A matriz da turma atual apresenta 22 disciplinas principais e meta total de 1.022 h/a.
- A matriz histórica de 2024 é usada como referência de estimativa; não é a carga oficial da turma atual.
- A previsão de conclusão está inicialmente em **12/03/2027**, editável no painel.
