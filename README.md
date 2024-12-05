
// app.js
const express = require('express');
const app = express();
const port = process.env.PORT || 3000;

app.get('/', (req, res) => {
    res.send('Olá, esta é a minha API na Nuvem!');
});

app.listen(port, () => {
    console.log(`API rodando na porta ${port}`);
});

// Passos para Deploy:

// 1. Crie um novo projeto Node.js:
// mkdir minha-api
// cd minha-api
// npm init -y

// 2. Instale o Express:
// npm install express

// 3. Crie o arquivo `app.js` com o código acima.

// 4. Inicie a API localmente para testar:
// node app.js

// 5. Configure o Azure App Service com a CLI do Azure para criar a infraestrutura de nuvem:
// az login
// az appservice plan create --name meu-plano --resource-group meu-resource-group --sku B1 --is-linux
// az webapp create --resource-group meu-resource-group --plan meu-plano --name minha-api-node --runtime "NODE|14-lts"

// 6. Faça o deploy para o Azure:

// Inicialize o Git:
// git init
// git add .
// git commit -m "Primeiro commit da API"

// Configure o remote do Azure:
// az webapp deployment source config-local-git --name minha-api-node --resource-group meu-resource-group

// Adicione o remote do Git e faça o push:
// git remote add azure https://<nome-da-api>.scm.azurewebsites.net:443/<nome-da-api>.git
// git push azure master

// 7. Acesse sua API na URL do Azure, algo como:
// https://minha-api-node.azurewebsites.net
