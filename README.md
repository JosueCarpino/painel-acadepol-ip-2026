# Painel ACADEPOL IP 2026/2027 · Turma 3

Dashboard web estático com grade, disciplinas, avaliações, diário e comparação curricular. Inclui **105 registros de grade**, de 24/09 a 21/11/2026. As semanas de 09–14/11 (**40 h/a**) e de 16–21/11 (**22 h/a**) entram como **concluídas somente para cálculo**, não como frequência efetiva. Os dois blocos ilegíveis de 11 e 14/11 não recebem horas. As aulas anteriores já marcadas como realizadas continuam preservadas; outros lançamentos exigem conferência.

## Acesso

GitHub Pages: <https://josuecarpino.github.io/painel-acadepol-ip-2026/>

Site HTML puro, sem instalação. Dados locais permanecem guardados no navegador e backups JSON/CSV podem ser gerados. O repositório é público; **não** adicione dados pessoais/boletins/credenciais ao código.

A grade de novembro aparece no painel online e no arquivo `grade_turma3_2026.csv`. Ao conectar o Firebase, registros importados da grade são reconciliados sem duplicar IDs. Dados manuais existentes devem ser preservados; faça backup JSON antes de escolher substituir uma versão da nuvem.

## Grade 16–21/11/2026: conclusão antecipada para cálculo

A grade enviada em 15/11 acrescenta **22 h/a**, sem marcar presença, realização efetiva ou aprovação.

| Data | Atividade | Horário | h/a |
|---|---|---|---:|
| 16/11 | Estágio | 09h–12h | 4 |
| 16/11 | Prova de História Policial | 16h30–17h50 | 2 |
| 17/11 | Conduta Policial | 08h–10h50 | 4 |
| 18/11 | Estágio | 09h–12h | 4 |
| 19/11 | Comunicação e Documentação | 08h–10h50 | 4 |
| 19/11 | Defesa Pessoal e Condicionamento | 12h20–15h10 | 4 |
| 20/11 | Consciência Negra | Feriado | 0 |
| 21/11 | Facultativo | Sem carga na grade | 0 |
| | **Total** | | **22** |

Os estágios de 09h a 12h contam como 4 h/a estimadas por bloco, seguindo o padrão da grade anterior. O acumulado de referência passa de **346 para 368 h/a**, ou **36,0% de 1.022 h/a**. Os totais pessoais podem variar de acordo com os lançamentos e as projeções ativas no painel.

## Grade 09–14/11/2026: conclusão antecipada para cálculo

A pedido do usuário em **08/11/2026**, a programação de **09 a 14/11** foi importada com a marcação **“Concluída (cálculo)”**. Trata-se de projeção antecipada, não de aula realizada nem de frequência confirmada. A projeção pode ser desfeita na aba **Grade Turma 3**; depois que a data ocorrer, a aula também poderá ser marcada como efetivamente realizada.

| Atividade | h/a consideradas para cálculo |
|---|---:|
| Armamento (GOE e estande GM Jundiaí) | 12 |
| Informática Policial (UEP2) | 8 |
| Ética Policial | 8 |
| Defesa Pessoal e Condicionamento (GOE) | 4 |
| Estágio | 8 |
| **Total projetado** | **40** |

As células ilegíveis de 11/11 (primeiro bloco) e 14/11 (segundo bloco) não foram contabilizadas, e o estágio aparece como **atividade curricular**, não como uma das 22 disciplinas principais.

### Revisão do acumulado — 08/11/2026

A grade da nova semana **soma** às anteriores: 262 h/a de 24/09 a 31/10 + 44 h/a de 03 a 07/11 + 40 h/a da semana 09–14/11 = **346 h/a previstas no acumulado da grade**, ou **33,9% de 1.022 h/a**. Células `########`, folgas e feriados permanecem sem carga.

O indicador anterior mostrava **60 h/a** porque considerava apenas 20 h/a marcadas realizadas e 40 h/a projetadas. Excluía indevidamente **262 h/a** de registros antigos pré-lançados e **24 h/a** da grade de 05–07/11 que ainda não tinham sido importadas para o diário. O novo acumulado considera todos esses períodos, sem substituir ou apagar registros anteriores.

