### Directives
it is use to modify the structure of the DOM

**Structure Directive**: It is use to modify structure of DOM.
- `ngIf` : conditionally include element in dom.   (`hidden` property just hide element, it doesn't remove element from dom)
- `ngSwitch`: include element based on switch case
- `ngFor`: use to loop through list & create html element for each item in list
	- angular will rebuild DOM if content is modified or if content location changes.
	- we can disable rebuild when memory location changes by setting the value of `trackBy` function in `*ngFor` directive. 
```html
<!-- ngIf -->
<div *ngIf="condition; then thenBlock else elseBlock"></div>
<ng-template #thenBlock></ng-template>
<ng-template #elseBlock></ng-template>

<!-- ngSwitch -->
<div [ngSwitch]="'value'">
	<div *ngSwitchCase="'1'">case with value 1</div>
	<div *ngSwitchCase="'2'">case with value 2</div>
	<div *ngSwitchDefault>Otherwise</div>
</div>
```


> Leading asterisk "`*`" in directive tell angular to rewrite block using `ng-template` element.

**Attribute Directive**: It is use to modify the attribute of DOM.
- `ngClass`: allow conditionally including multiple classes with simpler syntax
	- key is class surrou nded with single quote
```html
<div [ngClass]="{'class_name':expression,}">content</div>
```


#### Creating Custom Directive 
Use to provide more control over DOM element.
We can pass data to directive using input property

```typescript
@Directive({selector: '[appInputFormat]'})
export class InputFormatDirective {
	@Input('appInputFormat') format: any;
	@HostListener('blur') onBlur() { 
		let value: string = this.el.nativeElement.value;
		if(this.format == 'lowercase') {
		  this.el.nativeElement.value = value.toLowerCase();
		}
		else {
		  this.el.nativeElement.value = value.toUpperCase();
		}
	}
	constructor(private el: ElementRef) {} // el is reference to hosting element
}
```
- best practice: we prefix directive name so that they do not clash with other directive




