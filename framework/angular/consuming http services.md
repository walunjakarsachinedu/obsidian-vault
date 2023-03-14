### Consuming HTTP Services
Angular provide `HTTP` object from `HTTPModule`.        
Http object can be use in component using dependencies injection & by registering `HTTPModule` in imports.
    
Http provide `get, put, post, delete`  methods.

>Best practice: make service class to encapsulate logic for communicating with backend  

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

// or another and more cleaner, maintaining syntax
http.get(url).pipe(
  catchError(
    (error: Response) => { return throwError(() => CustomError()); }
  )
);
class AppError {} // base class for all application errors
class CustomError extends AppError {}
```

>Best practice in error handling: 
> - in service, always try to return application specific user defined custom error 
> - in service & component, use single function to encapsulate logic for error handling
