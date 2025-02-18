# Java Database 

Este repositório contém um exemplo básico de como conectar-se a um banco de dados MySQL utilizando JDBC em Java. O código cria uma tabela de usuários, insere dados e lista os usuários cadastrados.

## Funcionalidades

- Conexão com um banco de dados MySQL local.
- Criação de tabela de usuários (caso não exista).
- Inserção de novos usuários na tabela.
- Listagem de usuários existentes na tabela.

## Como Usar

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/nome-do-repositorio.git

2. Substitua os valores de conexão (URL, USER, PASSWORD) com as informações do seu banco de dados MySQL:
- URL: O endereço do seu banco de dados MySQL (exemplo: jdbc:mysql://localhost:3306/meu_banco).
- USER: O nome de usuário do banco de dados.
- PASSWORD: A senha do banco de dados.

3. Compile e execute o código Java:
```bash
javac DatabaseExample.java
java DatabaseExample
```

## Dependências
- Java 8 ou superior.
- MySQL (ou MariaDB) com o conector JDBC configurado.

## Observações
Este código é um exemplo simples para fins educacionais. Não é adequado para ambientes de produção sem modificações para segurança e eficiência.
