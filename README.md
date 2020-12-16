# Shopping Cart Infra

O objetivo desse repositorio e facilmente provisionar a infra estrustura necessaria para rodar a aplicacao shopping cart.

## Como rodar?

```
git clone --recurse-submodules git@github.com:evaldosantos/shopping-cart-infra.git
docker-compose up
docker exec -i shopping-cart-db sh -c "mongorestore --archive" < ./database.dump
```

## Porque submodules?
Porque nao? Usando submodules temos uma estrutura focada em cada uma das responsabilidades (front, back, infra), cada uma evoluindo a sua mandeira.
Dependendo do caso, permite builds independentes, com vendors independentes.
Usando uma outra estrutura, monorepo por exemplo usando yarn workspaces, nao me permitiria essa flexibilidade.

No caso em especial dessa aplicacao, como queria usar servicos gratuitos, optei por essa solucao usando submodules.