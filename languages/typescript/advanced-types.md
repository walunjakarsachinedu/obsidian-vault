### Advanced Types

```javascript
// Type aliases
type Employee = {
	readonly id: number,
	name: string,
	retire: (date: Date) => void
}

// Unions
type Weight = number | string;


type Draggable = { drag: () => void };
type Resizable = { resize: () => void };

// intersection
type Widget = Draggable & Resizable; // widget can use method in both types

// literal type
type Binary = 0 | 1;  type Rating = 'good' | 'best' | 4 | 5;


// optional property access operator
let widget: Widget | null | undefined; 
widget?.drag();

// optional property access operator
let widgets: Widget[] | null | undefined;
widget?.[0].drag(); // call only when object is not null

// optional function call operator
let func: (() => void) | null | undefined;
func?.(); // call only when object is not null

// Nullish Coaelscing Operator
let nullValue;
let value = nullValue ?? "default";

// Type Assertion
let phone = document.getElementById('phone') as HTMLInputElement;
let another = <HTMLInputElement>document.getElementById('phone');

let unknownType: unknown; // forces us to perform type checking before calling any methods & it should preferred over "any"

```
