<!-- Answers to the Short Answer Essay Questions go here -->

Q1.  Describe Middleware, Sessions (as we know them in express), bcrypt and JWT.

A:
  Middleware - functions that execute between an initiating function and its end result.  Middleware contributes intermediate operations towards the end result.

  Sessions - In our present context sessions refers to one of two types of authentication: Sessions-based and JWT-based (JASON Web Tokens).  Whereas JWT-based authentication is designed to work for stateless applications (as with mobile devices), sessions-based authentication utilizes server resources to manage access to the target application.  

  bcrypt - bcrypt is a library that provides password hashing functions to node/express applications.

  JWT - JWT (JASON Web Tokens) is standard for managing user access tokens.  The tokens are used by users as evidence of rights to specific claims to services provided by the API of a server/app.  (No relationship to J. Walter Thompson Worldwide ;-)  )

Q2.  What does bcrypt do in order to prevent attacks?

A:  bcrypt's primary method of defense is its use of an interation count that makes it progressively slower, requiring progressively increasing computational power to overcome its defenses using brute-force search attacks.

Q3.  What are the three parts of the JSON Web Token?

A: JWT's are comprised of two sections, JSON Data + a verifiable signature.  

The JSON Data section is typically not encrypted and has the following components:
  1) Header
  2) Payload
  
  The header has two subparts: a type delaration (i.e. JWT) and the hashing algorithm to use.  The header syntax is:
    { 
      "typ": "JWT",
      "alg": "HS256"
    }

The payload component carries the 'JWT Claims', which is the information to be transmitted as well as other information about the token.  Claims come in three flavors: Registered, Public and Private.  Claims are encoded.

The signature section consists of a hash of the header, the payload plus a secret (i.e. signature) known only to the server.