### Handling Error
error can occur in api do various reason like database goes down.

- error handling middleware: It is middleware use to handle unhandled error in request handling pipeline. It is present at the end of the request handling pipeline.
- library `express-async-errors` is use to wrap each router handler with try catch block with catch contain code to pass control to error handling middleware.
- type exception can occur in node application:
	1. exception occur in request handling pipeline.
	2. uncaught exception.
	3. unhandling rejection.


### Logging Error
Logging is essential in big application. With logging we can come back later and see what are the area of application we can improve. 

#### winston
- library use for logging.
- it can log message in different transports: **console, file, http, mongodb, http**
- transport is storage devices use by winston to store its output.
- logging can be done in different importance levels: **error, warn, info, http, verbose, debug, silly.**  To log at particular level we can use helper for each level.  e.g., `logger.warn(err);` 
- logger will output message only for level for which it is define for & for all above level.
- we configure transport to use be use for certain level. e.g., `winston.add(transports.Find({level: _level_, filename: 'all.log'});`
- we can define custom logger: 
```javascript
const winston = require('winston');

const customFormat = printf(({ level, message, label, timestamp }) => {
  return `${timestamp} [${label}] ${level}: ${message}`;
});

const logger = winston.createLogger({
  level: 'info', // only log message from level 'info' & above.
  format: combine(format.json(), format.colorize(), customFormat), // 
  transports: [ // error.log only use for level 'error'
    new winston.transports.File({ filename: 'error.log', level: 'error' }),
    new winston.transports.File({ filename: 'combined.log' }),
  ], // 'combine.log' is use for all logs.
});
```



#### uncaught exception & unhandled rejection
**uncaught exception** are exceptions which occur outside request processing pipeline.
When uncaught exception occur, its best to terminate process.
**unhandled rejection** are exception occur when promise end up in error state.

