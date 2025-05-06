# APIs

## REST (Representational State Transfer):

Set of rules and conventions for building and interacting with web services using the following principles of REST.
- Statelessness: Each client request contains all information; server doesn't store client state between requests.
- Resources: Identified by URIs, representing entities like users, products, or data.
- Representation: Resources presented in formats (e.g., JSON, XML) easily processed by the client.
- Uniform Interface: Consistent interaction with resources through standard HTTP methods (GET, POST, PUT, DELETE).

### HTTP methods
- GET
- POST
- PUT
- DELETE

### HTTP Status codes
- 200 OK: Successful request.
- 201 Created: Resource successfully created as a result of the request.
- 204 No Content: Request successful, but no additional content to send in the response.
- 400 Bad Request: Invalid request syntax or parameters.
- 401 Unauthorized: Authentication is required and has failed.
- 403 Forbidden: Request is understood but access is refused.
- 404 Not Found: Requested resource is not found.
- 405 Method Not Allowed: The method used in the request is not allowed for the specified resource.
- 500 Internal Server Error: Generic server error; something went wrong on the server side.
- 503 Service Unavailable: Server is not ready to handle the request; typically temporary.

## SOAP

## GraphQL