**Como o cálculo funciona:**
- as horas existentes no diário entram uma única vez, mesmo quando ainda são pré-lançamentos;
- as 24 h/a de 05–07/11 que faltavam são acrescentadas **virtualmente ao cálculo**, por dia e disciplina, somente na parcela que ainda não tem lançamento equivalente; isso preserva suas edições manuais e não cria frequência fictícia no Firebase;
- as 40 h/a de 09–14/11 continuam como projeções antecipadas e podem ser desativadas individualmente;
- o diário exibe separadamente o total efetivamente salvo e o acumulado usado no cálculo, incluindo a diferença explicada. A exportação de diário CSV identifica os complementos virtuais.

Na revisão de 08/11, o total do usuário podia diferir das **346 h/a de referência**, caso tenha ajustado, excluído ou acrescentado aulas. **São horas para planejamento, não comprovação de frequência institucional nem conclusão integral das matérias.**

## Carga horária prevista (matriz PDF CFTP 2026)

A nova matriz recebida em 27/10/2026 informa **1.022 horas-aula**, com uma hora-aula de **40 minutos**. A distribuição adotada pelo painel é:

| Categoria | Carga prevista |
|---|---:|
| 22 disciplinas principais | 918 h/a |
| Quatro módulos adicionais (Aprendizagem Participativa 12; Sistema de Justiça Criminal/Gênero 8; Exercício de Gerenciamento de Crises 16; Exercício de Inteligência Policial 8) | 44 h/a |
| Subtotal de disciplinas | **962 h/a** |
| Cinco palestras de 4 h/a | 20 h/a |
| Estágios curriculares | 40 h/a |
| **Total previsto** | **1.022 h/a** |

Os 27 subtópicos da matriz foram associados às 22 disciplinas do painel. **Subtópicos já incluídos na carga principal não são somados uma segunda vez**. Na planilha do painel, Investigação de Crimes contra o Meio Ambiente está agrupada em Investigação Policial (12 h/a de seus 132 h/a), embora a matriz PDF a apresente em linha própria.

Em **Disciplinas**, o painel agora mostra as horas previstas em 2026, siglas, períodos informados e barras de progresso baseadas nos lançamentos. A aba **Referência 2024** continua disponível separadamente. Em **Disciplinas** ou **Configurações**, a opção **Matriz 2026 CSV** exporta todas as linhas, inclusive os módulos e as palestras. Metas personalizadas existentes não são apagadas.

### Divergências preservadas da fonte

- O PDF informa **1.022 h/a** no total consolidado, mas também menciona **974 h/a do CFTP** no rodapé. O painel usa o total consolidado de 1.022 h/a sem tentar explicar a diferença.
- Alguns números de períodos são inconsistentes com a carga informada (por exemplo, Teoria Geral da Investigação: 28 h/a / 6 períodos; Investigação Patrimonial: 12 h/a / 6 períodos). Foram mantidos os dois valores escritos no documento, sem correção arbitrária.
- O número de períodos no subtotal geral também não reconcilia perfeitamente com a soma das linhas. Os **totais em h/a** são a referência para os indicadores.
- As horas registradas incluem pré-lançamentos de grade que dependem de validação de presença. Metas previstas não são, por si sós, horas cursadas.

## Melhorias UI/UX (novembro de 2026)

A interface usa a folha de estilos `ui-ux.css`, além dos estilos embutidos.

- **Visão geral:** o acumulado e o percentual aparecem primeiro, com a separação entre horas realizadas informadas, pré-lançamentos, complemento e projeções. Aulas e avaliações têm acesso direto. As análises por mês e por disciplina ficam em uma seção expansível.
- **Grade:** abre na última programação recebida, com resumo da carga, busca por aula, local ou data e filtros rápidos para próximas aulas, projeções, pendências e histórico completo.
- **Celular:** barra inferior com atalhos para Início, Grade, Agenda e Disciplinas. A grade usa cartões em telas menores. Todas as abas continuam disponíveis no menu Mais.
- **Acessibilidade e navegação:** indicação do filtro ou aba ativa, foco de teclado no conteúdo após a navegação e links diretos para cada seção. O modo escuro, os atalhos existentes e o retorno de foco dos diálogos foram preservados.
- **Firebase:** a lógica de sincronização, permissões, backups e registros permanece a mesma.

