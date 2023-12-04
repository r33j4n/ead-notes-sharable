![[Pasted image 20231204090352.png]]


- **Definition:**
    
    > OAuth 2.0 is an authorization framework that enables secure third-party access to resources without exposing user credentials. It is widely used for granting applications access to APIs on behalf of users.
- **Key Components:**
    
    - **Resource Owner:** The user who owns the data and authorizes third-party access.
    - **Client:** The application requesting access to protected resources.
    - **Authorization Server:** Verifies the identity of the resource owner and issues access tokens.
    - **Resource Server:** Hosts the protected resources and responds to requests with access-controlled data.
- **Flow Types:**
    
    - **Authorization Code Flow:**
        
        - **Description:** Used by web and mobile apps, involves a series of redirects.
        - **Example:** A user logs into a social media app, granting it access to post on their behalf.
        - **Learning Tip:** Visualize the user granting permission through a series of redirects.
    - **Implicit Flow:**
        
        - **Description:** Designed for client-side applications, the access token is returned immediately.
        - **Example:** JavaScript-based applications accessing user data.
        - **Learning Tip:** Think of immediate access tokens for client-side interactions.
    - **Password Grant Type:**
        
        - **Description:** Resource owner's credentials are exchanged for an access token.
        - **Example:** Mobile apps where the client can securely store credentials.
        - **Learning Tip:** Imagine direct exchange of credentials for access.
    - **Client Credentials Grant Type:**
        
        - **Description:** Used when the client is the resource owner.
        - **Example:** A server accessing its own resources.
        - **Learning Tip:** Picture a server using its own credentials to access resources.
- **Access Token:**
    
    - **Definition:** A string representing the authorization granted to the client.
    - **Example:** A token allowing an application to post tweets on a user's behalf.
    - **Learning Tip:** Think of the access token as a key to access specific resources.
- **Refresh Token:**
    
    - **Definition:** A token used to obtain a new access token when the current one expires.
    - **Example:** A long-lived token allowing continuous access without reauthentication.
    - **Learning Tip:** Visualize the refresh token as a renewable access permit.

### Flow of 0Auth 2.0

> The Authorization Code Flow is commonly used for web and mobile applications. It involves a series of steps, including user redirection, to obtain an access token for accessing protected resources.

#### Steps:

1. **User Initiation:**
    
    - The user initiates an action that requires third-party access, such as logging into an application.
2. **Redirect to Authorization Server:**
    
    - The application redirects the user to the Authorization Server's authorization endpoint, including details like client ID and requested scopes.
    
    `GET /authorize? response_type=code& client_id=CLIENT_ID& redirect_uri=REDIRECT_URI& scope=SCOPE& state=STATE`
    
3. **User Authentication:**
    
    - The user authenticates with the Authorization Server and grants/denies permission for the requested scopes.
4. **Authorization Code Response:**
    
    - If the user grants permission, the Authorization Server responds with an authorization code.
    
    `GET /callback?code=AUTHORIZATION_CODE&state=STATE`
    
5. **Token Request:**
    
    - The application exchanges the authorization code for an access token by sending a token request to the token endpoint.
    
    `POST /token grant_type=authorization_code& code=AUTHORIZATION_CODE& redirect_uri=REDIRECT_URI& client_id=CLIENT_ID& client_secret=CLIENT_SECRET`
    
6. **Access Token Response:**
    
    - The Authorization Server responds with an access token and, optionally, a refresh token.
    
    `{   "access_token": "ACCESS_TOKEN",   "token_type": "Bearer",   "expires_in": 3600,   "refresh_token": "REFRESH_TOKEN" }`
    

#### Example:

1. **User Action:**
    
    - A user logs into a social media app and decides to allow a third-party app to post on their behalf.
2. **Redirection:**
    
    - The app redirects the user to the social media's authorization endpoint.
3. **User Authentication:**
    
    - The user logs in, granting permission to the third-party app.
4. **Authorization Code:**
    
    - The Authorization Server returns an authorization code.
5. **Token Exchange:**
    
    - The third-party app exchanges the code for an access token.
6. **Access Token Obtained:**
    
    - The app receives the access token, allowing it to post on behalf of the user.

> Visualize a user logging into a social media app, confirming access for a third-party app, and the subsequent exchange of authorization code for an access token. This mental walkthrough aids in recalling the Authorization Code Flow during your exam. Good luck!