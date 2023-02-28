### Building Re-usable Component

#### Component API
- Input property: Pass state to component.
	- add decorator `@Input([alias-name])` to mark member as input property.
	- `alias-name` allow us to change member name without modifying template of component 
- Output property: Raise event from component.
	- create event emitter as :  `@Output([alias-name]) change = new EventEmitter();` 
	- call `change.emit([optionalData])` to raise an event.
	- function with argument `$event` is use to get data provided by event.

#### Applying Styles
- using `styleUrls` in component decorator
- directly define style in `styles` argument of component decorator
- using inline style in html code  as `<style></style>`