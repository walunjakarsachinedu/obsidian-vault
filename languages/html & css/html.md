### html
It is markup language, use to give structure to web page.

> In this note, in tag formate `tag(attr1, attr2, ...)` value in round bracket represent attribute on tag.

#### html tags
- basic tags: `!doctype html, html, meta, head, body`  
- common tags:  `h1, p, b, i, br, hr, big, small, sub, sup`     
- formating page tags: `header, main, footer, nav, article, section, aside`  
- link: `a`(href, target)     
	- `target="_blank"` will open link in new tab
- image: `image`(src, alt, width, height)  
- video: `video`(src, controls, width, height, poster, autoplay, loop)  
- lists: `ul, ol, li` 
	- pass one of `['a', 'A', 1, i, 'I']` value to `type` attribute of  `ul` to get different ordered list 
- tables: `table, tr, td`(calspan), `th, caption, thead, tbody`
- tag for styling:
	- block level tag: `div`  
	- inline tag: `span`  
- input & forms: `input`( type, value, name), `textarea, form`  
	- pass one of `[text, password, email, range, file, checkbox, submit]` value to `type` attribute of `input` to get different input field.
	- value attribute represent default value for input field
- iFrame: `iframe`(src, width, height, frameborder).
	- use to display another website in our webpage.
- meta tags:
	- `meta`(charset)  
	- `meta`(name{description, author, keywords, viewport}, content)  
	- useful in search engine optimization
    
#### style & colors:
- use `style` attribute to set style for any tag in html.
- e.g., `<p style="color: green; background-color: red;">paragraph</p>`

#### general info:
- attributes: It allow us to pass addition info to tags
	- multiple values passed to attribute are separated by semicolon(`;`)
- white space: html doesn't care about white-space & newline & tab. Rendering is purely done using tags
- comments: `<!-- comment -->` is syntax for comments in html. 
- DOM: It is model represents tree structure of document.  
	- most of attribute of html element has one to one mapping with property of dom object, 
	- but for certain attribute their is no mapping, also for certain property in dom their is no attribute in html.