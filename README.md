# Painel ACADEPOL IP 2026/2027 · Turma 3

Dashboard web estático com grade, disciplinas, avaliações, diário e comparação curricular. Inclui 72 registros da grade Turma 3 de 24/09 a 31/10/2026 (242 h/a estimadas até 27/10 e 20 h/a programadas), sinalizando campos ilegíveis e a prova de Socorros de Urgência.

## Acesso

GitHub Pages: <https://josuecarpino.github.io/painel-acadepol-ip-2026/>

Site HTML puro, sem instalação. Dados locais permanecem guardados no navegador e backups JSON/CSV podem ser gerados. O repositório é público; **não** adicione dados pessoais/boletins/credenciais ao código.

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