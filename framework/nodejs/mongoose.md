### Mongoose
Library use for accessing **mongodb** database.  
It has similar syntax to **mongosh commands**.

#### Connecting to database:
command: `mongoose.connect('url/to/database/databaseName')`

#### Storing documents: (steps)
1. create schema    `const schema = mongoose.Schema({name: String})`
2. compile schema to model    `const model = mongoose.model('Model', schema)`
3. use model to create data     `const data = new Model({name: 'sachin'})`
4. call save method to save data in database    `data.save()`

#### Schema 
-  **Types**: 
	`String, Number, Date, Buffer, Boolean, ObjectID`  
	Array type: wrap schema type with "[]" brackets. e.g., `[String]`
 
 >  Important note:  data & method should be define on schema before it can use for creating model. If method is define after creating model, we can't access them using model.

- **Validation**:
	- built-in validation: `required, enum, minlength, maxlength, match, min, max
	- custom validation: `validate.validator`  it take function as value
	- when validation failed, error object is thrown & this error object has `errors` property contain error for each field, and for each error `error.message` gives description of error.  
         
- **Schema Type**: 
	- `set, get` use to set custom setter and getter for fields
	- For string `lowercase, uppercase, trim`

	
#### Updating Document:
- Query first : first we query document then perform update  
	- use any `find` to get objects then perform update and call save method on it.
	- In short, Directly updating object get using `find` method & calling `save()` method.
- Update first : direct update document    `model.update(<filterObject>, <updateObject>)`
- **Updating specific element in array containing embedded document**
``` javascript
  const course = await Course.updateOne({ _id: courseId}, 
    {$set: { 'author.$[i].name': "Mosh Hamedani" }},
    {arrayFilters: [{"i._id": "63ddd5ab88916f1e5de74457"}]}
  );
```
	

### Relationship among objects:
- Using Reference: storing reference of document (stored in other collection)
	- schema:   `const courseSchema = mongoose.Schema({name: String, author: {type: mongoose.Schema.Types.ObjectId, ref: 'Author'}})`
	- use populate method on find to replace reference with actual object `.populate('author')` 
	- using reference more consistent but slow query
- Using Embedded Document: directly storing document instead of just reference
	- schema: `const courseSchema = mongoose.Schema({name: String, author: mongoose.Schema.Types.ObjectId`
	- it just like any other document, but stored in context of enclosing document
	- using embedded document less consistent but fast query
 - Using Hybrid Approach: storing only required field of inner document
	 - consistent & fast query
	 - use case: showing orders


> **Importance Notes:**  
>	In mongoose, any operation using field only works when 
> 		1. field is present in schemas.
		   2. type of field in schema matches type of data in mongodb database.
	  To avoid unexpected behaviour, make sure type of `_id` is `ObjectId`


### Transaction:



### ObjectId:
- unique id use to identify document in collection
- It contains 24 alphanumeric character taking 12 bytes of memory:
	- 4 bytes: timestamp
	- 3 bytes: machien identifier
	- 2 bytes: process identifier
	- 3 bytes: counter
 - ObjectId is generated by mongodb driver & not by mongodb itself.
 - In nodejs, mongoose generate ObjectId. It is assigned at time when we created instance of model. 
 - To manually create objectid use:   `const id = new mongoose.Types.ObjectId();`
 - methods:  `getTimestamp, isValid`


#### Tricks : 
- for `sort` and `select` function we can pass fields separated by space in string
   - e.g., `sort('name -price')` this sort name in asc & then name in desc
   - e.g., `select('name -price')` this select name & not select price field
	
