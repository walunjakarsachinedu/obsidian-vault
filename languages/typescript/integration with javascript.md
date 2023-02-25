compiler option: "allowJs" should enable to include javascript in compilation of typescript
    
     
ways to provide type information of javascript code:      
1. using JSDoc: special type of comment add to javascript code
```typescript
/**
 * 
 * @param {number} income 
 * @returns 
 */
export function calculateTax(income) {
    return 0.3 * income;
}
```
   
2. using declaration files:  it is a file with name same as original js file but with extension `d.ts`
	- with this approach if feature is not describe in declaration file, then that feature become invisible to compiler
```javascript
// tax.js
export function calculateTax(income) { return 0.3 * income }
```
```typescript
// tax.d.ts
export declare function calculateTax(income: number): number;
```
