## User Modeling - FROM on Canvas Reading 
- model sensitive data about users 
- developers responsibility to safely store the data provided by the user (emails, usernames, addresses, etc.), like in a database with a password and/or behind a firewall.
- passwords should be encrypted with hashing algorithms BEFORE being stored, so people (including developers) don't have access to the real password. 
- sensitive data should never be sent to client apps
- if app needs users to access personal info, create a second Profile Model and limit access to it. 

## Cryptography 
- encoding messages
- decoding messages - the secret key to read the encoded message
- cryptoanalysis - studying how to decode encoded/encrypted messages without the secret key

## Hash Algorithms 
- Cryptographic Hash Algorithm - takes data and creates a hash that is difficult to reverse (NOTE: If the same data is passed, the same hash is created).
- User Model -- hash password can be stored when the user signs up and when the user logs in again with the password, the hash is sent.
- If the hashed password and initial hashed password match, then the user is authenticated. 

## Cypher Algorithms
- Cryptographic Cypher Algorithm takes data and a key and makes it encrypted data. Process can be reversed by using the same key. 

## Basic Authorization 
- Basic Authorization - often used to send username and password with HTTP request. They are joined joined using base64. The 'Basic' string is set in the Authorization header. 
- Sever can decode Basic Authorization header to get the username and password
- Base64 encoding is not a form of encryption. Client and server must use HTTPS to protect the username and password that is traveling across the network. 
- Using base64 
  - `let base64 = require('base-64')` at the top of the page
  - `let string = 'username:password'` 
  - `let encode = base64.encode(string)` to encode the string to something like this c23w4890svcsjdifjsdlj
  - `let decode = base64.decode(string)` to decode it back to username:password.

## Basic access authentication FROM https://en.wikipedia.org/wiki/Basic_access_authentication
- BA uses fields in the HTTP header
- `Authorization: Basic <credentials>`
- Does not use cookies, session identifiers, or login pages
- Does not provide confidentiality for the credentials

## JSON Web Token FROM https://jwt.io/introduction/
- JWT can be encrypted 
- Signed tokens verify 
- Encrypted tokens hide
- JWT Uses: 
  - Authorization 
  - Informational Exchange 
- JWT Structure 
  - Header - two parts
  - Payload - contains claims - registered claims, public claims, private claims
    - Only put secret info in encrypted JWT payload or headers
  - Signature 
- How 
  - Authentication - User signs in - JWT returned
  - Using: `Authorization: Bearer <token>`

## Authentication Cheat Sheet FROM https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html
- Tips for safely authenticating 
- Common attacks
  - Brute force - testing many passwords on a single account
  - Credential stuffing - testing credentials from another site
  - Password spraying - testing a weak password on many different accounts
- MFA (Multi-factor authentication) - use when possible 
- Lock out after too many attempts 
- Captcha 
- security questions and words 
- Monitoring logins
- Authentication protocols  

## Bcrypt FROM https://www.npmjs.com/package/bcrypt
- Install to use `npm install bcrypt`
- async recommended 
- require bcrypt `const bcrypt = require('bcrypt');`
- Hash a password - 
  - Option 1: Generate a salt and hash using separate function calls 
  - Option 2: auto generate salt and hash
- Check password - True / false compare `bcrypt.compare(...)`