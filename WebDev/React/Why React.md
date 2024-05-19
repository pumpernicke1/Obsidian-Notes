tags: [[React Index]], [[WebDev Notes]] #react #webdev

**What does React do?**
- React bypasses the need for editing the DOM through JS and instead creats a virtual DOM to edit quickly
	- Also, these changes can be made without being rendered, allowing for multiple changes to be made at once or atleast it can appear that way to users
- Modularizes code allowing for easier editing
- React needs to know when components have been changed in order to decide whether it needs to be re-rendered, making you more mindful of creating immutable code

**Why choose React over Vue, Angular, etc.**
 - It has the largest ecosystem
 - It is the most commonly used library 
 - There is less "magic", sort of like C vs Python. This is good for learning since you know everything that is going on
 - It is composable
 - It is declarative

**Composability!**
- React allows you to more easily break down large chunks of HTML code into components which can be placed together and rendered.
- Here is an example:
```
function Header() {
	return (
		<a href="https://instagram.com/pumpernickie" source="blank">Visit our Instagram!</a>
		<h1>Gardening Guru<h1>
		<img src="logo.png"><\img>
	)
function MainContent() {
	return (
		<p>blah blah blah<\p>
	)
ReactDOM.render(
<div>
<Header />
<MainContent />
</div>,
document.getElementById("root")
)
```

**Declarativity!**
- Opposite of Imperative
	- An example of imperative coding would be raw JS where you have to create a new element and replace it with a corresponding element on the DOM