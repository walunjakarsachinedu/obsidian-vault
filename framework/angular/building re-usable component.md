### Building Re-usable Component

#### Component API
- Input property: Pass state to component.
	- add decorator `@Input([alias-name])` to mark member as input property.
	- `alias-name` allow us to change member name without modifying template of component 
- Output property: Raise event from component.
	- create event emitter as :  `@Output([alias-name]) change = new EventEmitter();` 
	- call `change.emit([optionalData])` to raise an event.
	- function with argument `$event` is use to get data provided by event.
 - Content property: Select injection & show content in proper format.
	 - use `ng-content` with `selector` to specify injection point for content in component  
	 - when defining content specify proper selector
	 - it is better use `ng-container` over `div` to specifying selector
		 - With `ng-container` angular will just take content & use it to replace injection point. whereas `div` replace it with content with selector
	 - note: you don't need a selector if you have only one ng-content

#### Applying Styles
- using `styleUrls` in component decorator
- directly define style in `styles` argument of component decorator
- using inline style in html code  as `<style></style>.
  
>Angular create scope for style, so that they will not leak outside of component template.  By default, it emulate shadow dom, using trick of template variable, but we can change it using `encapsulation` argument in component decorator. 