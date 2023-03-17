### Observable
It is like stream which return more than one value asynchronously.
Observable are lazy, it will not return value unless someone subscribe to it.
          
We can use "`.pipe`" method of `Observable` to process response data in specific way. 
To "`.pipe`" we can pass
- catchError: use handle error while providing value
	- throwError: function return `Observable` with error.
 - map: use to map value provided by stream to some another value.
 - switchMap: allow you to switch to new observable and cancel the previous one.
	 - it take value and return new observable


