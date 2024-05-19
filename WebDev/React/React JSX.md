
# Note: This is now outdated in React 18
- React allows us to directly (and declaratively) alter the HTML, allowing for easier implementation of interactivity
- This is done through the global ReactDOM object
- An example:
```
ReactDOM.render(element, element_location)
```
- Lets look at these components more closely
			- The elementdddddddd
		- Identifies the html type (h1, p, a, etc.) and the contents, functionally identical to regular HTML
		- One distinction: class is replaced by className so now it is `<h1 className="title"></head>`
		- Note: You can only load one parent element at a  time
			- For example,  `<h1><\h1><p><\p>` wouldn't work
			- Notice how it's one parent element and not just element though
			- You actually can load multiple elements together, but they must be placed in a container element like a div
	- The element location
		- The element in the HTML file you want to render to
		- eg.  document.getElementById("logo")
# New method of rendering in React 18
- Rather than calling the element location, you must now create a root object which you can render from directly.
```
ReactDOM.createRoot(Document.getElementById("root").render(element)

	//this can be split up into two lines
root = ReactDOM.createRoot(Document.getElementById("root"))
root.render(element)
```
