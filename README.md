
# API RESTFUL USANDO NODEJS, Express & TS

Leia em outras linguas: [Português](README.md), [English](README.en-US.md)

## Objetivo
- Criar 4 endpoints GET/POST/PUT/DELETE

Várias ferramentas podem ser utilizadas para fazer as requisições como Postman, Insomnia ou extensões do VS Code como REST Client.

Após baixar o projeto como zip ou via git clone:
```sh
	git clone https://github.com/Fizer65/test-FullstackJSJunior.git
```
### NodeJS
Para baixar as dependências do projeto:
```sh
	npm install
```
Iniciar a API:
```sh
	node run start
```
### Yarn
Para baixar as dependências do projeto:
```sh
	yarn install
```
Iniciar a API:
```sh
	yarn start
```

# Como utilizar
#### Porta utilizada: 3333
Exemplo de rota: `http://localhost:3333/api/v1/users` 

|  HTTP  |        	ROUTE          |	                BODY    	 	           |	        DESCRIÇÃO       |
|--------|-------------------------|-----------------------------------------|--------------------------|
| GET    |	/api/v1/users          |	              	                       |  Listar todos usuários   | 
| GET    |	/api/v1/users/user_id  |		    	                               |  Listar único usuário    |
| POST   |	/api/v1/users          |  JSON (email,senha) 	                   |	Criar único usuário     |
| PUT    |	/api/v1/users/user_id  |  JSON (email,senha nova, senha antiga)  |	Alterar único usuário   |
| DELETE |	/api/v1/users	         |	                    	                 |  Deletar todos usuários  |
| DELETE |  /api/v1/users/user_id  |		                 	                   |  Deletar único usuário   |

### - Listar todos usuários
- Requisição com protocolo `GET` em `/api/v1/users`.
- Retorna todos os usuários do banco de dados retornados com: ID, email, senha.

### - Listar único usuário
- Requisição com protocolo `GET` em `/api/v1/users/user_id`.
- O `user_id` é o ID do usuário requisitado
- Retorna: ID, email, senha.

### - Criar único usuário
- Requisição com protocolo `POST` em `/api/v1/users/`.
- Também precisa de um body do tipo JSON com: email e senha:
```json
{
	"email": "exemplo@gmail.com",
	"password": "senha"
}
```
- O ID será gerado de forma automática com o pacote UUID e as senhas serão criptografadas com o algoritmo Argon2
- Returna status `200 OK` se a requisição foi bem sucedida.

### - Alterar único usuário
- Requisição com protocolo `PUT` em `/api/v1/users/user_id`. 
- O `user_id` é o ID do usuário que terá os dados alterados.
- um body do tipo JSON com o email, senha antiga para validação e a nova senha:

```json
{
	"email": "novo.exemplo@gmail.com",
	"oldPassword": "velhaSenha",
	"newPassword": "novaSenha"
}
```
- Returna status `200 OK` se a requisição foi bem sucedida.

### - Deletar todos usuários
- Requisição com protocolo `DELETE` em `/api/v1/users/`. 
- ##### `⚠️ Atenção`: Fazer isso irá deletar TODOS os usuários. Pense com cuidado antes de utilizar essa rota.

- Returna status `200 OK` se a requisição foi bem sucedida.

### - Deletar único usuário
- Requisição com protocolo `DELETE` em `/api/v1/users/user_id`.
- O `user_id` é o ID do usuário que será deletado.

- Returna status `200 OK` se a requisição foi bem sucedida.