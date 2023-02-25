### Express
It is framework for creating restful web api.  
Create express app: `const app = express();`  
To listen on particular port: `app.listen(3000, callbackOnStartedListening)`  
Handling get request: `app.get('/', (req, res) => {})`   
- similarly we can handle requests like put, post, delete     
   
req: provide info about request  
- `req.params` give access to url parameters  ("`/courses/:id`" in this url "id" is url parameter )  
- `req.query` give access to url query parameters ("`/courses/?sort=asc`"  in this is query parameters)
- `req.body` give access to request body    
    
res: provide response to client  
- `res.send()` send response
- `res.status({http-status})` set status of response    
	
dynamically setting port for api: `const port = process.env.port || 3000;`  

#### Middle-ware 
Accept request of client & either **responds to client or passes control** to another middle ware.  
Calling middle-ware function: `app.use(express.json()`   
Useful middleware: 
- express.json()
- express.route()
- express.urlencoded()    // parses query parameters
- express.static('dir_name')    // give access to static files in "`dir_name`"
- helmet   // helps to secure express application
- morgan // use for performing logging on both console and files  (use for debugging)  
	
Note: middle-ware **impact performance**, so use only when it is required.
	
	
### Router
A router in Express is an isolated instance of middleware and routes that can be mounted on a specific path within the main Express application.   
It provides a way to modularize your application and define separate routes for different parts of your app, making it easier to manage and maintain your code.  
- to create router use:    `express.Router()`


### Environment
It define configuration of node application. (like address of server, password)  
[config](module%20&%20packages.md#useful%20package) package is use to automatically load environment specific configuration   