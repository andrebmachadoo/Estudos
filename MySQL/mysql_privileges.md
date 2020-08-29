## Permissões 

>Os comandos abaixo cria um usuário no serviço de banco de dados, em seguida da todas as permissões ao usuário de qualquer de qualquer ponto que acessar. Obs: Não recomendado esse procedimento 

```SQL
#Create a new user in a localhost 
CREATE USER 'novousuario'@'localhost' IDENTIFIED BY 'password';

## Grant privileges to a specific user
GRANT ALL PRIVILEGES ON *.* TO 'usuario'@'%';

FLUSH PRIVILEGES;
```

## Outras permissoes 

- ***ALL PRIVILEGES*** - como vimos anteriormente, isso daria a um usuário do MySQL todo o acesso a uma determinada base de dados (ou se nenhuma base de dados for selecionada, todo o sistema)
- ***CREATE***  - permite criar novas tabelas ou bases de dados
- ***DROP***  - permite deletar tableas ou bases de dados
- ***DELETE***  - permite deletar linhas das tabelas
- ***INSERT***  - permite inserir linhas nas tabelas
- ***SELECT***  - permite utilizar o comando Select para ler bases de dados
- ***UPDATE***  - permite atualizar linhas das tabelas
- ***GRANT OPTION***    - permite conceder ou revogar privilégios de outros usuários



Para dar uma permissão a um usuário específico, você pode utilizar esta estrutura:
```sh
GRANT [tipo de permissão] ON [nome da base de dados].[nome da tabela] TO ‘[nome do usuário]’@'localhost’;
```

Se você precisar revogar uma permissão, a estrutura é quase idêntica a concedê-la:

```sh 
REVOKE [tipo de permissão] ON [nome da base de dados].[nome da tabela] FROM ‘[nome do usuário]’
```
```sh
DROP USER ‘demo’@‘localhost’;
```
```sh
quit 
```
e faça login de volta com este comando no terminal:

```sh
mysql -u [nome do usuário]-p
```