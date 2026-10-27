# Painel ACADEPOL IP 2026/2027 · Turma 3

Dashboard web estático com grade, disciplinas, avaliações, diário e comparação curricular. Inclui 72 registros da grade Turma 3 de 24/09 a 31/10/2026 (242 h/a estimadas até 27/10 e 20 h/a programadas), sinalizando campos ilegíveis e a prova de Socorros de Urgência.

## Acesso

GitHub Pages: <https://josuecarpino.github.io/painel-acadepol-ip-2026/>

Site HTML puro, sem instalação. Dados locais permanecem guardados no navegador e backups JSON/CSV podem ser gerados. O repositório é público; **não** adicione dados pessoais/boletins/credenciais ao código.

## Sincronização opcional com Firebase

O painel está integrado com Firebase Authentication (e-mail/senha) e Cloud Firestore. O projeto Web configurado por padrão é `financas-1c48a`, que foi previamente fornecido pelo proprietário. Pode ser substituído dentro de **Configurações → Firebase → Trocar projeto Firebase**. **O Firebase não estará operacional antes da configuração do console e das regras de segurança.**

Para conectar o projeto:

1. Abra [Firebase Console](https://console.firebase.google.com/), selecione o projeto `financas-1c48a` (ou outro projeto de sua preferência).
2. Em **Authentication → Sign-in method**, habilite **Email/Password**. Não habilite login anônimo se não precisar dele. Confirme que o site está autorizado caso a plataforma solicite.
3. Em **Firestore Database**, crie um banco de dados, caso ainda não exista. Use **modo de produção**, sem regras de teste públicas.
4. Em **Firestore → Rules**, autorize apenas o documento `users/{uid}/acadepol/state` para o próprio UID autenticado. Use a referência de `firestore-acadepol.rules.example`. **Se o Firebase também hospeda seu sistema financeiro, incorpore apenas o bloco específico para ACADEPOL às regras existentes; não substitua todas as regras, pois isso poderia quebrar o outro aplicativo.**
5. Abra o painel publicado → **Configurações** → **Firebase**. Entre com seu e-mail/senha do Firebase Authentication ou crie uma conta por essa tela.
6. Na primeira conexão, se sua nuvem ainda estiver vazia, clique **Enviar meus dados para o Firebase**. Se já houver backup, escolha entre **Usar dados da nuvem** e **Enviar dados locais**. Faça um backup JSON antes de substituir qualquer versão.
7. Em um segundo dispositivo, abra o mesmo endereço e entre com a **mesma conta Firebase**. Se aparecer a escolha de versão, prefira **Usar dados da nuvem** para trazer os dados anteriormente enviados.

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