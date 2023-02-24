### module  
It is just a javascript file.   
benefit of modularity: **maintainability, reuse, abstract**  
  
syntax for define module are known as **module format**  
popular module format are: **CommonJS**, **ES6 Modules**, AMD, UMD  

>Basic **rule of modularity**: Thing that are highlly related should go together.

CommonJS:
- exporting object: 
	- named: `module.exports.variable = variable;`
	- named with alias: `module.exports.aliasName = variable;`
	- default export: `module.exports = variable;`
 - importing object: 
	 - named object: `const {ObjectName} = require('/path/to/module.js');`
	 - named object with alias: `const {ObjectName : aliasName} = require('/path/to/module.js');`
	 - default export: `const ObjectName = require('/path/to/module.js';);`

ES6 Modules:
- exporting object: 
	- named: `export {Object};`
	- named with alias: `export {Object as aliasName};`
	- default export: `export default Object;`
 - importing object: 
	 - named object: `import {ObjectName} from '/path/to/module.js';`
	 - named object with alias: `import {ObjectName as aliasName} from '/path/to/module.js';`
	 - default export: `import ObjectName from '/path/to/module.js';`
	  
        
	
ES6 Tooling:
- when using modern javascript we need two kind of tools:
	- transpiler = translator + compiler.     e.g., Babel
	   - using babel:
		 - install package: babel-cli, babel-core, babel-preset-env
		 - command: `babel --presets env index.js -o build/index.js`
		     
	-  bundler = compile all .js files into single .js file.  e.g., Webpack
		- using webpack:
			- install package: `npm i -g webpack-cli`
			- run command: `webpack-cli init`
			- command to bundle file: `npm run build`
			- to add watcher, add flag `-w` to webpack > build > script > package.json
			   
   