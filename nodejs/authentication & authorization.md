### Authentication
It is process of identifying if the user is who they claim they are.
It is login, where we send username & password to server & server  authenticates us.

- We don't store password as simple string in database, we first hash the password then store. So, it will be not visible to anyone. 
- To provide additional security, we add salt to password before hashing.
	- salt is also stored in hash. 
	- In validation, salt is use to rehash plain text password to compair with original password.
- To hash password, "bcrypt" library is used.
``` javascript
// hashing password
const salt = await bcrypt.genSalt(10);
const hashed = await bcrypt.hash(password, salt);
// validating password
bool a = await bcrypt.compare(entered_password, hashed_password);
```


### Authorization
It is process of determining if the user has right permission to perform given operation.
After authentication, token is send back to client which determine level of access to resource or in simple words determine "authorization".

#### JWT
It is **json web token** send by server to client after login. 
It is send with every req to server used as license or **identity of user.**
Its payload is use to authorize the user.
**jsonwebtoken** library is use for generating JWT.
```javascript
// creating token
const token = jwt.sign({_id: user._id}, 'jwtPrivateKey');
// verifying token
const payload = jwt.sign(token, 'jwtPrivateKey')
```

- It can be divided into three parts:
	1. header: contains algorithm used & type of token.
	2. payload: contains public info about user.
	3. signature: contains digital signature of user. It add **security to jwt.**
- Digital signature is created using contents of token  along with private/secret key. 
- Private key is only available on server. 
- If content of JWT tempared then digital signature become invalid.

#### Protecting Routes
Calling middleware before route which will verifying token & pass control to router only if token is correct.
syntax: `app.post('/', [middleware1, middleware2, ...], (req, res) {});` 
where middleware1, middleware2 route verify token & perform authorization.


### Logging out User
This feature should be implemented on client side because on server we are not storing any token or login data. 
User can log out at client side by deleting token from local storage.