**Interpretação dos indicadores:** “marcada realizada” significa declaração no painel, não comprovação institucional de presença. Pré-lançamentos entram no percentual de planejamento, não comprovam realização e não contam como frequência. Os totais originais das aulas importadas continuam recuperáveis no diário e nos backups. Sempre confirme `Nuvem sincronizada` antes de depender de outro dispositivo.

## Sincronização com Firebase ACADEPOL

O painel utiliza **exclusivamente** o projeto Firebase separado `acadepol-ae423`, com a configuração Web fornecida pelo proprietário. O projeto financeiro anterior NÃO é acessado e não é necessário instalar `firebase` com npm: o site no GitHub Pages importa o SDK no navegador.

A configuração do aplicativo Web **já está publicada no `index.html`**. Para ativar de fato os salvamentos privados na nuvem, faltam as configurações administrativas abaixo dentro do **Firebase Console do projeto ACADEPOL**:

1. Em [Firebase Console](https://console.firebase.google.com/), selecione **acadepol-ae423**.
2. Em **Build → Authentication → Sign-in method**, habilite o provedor **E-mail/senha**. Em **Authentication → Settings → Authorized domains**, confirme `josuecarpino.github.io` caso o painel indique falha de domínio não autorizado.
3. Em **Build → Firestore Database**, crie o banco de dados, se ainda não existir; selecione o **modo de produção**.
4. Em **Firestore Database → Rules**, publique o conjunto de regras restritas do arquivo [firestore-acadepol.rules.example](firestore-acadepol.rules.example). Faça isso **somente em acadepol-ae423**, nunca no projeto financeiro.
5. Abra o [painel](https://josuecarpino.github.io/painel-acadepol-ip-2026/) e escolha **Configurações → Firebase**. Faça backup JSON dos registros antes do primeiro envio.
6. Crie sua conta no Firebase Authentication pelo painel ou entre com seu e-mail/senha. Se a nuvem estiver vazia, clique em **Enviar meus dados para o Firebase**; se houver dados na nuvem, escolha a origem desejada com atenção.
7. Em outro dispositivo, entre com a mesma conta e use **Usar dados da nuvem** se aparecer um conflito.

**Status:** código conectado ao projeto Web, mas o envio ao Firestore só pode ser considerado ativo depois de uma autenticação e gravação bem-sucedidas no navegador. Não há promessa de que o banco ou as regras já tenham sido configurados remotamente.

### Onde ficam as informações

Coleção/documento: `users/{uid}/acadepol/state`, contendo versão, conteúdo serializado do painel, data de atualização e identificador da sessão. Cada usuário tem um UID próprio; não são criadas coleções públicas de avaliações ou diários.

### Cuidados

- A configuração Web do Firebase (`apiKey`, `projectId`, `appId`) é pública por natureza; **ela não substitui autenticação nem regras de acesso**. Nunca publique chaves de serviço ou credenciais administrativas.
- Os salvamentos são feitos localmente primeiro. Quando conectado, o app sincroniza automaticamente alterações e oferece resolução manual de conflito entre dispositivos; em caso de erro ou falta de rede, mantenha um backup JSON e tente sincronizar depois.
- Dados da grade e estimativas são referências provisórias; frequência e horas confirmadas devem ser corrigidas manualmente.
- O Firestore exige configuração e pode gerar custos dependendo do uso e do plano.

## Referências

- [Firebase Authentication – E-mail e senha](https://firebase.google.com/docs/auth/web/password-auth)
- [Cloud Firestore Security Rules](https://firebase.google.com/docs/firestore/security/rules-conditions)
- [GitHub Pages](https://docs.github.com/en/pages)