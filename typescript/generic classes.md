### Generic Classes


creating generic classes:
```typescript
class Pair<K, V> {
    constructor(public key: K, public value: V) {}
}
/// generic type inferred
let pair = new Pair('name', 'sachin');
/// generic type specified explicitly
let pair1 = new Pair<string, number>('id', 10);
```
  
> In many cases typescript compiler automatically infer the type generic class based on value provided
   
generic function:
```typescript
function wrapInArray<T>(value: T) : T[] { 
	return [value]; 
}
wrapInArray("sachin"); //output: [ "sachin" ]
```
   
generic interface:
```typescript
interface Result<T> {
	data: T | null
	error: string | null
}
```
   
generic constraints: it restricts type, generic parameter can have.
```typescript
function echo<T extends string|number>(value: T) {
	console.log(value);
}
// constraints to specific object
function printPerson<T extends {name: string}>(value: T) {
	console.log(value);
}
```
  
extending generic classes:
- we can extend generic class in 3 ways:
	1. keep base class generic
	2. fix generic type parameter
	3. restrict generic type parameter
```typescript
class Product {}
class Store<T> {}
class CompressibleStore<T> extends Store<T> {} // keep generic base class
class ProductStore extends Store<Product> {} // Fix generic type parameter
class AnotherProductStore<T extends Product>  extends Store<Product> {} // restrict generic type parameter
```

`keyof` operator:  it returns union of property on given type
```typescript
class Product { constructor(public name: string, public price: number) {} }
let indexType: keyof Product;  // 'name'|'price' union type
```

Type mapping: use to create new type based on existing.
```typescript
interface Product {
	name: string;
	price: number;
}

type ReadOnly<T> = {
	[K in keyof T]: T[K]
}
type Nullable<T> = {
	[K in keyof T]: T[K] | null
}
```

>typescript provide built-in utility types for type mapping. [click for more info.](https://www.typescriptlang.org/docs/handbook/utility-types.html)