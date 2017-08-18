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

O próximo passo agora é criar um banco:
