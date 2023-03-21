### displaying class field in dom
- interpolation : e.g, `<h2>{{title}}<h2>`,    where title is field in class.
	- showing `title` field in component class
- property binding : bind attribute to member of component class.
	- e.g., `<img [src]="imageUrl"/>`,    where imageUrl is field in class.
	- behind the scene, angular convert **interpolation to property binding**
	- binding is done in only one way from component  to dom
- class binding  : adding class based on member of component class.
	- e.g., `<button class="btn" [class.active]=isActive>Save<button>`
	- conditionally including `active` class based on `isActive` boolean variable.
- style binding: setting style value based on member of component class.
	- e.g., `<div [style.color]="isActive ? 'red': 'green'">Text</div>`
	 - setting color using `isActive` boolean variable.
- event binding: e.g, `button (click)="onSave($event)">Save</button>`
	- binding click event  with `onSave` method on class.
	- in value, we can write any expression.
	- `$event` contains info about event.
- event filtering: It allow to apply filter when handling event.
	 - e.g., `<input (keyup.enter)="onEnterPress()"/>` 
- template variable: It is variable referencing current element.
	- e.g., `<input #yourInput (key.enter)="onKeyUp(yourInput.value)"`
	- declaring variable `yourInput` which references input field.
 - two-way binding: It keep UI & properties of model in sync in both ways.
	 - syntax: `<input [(ngModel)]=email type="email" />`
	 - we can chane UI using property & property using UI.
 - pipes: It is use to format data.
	 - syntax apply pipes : `{{ value | pipe }}`
	 - build-in pipes : `uppercase, lowercase, decimal, currency, percent`
	 - creating custom pipes: 
		 - create class implementing `PipeTransfrom`  interface.
		 - register pipe inside module `declarations` arrays.
 
 >event bubbling: when any event raised, it is propogated up in DOM tree, unless any handler prevent further propogation. `$event.stopPropogation` is use to stop propogation.
	 

#### adding bootstrap:
- download bootstrap using : `npm install bootstrap`
- import `bootstrap.css` file in `src/style.css` 


