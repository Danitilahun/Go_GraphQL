Do the stuff below to initialize your project
Get gql gen for your project go get github.com/99designs/gqlgen
Add gqlgen to tools.go printf '// +build tools\npackage tools\nimport _ "github.com/99designs/gqlgen"' | gofmt > tools.go
Get all the dependencies go mod tidy
Initialize your project go run github.com/99designs/gqlgen init
After you've written the graphql schema, run this - go run github.com/99designs/gqlgen generate
After you've built the project, these are the queries to interact with the API -
