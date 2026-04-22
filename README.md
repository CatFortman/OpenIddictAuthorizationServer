# OpenIddictAuthorizationServer

This project implements an OAuth2 Authorization Server using OpenIddict and the Authorization Code Flow.

It demonstrates how to issue authorization codes and access tokens, validate client applications, and manage secure authentication flows in a controlled environment.

## Prerequisites
- .NET SDK
- Basic understanding of OAuth2 concepts
- A client application configured to interact with the authorization server
- (Optional) Postman or a browser for testing authorization flows

## Overview

This project focuses on implementing a standards-based OAuth2 server using the Authorization Code Flow, which is the recommended flow for server-side applications.

The authorization server is responsible for:

- Authenticating users
- Issuing authorization codes
- Exchanging authorization codes for access tokens
- Validating client applications
- Enforcing scopes and redirect URI rules

## Key Concepts Covered
1. Authorization Code Flow
    - Secure exchange of authorization code for access token
    - Separation between front-channel (browser) and back-channel (server) communication
2. Client Authentication
    - Validating registered client applications
    - Enforcing redirect URI constraints
3. Token Issuance
    - Generating access tokens
    - Managing token lifetimes and scopes
4. Security Considerations
    - Preventing token leakage
    - Ensuring secure redirects
    - Validating incoming requests

## Project Structure
- Authorization endpoint
- Token endpoint
- Client configuration
- OpenIddict setup and pipeline configuration
 
## Running the Application

From the project directory:
```
dotnet restore
dotnet build
dotnet run
```
The server will start locally and expose endpoints for authorization and token exchange.

## Example Flow (Authorization Code)
1. Client redirects user to authorization endpoint
2. User authenticates
3. Authorization server redirects back with authorization code
4. Client exchanges code for access token
5. Client uses access token to access protected resources

## Notes / Best Practices
- Use Authorization Code Flow for:
    - Server-side applications
    - Applications requiring strong security
- Always validate:
    - Redirect URIs
    - Client identity
    - Requested scopes
- Never expose:
    - Client secrets
    - Access tokens in URLs
- In production:
    - Use HTTPS only
    - Store secrets securely (e.g., Azure Key Vault)
    - Implement proper user authentication and identity management