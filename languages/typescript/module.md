### module
module is just a file contains similar things

- exporting object: 
	- named: `export {Object};`
	- named with alias: `export {Object as aliasName};`
	- default export: `export default Object;`
 - importing object: 
	 - named object: `import {ObjectName} from '/path/to/module.js';`
	 - named object with alias: `import {ObjectName as aliasName} from '/path/to/module.js';`
	 - default import: `import ObjectName from '/path/to/module.js';`
	 - import all objects: `import * as alias from '/path/to/module.js';`

To use the ES6 module formate  set  `"module": "ES6"`  in `tsconfig.json` file
