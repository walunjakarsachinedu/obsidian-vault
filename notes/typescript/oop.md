
creating class:
```typescript
class Person {
	firstName: string;
	secondName: string;
	constructor(firstName: string, lastName: string) {
		this.firstName = firstName;
		this.secondName = lastName;
	}
}
```

createing instance: `let person: Person = Person("sachin", "walunjakar");`
checking type of user defined class: `if(person instanceOf Person) {}`
	`typeof` can be use for premitive types.
 `readonly` keyword: use this keyword at time of property definition to make it readonly.
`override` keyword: helps to make sure that method is overrided properly with correct signature. 
