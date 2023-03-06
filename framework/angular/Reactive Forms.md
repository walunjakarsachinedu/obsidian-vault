### Reactive Forms
we explicitly create associate `FormControl, FormGroup` to template.
In reactive forms, 
- we first create instance of `FormGroup` in component, 
	- we can pass `Validators` inside constructor of `FormGroup` as 2nd argument.
- then use `formGroup` directive to link this instance to template 
- `formControlName` is use to link individual input by setting its value to key in form control
```html
<!-- template -->
<div [formGroup]='form'>
	<input formControlName='username'>
</div>
```
```typescript
export class SignupFormComponent {
  form = new FormGroup({
    username: new FormControl('', [Validators.required,
     Validators.minLength(3), UsernameValidators.cannotContainSpace]),
    password: new FormControl('', Validators.required),
  });
}
```


#### customValidator:
- it is just a function which take `AbstractControl` as argument return Object incase of error  else `null`
```typescript
cannotContainSpace(control: AbstractControl) {
	if((control.value as string).indexOf(' ') >= 0) 
		return { "cannotContainSpace": true };
	return null;
}
```