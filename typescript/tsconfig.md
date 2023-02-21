### TSConfig
configuration for typescript compiler.


#### configuration
- target: version javascript typescript will generate
- module: type of module formate used
- rootDir: directory containing source files
- outDir: directory containing javascript files 
- removeComments: remove comments in generated javascript code
- noEmitOnError: instruct not to generate javascript file on error in typescript code.
- strictNullChecks: strictly about null values
   
- debugging:
	- sourceMap: map of typescript code to javascript code. (its value must be true for debugging)   
- noImplicitAny: when set to false typescript do not warn about the implicit `any` type 
    
