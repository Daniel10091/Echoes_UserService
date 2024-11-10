# Estrutura do User Service (Serviço de Usuário)

O User Service será responsável por:

 - Cadastro e autenticação de usuários.
 - Atualização de informações de perfil.
 - Gerenciamento de dados de perfil e preferências dos usuários.

### 1.1 Definição das Funcionalidades

Aqui estão as principais funcionalidades que o User Service deve ter:

1. Registro de Usuário:
 - Endpoint: POST /users/register
 - Função: Recebe os dados do usuário (nome, e-mail, senha, etc.) e cria uma nova conta.

2. Autenticação de Usuário:

 - Endpoint: POST /users/login
 - Função: Verifica as credenciais do usuário e gera um token de autenticação (JWT, por exemplo).

3. Atualização de Perfil:

 - Endpoint: PUT /users/{userId}
 - Função: Permite ao usuário atualizar suas informações de perfil, como nome e foto.

4. Consulta de Perfil:

 - Endpoint: GET /users/{userId}
 - Função: Retorna as informações de perfil público do usuário.

5. Deleção de Conta:

 - Endpoint: DELETE /users/{userId}
 - Função: Permite que um usuário exclua sua conta e todos os dados associados.

### 1.2 Estrutura do Banco de Dados

Para começar, você pode estruturar o banco de dados com uma tabela chamada users. Um exemplo simplificado de como os dados poderiam estar organizados:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Campo&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Tipo&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Descrição

--------------- | --------------- | --------------------------------------------

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`id`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UUID&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;Identificador único do usuário.

&nbsp;&nbsp;&nbsp;`username`&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;VARCHAR&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;Nome de usuário único.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`email`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;VARCHAR&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;E-mail do usuário (único).

&nbsp;&nbsp;&nbsp;&nbsp;`password`&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;VARCHAR&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;Senha criptografada do usuário.

&nbsp;&nbsp;&nbsp;`profile_pic`&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;VARCHAR&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;URL da foto de perfil.

&nbsp;&nbsp;&nbsp;`created_at`&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;VARCHAR&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;Data de criação da conta.

&nbsp;&nbsp;`updated_at`&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;VARCHAR&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;Data da última atualização de perfil.