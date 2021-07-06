# go-graphql

Este projeto é destinado ao aprendizado do desenvolvimento de uma API utilizando o conceito de GraphQL.

Para a criação do server, foi utilizada a dependência [gqlgen](https://pkg.go.dev/github.com/99designs/gqlgen@v0.13.0). O modo de uso e os comandos necessários são bem explicativos em sua documentação, caso queira utilizar o mesmo em seu projeto.

Este projeto utilizou apenas três itens relacionados, sendo os seguintes:

- Category
- Course
- Chapter

~~~go
type Category struct {
	ID          string  `json:"id"`
	Name        string  `json:"name"`
	Description *string `json:"description"`
}

type Course struct {
	ID          string    `json:"id"`
	Name        string    `json:"name"`
	Description *string   `json:"description"`
	Category    *Category `json:"category"`
}

type Chapter struct {
	ID       string    `json:"id"`
	Name     string    `json:"name"`
	Course   *Course   `json:"course"`
	Category *Category `json:"category"`
}
~~~

A dependência [gqlgen](https://pkg.go.dev/github.com/99designs/gqlgen@v0.13.0) realiza a criação de toda a base de nosso server utilizando apenas o escrevemos em nosso arquivo `graph/schema.graphqls`, sendo o responsável por contar todas as nossas definições de estruturas que serão utilizadas para o [GraphQL](https://graphql.org/).

A aplicação não está realizando o uso de nenhuma base de dados para armazenar as informações. Como o objetivo é o estudo do [GraphQL](https://graphql.org/), foi realizado o armazenamento em um array na proprópria aplicação, para que podesse existir um armazenamento dos dados.