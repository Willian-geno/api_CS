# Entrega Capstone Q2 / Sprint 6

A ideia da API é armazenar produtos para a aplicação do capstone, possibilitando também criar e autenticar usuários na plataforma.

## Produtos

Para ver todos os produtos registrados use o Endpoint _GET /produtos_, que não necessita nem de corpo e nem de header e retornará um array com todos os itens cadastrados na API.

A busca por um produto específico pode ser feito pelo Endpoint _GET /produtos/id_, com o _id_ sendo o id do produto em questão. Novamente, não é necessário nenhum tipo de autenticação.

Um produto, por padrão, é um objeto com as propriedades id (número), img, title, weight, price, tags (array de strings), description, ingredient, category e valueNutri (um obejto com valor energético, carboidratos, proteínas, gorduras totais, gorduras, saturada, gorduras trans, fibra alimentar e sódio).

## Boxes

A visualização de boxes cadastradas pode ser feita da mesma forma que os Endpoints de Produtos, porém utilizando os Endpoints _GET /boxes_ e _GET /boxes/id_.

Uma box possui as propriedades id (número), img, title, weight, price, description, contents (array de strings) e category.

## Usuário

A criação do usuário é feita pelo Endpoint _POST /register_, onde são passados os dados do mesmo (name, email, phone, password, cep, address, area, number, complement e subscriber (booleano)).

Para fazer login é necessário apenas passar o email e a password para o Endpoint _POST /login_.

Ambos esses Endpoints retornarão o accessToken do usuário e um objeto user com as propriedades de email, name, phone, cep, address, area, number, complement, subscriber (booleano) e id (número).

Também é possível acessar os dados de um usuário específico pelo seu id usando o Endpoint _GET /users/id_. Porém, é preciso estar logado para acessar esse recurso e passar o token de acesso no header da requisição.

Finalmente, a alteração dos dados de um usuário pode ser feita com esse mesmo id pelo Endpoint _PATCH /users/id_, passando no coprpo da requisição as propriedades a ser alteradas. O retorno será um objeto com os todos os dados do usuário, já incluindo as alterações. Novamente, esse recurso só é disponibilizado se houver um token de acesso válido no header.
