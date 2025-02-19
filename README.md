## 🚀 Testes de API – ServRest (Postman + Newman)
Este repositório contém os testes automatizados da API ServRest, utilizando Postman e Newman. Os testes cobrem os principais fluxos do sistema, incluindo usuários, produtos e carrinho de compras.

## 📌 Tecnologias Utilizadas
Postman – Criação e execução dos testes de API.
Newman – Executor de coleções Postman via CLI.
GitHub Actions – Automação da execução dos testes.
📁 Estrutura do Projeto
python
Copiar
Editar
├── collections/               # Coleções de testes do Postman  
│   ├── usuarios.json          # Testes de criação e login de usuários  
│   ├── produtos.json          # Testes de gerenciamento de produtos  
│   ├── carrinho.json          # Testes do fluxo de compras  
│  
├── environments/              # Configuração dos ambientes Postman  
│   ├── environment.json       # Variáveis de ambiente para testes  
│  
├── globals/                   # Variáveis globais do Postman  
│   ├── globals.json           # Definições globais dos testes  
│  
├── .github/workflows/         # Pipeline CI/CD  
│   ├── newman-tests.yml       # Configuração do GitHub Actions  
│  
└── README.md                  # Documentação do projeto  

## 🎯 Cenários de Testes
🔹 Usuários
✅ Criar um novo usuário
✅ Fazer login com usuário válido
✅ Tentar login com credenciais inválidas

🔹 Produtos
✅ Listar todos os produtos
✅ Buscar um produto por ID
✅ Criar, atualizar e deletar um produto

🔹 Carrinho de Compras
✅ Adicionar um produto ao carrinho
✅ Remover um item do carrinho

🛠 Como Executar os Testes
🔸 1. Instalar Dependências
Antes de executar os testes, instale o Newman globalmente:

npm install -g newman newman-reporter-htmlextra

🔸 2. Executar Testes Manualmente
Executar os testes de Usuários

newman run collections/usuarios.json -e environments/environment.json --reporters cli,htmlextra --reporter-htmlextra-export result/usuarios_report.html
Executar os testes de Produtos

newman run collections/produtos.json -e environments/environment.json --reporters cli,htmlextra --reporter-htmlextra-export result/produtos_report.html
Executar os testes de Carrinho

newman run collections/carrinho.json -e environments/environment.json --reporters cli,htmlextra --reporter-htmlextra-export result/carrinho_report.html
## 🔸 3. Executar via GitHub Actions
Os testes são executados automaticamente via GitHub Actions quando um push é feito na branch principal.

## 📊 Relatórios
Os relatórios HTML são gerados na pasta result/. Para visualizar, basta abrir o arquivo no navegador.
