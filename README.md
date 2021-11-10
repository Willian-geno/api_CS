# Entrega Capstone Q2 / Sprint 6

A ideia da API é armazenar produtos para a aplicação do capstone, possibilitando também criar e autenticar usuários na plataforma.

## Produtos

Para ver todos os produtos registrados use o Endpoint _GET /produtos_, que não necessita nem de corpo e nem de header.

A busca por um produto específico pode ser feito pelo Endpoint _GET /produtos/id_, com o _id_ sendo o id do produto em questão. Novamente, não é necessário nenhum tipo de autenticação.

Um produto, por padrão, é um objeto com as propriedades id (número), img, title, weight, price, tags (array de strings), description, ingredient, category e valueNutri (um obejto com valor energético, carboidratos, proteínas, gorduras totais, gorduras, saturada, gorduras trans, fibra alimentar e sódio).

## Usuário

A criação do usuário é feita pelo Endpoint _POST /register_, onde são passados os dados do usuário (name, email e password).

Para fazer login é necessário apenas passar o email e a password para o Endpoint _POST /login_.

Ambos esses Endpoints retornarão o accessToken do usuário e um objeto user com as propriedades de email, name e id (número).

Finalmente, também é possível acessar os dados de um usuário específico usando o Enpoint _GET /users/id_. Porém, é preciso estar logado para acessar esse recurso e passar o token de acesso no header da requisição.
