# API DE GERENCIAMENTO DE FINANÇAS PESSOAIS

## 📄 Descriçao
A API serve como um gerenciador financeiro onde é possível adicionar receitas e despesas. A partir desses dados, temos o saldo atual, extrato de todas as transações com visualização das mais recentes primeiro. Para acessar, o usuário deve criar um cadastro e fazer login.

## 🚀 Funcionalidades

### Cadastro e Login
O cadastro de usuários passa por uma validação de consistência dos dados, seguido por uma verificação no banco de dados afim de evitar dados já existentes ou duplicidade.
![image](https://github.com/user-attachments/assets/ff1cd583-1455-4873-ae87-833283c3ed20)
![image](https://github.com/user-attachments/assets/804a1b65-151c-4486-a848-79b7f685f3fc)


Após o cadastro bem sucedido, o usuário está apto à fazer login. Novamente os dados inseridos passam por uma validação de consistência e existência, retornando a todo momento possíveis erros. 
Assim que o login é autorizado, o usuário recebe um token de autenticação via JWT (JsonWebToken). Esse mesmo token é verificado para acessar rotas privadas como efetuar transações e visualizar dados sensíveis.

### 🪙 Trasações
As transações são estruturadas com tipo, categoria, valor e descrição, sendo este último não obrigatório. O tipo é obrigatoriamente "Receita" ou "Despesa".

#### Exemplo de uma Transação: 
```bash
tipo: Despesa
categoria: Entretenimento 
valor: R$ -60,00
descrição: McDonald's 
```

### 🧾 Extrato e Saldo
O usuário tem a opção de visualizar o extrato de transações efetuadas bem como o saldo atual. Para ter acesso ao Extrato o sistema busca o usuarioId do usuário já autenticado e consulta no banco de dados as transações efetuadas pelo mesmo.

