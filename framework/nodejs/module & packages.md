### Module
It is javascript file containing similar object grouped together
object in module are private by default in module
export object in module: `exports.variable_name = object_name`
every module is wrap inside **Wrapper Function** which provide global looking variable like `require`, `exports`, `process.env` which specific to each module

> Important: In JavaScript, modules are typically implemented using a single instance pattern, meaning that only one instance of a module is loaded in memory and shared across all imports of that module.

>note: following import, export described using "`ES6 syntax`".

export: 
- default export: `export default Movie; // Movie is any object`
	- note: You can't have more than one default export
- named export: `export {value};`
- mixed export: use both statement to do mixed export
- export with alias name: `export {value as newValue};`
import:
- default import: `import Movie from './path/movie.js';`
- named import: `import {value} from './path/value.js'`;
	- note: for named import, import name should match name of variable exported.
- mixed import: `import Movie, {value} from './path/file.js';`

>  note: if same value **exported** using both **default & named** then it can be **imported** using **default & named** import ways.


### package.json
It stores meta data out project (like name, dependencies, dev-dependencies)

#### NPM Commands:
install all packages in package.json: `npm install`
install : `npm install package`   or `npm i package`
uninstall: `npm uninstall package`  or `npm un package`
list: `npm list`   (to see only project dependencies and not subdependencies use `--depth=0` flag) 
list: `npm list --outdated`
update: `npm update`   (use `npm-check-updates` package for installing latest version)
install dev-dependencies: `npm i package --save-dev`
install specific version: `npm install package@5.0.0`
view specific package: `npm view package [property]`

> Note: To make changes globally use `-g` flag.


#### Useful package
**nodemon**: automatically rebuild project based on changes made in file
**jshint**: check commonly made mistakes and potential bugs`
**underscore**: collection of useful function
**morgan**: logging (middleware)

**joi**: powerful tool for validating json data
- give useful error message for invalid data
- use to define a schema for data and validate the data against the schema. 
- e.g., `const schema = Joi.object({name: Joi.string().min(3).required()})`
- `const { error } = schema.validate(req.body)`    use to get error
- `error.details[0].message`    give error message

**config**: use to set configuration for node project
- select configuration based on type of environment determined by environment variable `NODE_ENV`
- we can use `config.get(path.to.field)` to get configuration.
- it looks for configuration in folder "`./config`"
- config package use special file : "custom-environment-variables.json" 
	  - for storing mapping from key => environment variable values
	  - this file can be use for storing password or secret info and set through environment variable
- if `NODE_ENV==filename`  then it load configuration from "config/filename.json" 

**debug**: use to show debug message based on environment-variable `DEBUG`
- Use for creating debugger under custom namespace
- Only show output of those debugger whose namepsace stored in `DEBUG` environment variable
- e.g., "`export DEBUG=app*,dev`"  displays output only from debug function whose namespaces equal to "dev" or starting with "app" 

**pug**: it is templating engine, use to return html in response.
- `app.render('pugfile', map)` function sends a `pubfile` in response, where the `pugfile` loaded with values from `map`."
- `app.set("view engine", "pug")` for pug as default engine
- `app.set("views", "/path/to/pug/files")` use for specifying path to pub file (default is `./views`)

lodash: popular library contains useful functions for object & array.
- e.g., for object, it provide `pick` to create object from existing one with specified property

bcrypt: use for hashing passwords.
jsonwebtoken: use for generating jsonwebtoken.

winston: library use for logging. [click for more details](handling%20errors.md#winston)
