### Consuming HTTP Services
Angular provide `HTTP` object from `HTTPModule`.        
Http object can be use in component using dependencies injection & by registering `HTTPModule` in imports.
    
Http provide `get, put, post, delete`  methods.

>Best practice: make service class to encapsulate logic for making http request & handling response  

	 
### Error Handling
types of error:
- unexpected: service is offline, network is down, unhandled exceptions
- expected: "not found" errors (404), "bad request" errors (400)
         
syntax for handling error:
```typescript

http.get(url).subscribe({
	// callback for successful request
	"next": response => {console.log(response)},
	// callback for unsuccessful resquest
	"error": error => {console.log(error)},
});

// another more cleaner & maintaining syntax
http.get(url).pipe(catchError(handleError));
handleError(error: Response) => { return throwError(() => CustomError()); } 
class AppError {} // base class for all application errors
class CustomError extends AppError {}
```
            
note: we can use "`.pipe`" method of `Observable` to process response data in specific way.   
           
Best practice in error handling: 
 - in service, always try to return application specific user defined custom error.
	 - This enables separation of concerns. Allow application to not directly work with response object which is return by service.
	 - when defining custom error, include original error in it.
 - in service use single function to encapsulate logic for error handling
                          
Types of updates:
- Optimistics: we change ui immediately before sending request, if request is unsuccessful then we revert those ui changes
- Peimmistics: we first make request after request is successful then only we make changes in ui
                             
Observable vs Promise: Observable are lazy, it will not make request unless someone subscribe to it whereas Promise are eager.
