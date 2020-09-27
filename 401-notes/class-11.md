## Why you should use BCrypt to hash passwords FROM https://medium.com/@danboterhoven/why-you-should-use-bcrypt-to-hash-passwords-af330100b861
- Plain text passwords - only letters (often used for other logins)
- One way hash 
  - server does not store plain text PW to authenticate user 
  - hashing algorithm applied - slightly more secure but there are ways around (guessing until a password is matched)
- 'salting' the password - adds a long string of bytes to the password 
  - if a hacker guesses hash, it's difficult to guess the salt string
  - NOTE: if someone has access to the source code, then your 'salt' string passwords are still easily found
- random 'salt' for each user - makes it much harder to guess password because a 'salt' string is given to each user. Not impossible to get password, just need more time needed to get passwords for many users. 
- BCrypt Solution Hashing function - Designed by Neils Provos and David Mazieres in 1999. 
  - Based on Blowfish block cipher - adaptive hash function 
  - Key Factor: great protection against rainbow table (a password cracking type)
  - Use BCrypt for sensitive data 

## Hashing in Action: Understanding bcrypt FROM https://auth0.com/blog/hashing-in-action-understanding-bcrypt/
- Ideal authentication: integrating both hashing and salting 
- Cryptographic functions: SHA2 family, SHA-3 family -- these are fash which makes them less safe. Hashing speed and security. 
- Need slow hashing that is adaptive so it runs slower over time as hardware gets faster 
- Must be aware of hardware development and password length 
- Bcrypt uses salt, 128-bit salt and 192-bit magic value 
- eksblowfish - expensive key schedule Blowfish
- Key Setup (only done once for each key used): 
  - Setup phase: internal state is initialized 
    - If user selects a short or bad password, bcrypt stretches it into a longer/better password. This is called key stretching. This is all key strengthening which slows attackers down. 
  - Operational phase: add ciphertext, encrypt plain text, or decrypt
    - Magic value, encrypted 64 times using eksblowfish.

- Bcrypt's 3 core properties 
  - pre-image resistant 
  - large salt space 
  - adaptable cost 

- Cost (aka work factor) - want it as slow as possible without impacting user experience. 
- Best to use 2FA and MFA for if password is cracked 

- Two Techniques (new hash generated each time function is run)
  - 1: generate salt and hash in separate function calls 
  - 2: auto-generate a salt and hash 
  - use `.compare(plainTextPassword1, hash)` to check password matches the hash 

## Token Storage FROM https://auth0.com/docs/tokens/token-storage
- SPA Single Page Application
- Be careful with SPAs that make API calls. Must make sure to protect tokens and sensitive data from cross-site scripting (XSS) or malicious JS.

- Possibly needs for authentication 
  - accessing a page
  - accessing an API route
  - when app makes an API call to an outside API on behalf of the user

- If a server is available, app can use AuthO to to create a session to handle authentication.
  - User redirected to AuthO 
  - After successful sign-in, user is redirected back to app
  - Complete code exchange. AuthO retrieves the user's id_token and access_token and they are stored in memory. 

- Traditional Web App Scenarios 
  - App *doesn't require* API call --> only need ID token. Don't need to store token. Only need to validate token and get data.
  - App *needs* to make API call on behalf of user --> need access tokens and refresh tokens (optional) --> stored in server-side or session cookie. 

- Native/Mobile App Scenarios 
  - Token should be stored in secure storage and there should be limited access. 
    - Android - KeyStorage 
    - iOS - KeyChain 

- Single-Page App Scenarios 
  - AuthO SPA SDK - used for handling token storage, session management, and other sensitive details 
  - SPA backend can handle API calls -- handle tokens server-side.
  - SPA backend cannot handle API calls -- tokens stored in SPA backend. Need to secure the token transfer (from backend to SPA). 
  - SPA - no backend server - SPA requests new tokens when user logs in and stores them to memory (no persistence). SPA uses in-memory copy of the token for API calls. 

- Browser in-memory scenarios 
  - store tokens in browser memory - most secure. Uses Web Workers.
  - JavaScript closures (alternate to Web Workers)

- Browser Local Storage Scenarios
  - Tokens in browser local storage with persistence across tabs and refreshes makes user vulnerable to XSS attack. Tokens can be retrieve from local storage. Minimize security risks by lowering expiration time.  