### Reactive Forms
we explicitly create & then associate `FormControl, FormGroup` to template.
In reactive forms, 
- we first create instance of `FormGroup` in component, 
- then use `formGroup` directive to link this instance to template 
- `formControlName` is use to link individual input by setting value of `formControlName` to key in form control
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

#### Validators
we can pass Validators & AsyncValidators inside constructor of `FormControl` as 2nd & 3rd argument respectively.    
We can apply validator to `FormControl, FormGroup, FormArray `

##### customValidator:
- it is just a function which take `AbstractControl` as argument return `ValidationErrors | null`
```typescript
cannotContainSpace(control: AbstractControl): ValidationErrors|null {
	if((control.value as string).indexOf(' ') >= 0) 
		return { "cannotContainSpace": true };
	return null;
}
```
- asyncValidator return `Promise<ValidationErrors | null>`
	- `FormControl` has `pending` property which return if atleast one async validator is running
     
>use `ngSubmit` directive for calling validators on form submit.
>we can set error using `setErrors` method of Form object.


### FormBuilder
use to create form with minimalist syntax
```typescript
export class NewComponent {
	form;
	constructor(fb: FormBuilder) {
		this.form = fb.group({
			name: ['', Validators.required],
			contact: fb.group({ // FormGroup
				email: [],  // FormControl
				phone: [], 
			}),
			topics: fb.array([]) // FormArray
		})
	}
}
```