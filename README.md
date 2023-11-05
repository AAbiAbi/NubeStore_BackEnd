# NubeStore_BackEnd
## Overview
This Go application serves as a backend for an app store, handling app uploads, user authentication, and purchase transactions. It uses Stripe for payment processing, Elasticsearch for data storage and search, Google Cloud Storage (GCS) for file uploads, and JSON Web Tokens (JWT) for authentication.

## Features
- File upload handling.
- Search functionality through Elasticsearch.
- Checkout and payment processing with Stripe.
- User authentication with JWT.
- Cross-Origin Resource Sharing (CORS) support.

## Prerequisites
- Go programming language
- Stripe account for API keys
- Elasticsearch server
- Google Cloud Storage bucket
- JWT secret for token signing

- Install the necessary Go packages:

```bash

go get -u github.com/stripe/stripe-go/v74
go get -u github.com/gorilla/mux
go get -u github.com/olivere/elastic/v7
go get -u github.com/pborman/uuid
go get -u cloud.google.com/go/storage
go get -u github.com/form3tech-oss/jwt-go
go get -u github.com/auth0/go-jwt-middleware
go get -u github.com/gorilla/handlers

```
## Configuration
Stripe Configuration: Set your Stripe API keys in the constants.go file.
go
```go
package constants

const STRIPE_API_KEY = "your_stripe_api_key_here"
Elasticsearch Configuration: Define the connection details in backend/elasticsearch.go.
go
Copy code
package backend



const ELASTICSEARCH_URL = "http://localhost:9200"
```
## GCS Configuration: 
Set up your Google Cloud Storage bucket details in constants.go.
```go

const GCS_BUCKET = "your_gcs_bucket_name"
JWT Configuration: Specify your JWT signing key in service/jwt.go.
```
```go

const mySigningKey = "your_jwt_signing_key"
```
## Running the Server
From the project directory, run the following command to start the server:

```bash

go run main.go
The server will start listening for requests.
```

## Endpoints
POST /upload: Handles file uploads to Google Cloud Storage.
GET /search: Searches for apps in the Elasticsearch index.
POST /checkout: Initiates a Stripe checkout session.
POST /authenticate: Authenticates a user and returns a JWT.
## CORS Support
CORS is enabled by default. All responses include the necessary headers to support CORS requests from any origin.

## Testing
You can test the API endpoints using the provided Postman collections. Import the collections using the links provided in the lessons.

## Notes
Replace all placeholders like your_stripe_api_key_here with actual values from your Stripe account, GCS, and other services.

For more detailed information on each endpoint and how to use it, refer to the inline documentation within the code files.





