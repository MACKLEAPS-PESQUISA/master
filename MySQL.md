# MySQL Database
Instruções pertinentes para o setup de um banco de dados MySQL no  **Ubuntu 16.04**. 

## Setup
Antes de qualquer coisa, atualize a lista de programas:

```bash
$ sudo apt-get update
```
Quando acabar, procure pelo mysql-server:

```bash
$ sudo apt-get install mysql-server
```

Ele pedirá por uma senha para o **ROOT USER**, escolha uma senha difícil de identificar. 


#### Secure Install - Opcional 
Depois, configure a instalação segura do MySQL:

```bash
$ sudo mysql_secure_installation
```

#### Se tudo ocorrer bem...
Para verificar se a instalação funcionou corretamente:

```bash
$ service mysql status
```
Deve aparecer algo indicando que o **serviço está ativo.**


## Criando um banco

O próximo passo agora é criar um banco.

#### Criando um usuário

Para criar um banco, primeiro precisamos criar um usuário.

```bash
$ mysql -u root -p
```
Isso servirá para se conectar ao MySQL usando **ROOT**, entre com sua senha e continue.

```bash
 mysql>
```
Quando aparecer esse registro no terminal, entre com:

```bash
$ CREATE USER 'mynewuser'@'localhost' IDENTIFIED BY 'password';
```

Lembre-se de subtituir **mynewuser** pelo nome de usuário desejado,
e **password** pela senha. 

Isso será usado para conexões ao banco, então pode ser interessante guardar
estas credenciais.

Não se esqueça do '**;**' em todos os comandos SQL.

#### Aplicando privilégios

Nós precisamos aplicar permissões de usuário para este novo usuário:

```bash
$ GRANT ALL PRIVILEGES ON * . * TO 'mynewuser@localhost';
```
e depois

```bash
$ FLUSH PRIVILEGES;
```
saia do MySQL usando

```bash
$ exit;
```

#### Conectando com o novo usuário

```bash
$ mysql -u mynewuser -p
```

Insina a senha e pronto! Você está conectado com seu usuário não ROOT.

### Criando um banco

Quando finalmente conectado ao usuário desejado, basta um comando para
o novo banco.

Onde **bancoTeste** é o nome do seu banco.

```bash
$ CREATE DATABASE bancoTeste;
```
Para usar esse banco, use o comando **USE**

```bash
$ use bancoTeste;
``` 
Para sair, de novo:

```bash
$ exit;
```

## Conclusões

Agora seu banco está criado e **MySQL** está acessível como serviço no seu sistema.

Caso não consiga conectar em algum momento, provavelmente é porque o banco está inativo,
um simples 

```bash
$ service mysql start
```

deve servir para iniciar o **MySQL**


Retirado de:

[How To Install MySQL on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-16-04)

&

[How to Install and Use MySQL on Ubuntu 16.04](https://www.fullstackpython.com/blog/install-mysql-ubuntu-1604.html)

