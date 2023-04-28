#### ng-template
- it is angular directive which doesn't render on its own
- used in conjuction with ngIf, ngFor & ngSwitch directive
- use "template input variable" to pass value from component to ng-template. 
-  using template input variable e.g., 
```html
<ng-template #blogTemplate let-head="head" let-body="body">
	<h2>{{head}}</h2>
	<p>{{body}}</p>
</ng-template>

<div *ngFor="let blog of blogs">
	<ng-container
		[ngTemplateOutlet]="blogTemplate"
		[ngTemplateOutletContext]='{head: blog.head, body: blog.content}'
	></ng-container>
</div>
```
- syntax for "template input variable" => `let-var="key_name"`
	- `key_name` is name of key in object passed to `ngTemplateOutletContext`

