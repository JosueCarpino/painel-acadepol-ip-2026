# Painel ACADEPOL IP 2026/2027 · Turma 3

Dashboard web estático com grade, disciplinas, avaliações, diário e comparação curricular. Inclui 72 registros da grade Turma 3 de 24/09 a 31/10/2026 (242 h/a estimadas até 27/10 e 20 h/a programadas), sinalizando campos ilegíveis e a prova de Socorros de Urgência.

## Acesso

GitHub Pages: <https://josuecarpino.github.io/painel-acadepol-ip-2026/>

Site HTML puro, sem instalação. Dados locais permanecem guardados no navegador e backups JSON/CSV podem ser gerados. O repositório é público; **não** adicione dados pessoais/boletins/credenciais ao código.

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