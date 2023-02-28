### Building Re-usable Component

#### Component API
- Input property: Pass state to component.
	- add decorator `@Input([alias-name])` to mark member as input property.
	- `alias-name` allow us to change member name without modifying template of component 
- Output property: Raise event from component.
	- create event emitter as :  `@Output([alias-name]) change = new EventEmitter();` 
	- call `change.emit([optionalData])` to raise an event.
	- function with argument `$event` is use to get data provided by event.
 - Content property: Select content & replace with corresponding injection point.
	 - define content property: use `ng-content` with `selector` to specify injection point for content in component  
		  - **selector is any css selector**.
	 - using content property: when defining content specify proper selector based on, in which injection point content is to be insert.
	 - it is better use `ng-container` over `div` to specifying selector for content.
		 - With `ng-container` angular will just take content & use it to replace injection point. whereas `div` replace it with content with selector
	 - note: you don't need a selector if you have only one ng-content
	  e.g, 
	```html
	<!-- info.component.html -->
	<h1> <ng-content select=".title"> </h1>
	<p> <ng-content select=".body"> </p>

	<!-- app.component.html -->
	<info> 
		<div class="title">Title</div>
		<div class="body">This content of body...</div>
	</info>
```

#### Applying Styles
1. using `styleUrls` in component decorator 
2. directly define style in `styles` argument of component decorator 
3. using inline style in html code  as `<style></style>.
  
>Angular create scope for style, so that they will not leak outside of component template.  By default, it emulate shadow dom, using trick of template variable, but we can change it using `encapsulation` argument in component decorator. 