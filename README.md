# Painel ACADEPOL IP 2026/2027 · Turma 3

Dashboard web estático com grade, disciplinas, avaliações, diário e comparação curricular. Inclui 72 registros da grade Turma 3 de 24/09 a 31/10/2026 (242 h/a estimadas até 27/10 e 20 h/a programadas), sinalizando campos ilegíveis e a prova de Socorros de Urgência.

## Acesso

GitHub Pages: <https://josuecarpino.github.io/painel-acadepol-ip-2026/>

Site HTML puro, sem instalação. Dados locais permanecem guardados no navegador e backups JSON/CSV podem ser gerados. O repositório é público; **não** adicione dados pessoais/boletins/credenciais ao código.

## Sincronização com Firebase ACADEPOL

O painel já contém suporte a Firebase Authentication (e-mail/senha) e Cloud Firestore. **Não usa mais o projeto financeiro `financas-1c48a`.** A configuração Web do novo projeto ACADEPOL ainda deve ser fornecida; até lá, o site permanece funcional com armazenamento local e backup JSON.

Para conectar o projeto separado:

1. Abra [Firebase Console](https://console.firebase.google.com/), selecione seu projeto **ACADEPOL** e vá a **Configurações do projeto → Seus aplicativos**. Registre um **aplicativo Web (</>)** se ainda não existir; copie o bloco `const firebaseConfig = { ... }`. Não precisa ativar Firebase Hosting: o site está no GitHub Pages.
2. No projeto ACADEPOL, em **Authentication → Sign-in method**, habilite **Email/Password** e confira em **Settings → Authorized domains** o domínio `josuecarpino.github.io` (adicione-o se necessário).
3. Em **Firestore Database**, crie o banco de dados no **modo de produção** e escolha a região disponível que preferir.
4. Em **Firestore → Rules**, substitua as regras iniciais desse **novo projeto** pelas regras restritas em [firestore-acadepol.rules.example](firestore-acadepol.rules.example) e publique-as. Essas regras permitem ao próprio usuário autenticado ler/gravar somente seu documento `users/{uid}/acadepol/state`. **Não aplique essas regras no projeto financeiro.**
5. Abra o painel → **Configurações → Firebase → Configurar o novo Firebase ACADEPOL**. Cole o bloco `firebaseConfig` e salve. Como alternativa, forneça o objeto de configuração Web para inserir no código GitHub e evitar configurar cada navegador.
6. Faça um backup JSON antes da primeira sincronização. Entre ou crie conta com e-mail e senha. Escolha **Enviar meus dados para o Firebase**. Nos demais dispositivos, use **Usar dados da nuvem**.

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