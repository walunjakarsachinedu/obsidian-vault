**component**: encapsulate data, html template, logic
- similer to widget
- real world app has tree of components
- whenever angular sees selector of component it will render template of component
    
**module**: container for group of related components 
- when module become very big we may need to split that module in sub-module
    
**Template**: we can use value class member  inside template through interpolation
- if value of member changes angular will automatically re-render DOM.
- syntax use for templating is : `{{ }}`
- interpolation in template is further translated into **property binding**
   
**Dependency injection**: 
- when dependency is registered as provider in module then angular will create single instance of that class for entire module. (singleton pattern)

