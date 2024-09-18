# Pesquisa sobre conceitos em NODE.JS

## Controller

## Introdução

O padrão Controller é um componente crucial na arquitetura de aplicações web, especialmente em projetos construídos com Node.js. Ele atua como um intermediário entre as requisições do cliente e a lógica de negócios, proporcionando uma organização clara e fácil de manter.

## Função do Controller

Os controllers desempenham várias funções importantes:

1. **Gerenciar a Lógica de Negócios**: Contêm as funções que processam requisições e aplicam regras de negócio.

2. **Interagir com Modelos**: Comunicando-se com os modelos da aplicação, que representam os dados e a lógica de acesso ao banco de dados, para operações de CRUD (Create, Read, Update, Delete).


   ### Exemplo de Função de Criação

   Aqui está um exemplo de uma função para criar um novo usuário:

   ```javascript
   const Usuario = require('../models/usuario');

   exports.criarUsuario = async (req, res) => {
       try {
           const novoUsuario = new Usuario(req.body);
           await novoUsuario.save();
           res.status(201).json(novoUsuario);
       } catch (error) {
           res.status(400).json({ message: 'Erro ao criar usuário', error });
       }
   };

3. **Retornar Respostas ao Cliente**: Enviam as respostas apropriadas de volta ao cliente, geralmente em formato JSON.

## Vantagens do Uso de Controllers

- **Organização do Código**: Facilita a leitura e a manutenção ao separar a lógica de negócios das rotas.
  
- **Reutilização de Código**: Funções podem ser reutilizadas em diferentes rotas, evitando a duplicação.

- **Facilidade de Testes**: Permitem que o código seja testado de forma isolada, melhorando a qualidade do software.

- **Escalabilidade**: A estrutura modular facilita a adição de novas funcionalidades sem comprometer a aplicação.

## Estrutura Comum

Um controller em Node.js normalmente contém funções para as seguintes ações:

- **Listar**: Obter todos os registros de um recurso.
- **Criar**: Adicionar um novo registro.
- **Atualizar**: Modificar um registro existente.
- **Excluir**: Remover um registro.

==========================

# REST em Aplicações Node.js

REST (Representational State Transfer) é um estilo arquitetural para construir APIs que usam operações HTTP como GET, POST, PUT e DELETE para manipular recursos. Em aplicações Node.js, REST é comumente implementado usando frameworks como Express.js.

Uma API REST define endpoints (URLs) que representam recursos e são acessados de forma stateless, significando que cada requisição é independente e contém todas as informações necessárias. Os dados são geralmente enviados e recebidos no formato JSON.

