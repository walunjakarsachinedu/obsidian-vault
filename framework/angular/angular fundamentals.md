component: encapsulate data, html template, logic
- similer to widget
- real world app has tree of components
- whenever angular sees selector of component it will render template of component

module: container group of related components 
	- when module become very big we may need to split that module in sub-module


dependency injection: 
	when dependency is registered as provider in module then angular will create single instance of that class for entire module. (singleton pattern)
- command to create component: ng g s service_name