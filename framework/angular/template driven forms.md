### Forms in Angular
In angular, we two class to keep track of input & their validity
- `FormControl`: represent only one input field.
- `FormGroup`: respresent group of input field.    
- note:  By applying `ngModel, ngGroup` directives, angular will automatically create `FormControl, FormGroup` object correspondingly for us.
     
### Template driven forms
- `ngModel` directive is used for creating template driven forms. 
- It is required to set value of `name` attribute when `ngModel` directive is used.
- we can use template variable to get access to form controller, by setting its value to `ngModel` as `<input ngModel name='firstname' #template_var='ngModel'>`
- `errors`  is object provided by `ngModel` to access errors.
```typescript
<input ngModel name='firstname' #template_var='ngModel'>
<div *ngIf="name.errors?.['required']">value is required</div>
```
- angular automatically apply `ng-invalid` class to input field with invalid data.

>different validation contraints on input field: input, minlength, maxlength, pattern
      
- `ngForm` directive is automatically applied by angular to form 
	- using `value` property we can get access all value under that form
	- it provide `ngSubmit` to handle submit event
- `ngModelGroup` is use to group multiple `ngModel` into single group. e.g, name & contact field can be group under contact group like: contact: {name: "name", contact: "contact"}
	- to use this directive, enclose multiple input field under single div & apply `ngModelGroup` directive to that div.


>Using template variable we can reference `ngModel, ngForm, ngModelGroup`

