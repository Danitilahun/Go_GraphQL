Do the stuff below to initialize your project

Get gql gen for your project go get github.com/99designs/gqlgen

Add gqlgen to tools.go printf '// +build tools\npackage tools\nimport \_ "github.com/99designs/gqlgen"' | gofmt > tools.go

Get all the dependencies go mod tidy

Initialize your project go run github.com/99designs/gqlgen init

After you've written the graphql schema, run this - go run github.com/99designs/gqlgen generate

After you've built the project, these are the queries to interact with the API -

Get All Jobs
query GetAllJobs{ jobs{ \_id title description company url } }

=======================

Create Job
mutation CreateJobListing($input: CreateJobListingInput!){ createJobListing(input:$input){ \_id title description company url } }

{
"input": {
"title": "Junior Software Engineer",
"description": "Join an innovative team creating groundbreaking software solutions. Exciting opportunities for growth!",
"company": "TechCorp",
"url": "www.techcorp.com/careers"
}
}
=========================

Get Job By Id
query GetJob($id: ID!){ job(id:$id){ \_id title description url company } }

{ "id": "use the id you get" }

=========================

Update Job By Id
mutation UpdateJob($id: ID!,$input: UpdateJobListingInput!) { updateJobListing(id:$id,input:$input){ title description \_id company url } }

{ "id": "use the id you get", "input": { "title": "Senior Software Engineer" } }

=================================

Delete Job By Id
mutation DeleteQuery($id: ID!) { deleteJobListing(id:$id){ deletedJobId } }

{ "id": "use the id you get" }
