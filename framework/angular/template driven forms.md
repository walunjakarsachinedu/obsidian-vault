### Template driven forms
- `ngModel` directive is used for creating template driven forms. 
- It is required to set value of `name` attribute when `ngModel` directive is used.
- we can use template variable to get access to form conroller, by setting its value to `ngModel` as `<input ngModel name='firstname' #template_var='ngModel'>`
- `errors`  is object provided by `ngModel` to access errors.
```typescript
<input ngModel name='firstname' #template_var='ngModel'>
<div *ngIf="name.errors?.['required']">value is required</div>
```


>differen validation contraints on input field: input, minlength, maxlength, pattern