# Authorization/Authentication

### Review, Research, and Discussion

1. **What header(s) are used in authentication and authorization**

   There are many types of Authorization Request Headers. Some of them are mentioned below.

- Basic Auth
- Bearer Token
- API Key
- Digest Auth
- OAuth 2.0
- Hawk Authentication
- AWS Signature<br>

2. **What is safe to put into a JWT**

   When we want to signature a new Json web token; it is better to use a unique field from the user's record in the database along with a secret key that is not revealed to the public, it is also recommended to avoid using the password to generate the token, so we can use either the username or email as long as they are unique fields along with the secret key.

3. **How are JWTs validated**

   JWTs are signed so they can't be modified in transit. When an authorization server issues a token, it signs it using a key. When the client receives the ID token, the client validates the signature using a key as well

---

### Vocabulary Terms

| Term       | Defenition                                                                                                                                                                                                                                                                                                                                                          |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RBAC       | Role-based access control (RBAC) is a method of restricting resources access based on the roles of individual users within a website or web application. RBAC ensures users access only information they need to do their jobs and prevents them from accessing information that doesn't pertain to them.                                                           |
| User Roles | User Roles are permission sets that control access to areas and features within the Professional website or platform.                                                                                                                                                                                                                                               |
| JWT Token  | JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA. |

---

### 1- Which 3 things had you heard about previously and now have better clarity on?

- the Authentication and authorization process.
- JWT and tokens.
- Access Control List (ACL).

### 2- Which 3 things are you hoping to learn more about in the upcoming lecture/demo?

- OAuth
- best practices when using JWT.
- More about RBAC.

### 3- What are you most excited about trying to implement or see how it works?

- the singleton design pattern and whether it is related to the JWT single use tokens.
- Fully authenticated/secured API.
- Connecting the API with the front end.

---

### Resources

[Types of auth headers](https://www.loginradius.com/blog/async/everything-you-want-to-know-about-authorization-headers/)<br>
[The JWT documentation](https://jwt.io/introduction)<br>
