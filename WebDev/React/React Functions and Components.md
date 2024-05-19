Tags: [[React Index]] #react #webdev 

- You've seen earlier in  [[React JSX]] how to properly render elements on the virtual DOM, but this doesn't properly reflect how elements are normally composed
- Instead, multiple elements are compiled into one "component" which is rendered all at once
	- Examples of components include navbars, grids, forms
	- Components can even be made of smaller components
		- eg. A grid component can be made out of smaller tile components
- Components are constructed through react functions:
	- Example below
```
function Square({ value }) {
  return <button className="square">{value}</button>;
}

export default function Board() {
  return (
    <>
      <div className="board-row">
        <Square value="1" />
        <Square value="2" />
        <Square value="3" />
      </div>
      <div className="board-row">
        <Square value="4" />
        <Square value="5" />
        <Square value="6" />
      </div>
      <div className="board-row">
        <Square value="7" />
        <Square value="8" />
        <Square value="9" />
      </div>
    </>
  );
}

```
- These functions just return regular HTML code and can even use JS values 
	- Look at function Square's parameter value
		- When using passed in JS values like value or something like object properties, the value must be wrapped in braces whenever it's used
- If you have a JS function related to a component, place this function inside of the component function
	- For example, let's say you have a button component and you need a function that executes when the button is clicked, you would write the following
```
	function LikeButton() {
		const[numLikes, setLikes] = useState(null); //This is a hook, which will be covered later
		function handleClick() {
			setLikes(numLikes + 1)
		}
		return <button className="like-button">{numLikes}</button>;
	}
```
## Props and "Lifting Up"
- This like  button works great. Now, let's say we place one like button above the video and one under the description. It shouldn't matter which one you click right? Since both count as a like, the number of likes should be the same whether we click the top or bottom button.
- Error! When we click on the top button, it increments from 0 likes to 1 like. Great, but the bottom button is still at 0 likes. It looks like numLikes isn't a shared variable between the components. How do we fix this
- The solution is lifting up the state to the larger component containing the two LikeButton components. Let's call this component VideoPage which would look something like this
```
function VideoPlayer() {
	return(
		<>
			<div className="video-player">
				<VideoPlayer value="vidId" />
			</div>
			<div className="interactions">
				<LikeButton />
				<LikeButton />
				<Subscribe />
			</div>
	)
}
```
-  Instead of having our useState declaration in the Square function, we lift it up one level into the VideoPlayer component as shown here
```
function LikeButton(likes, onButtonClick) {
	return <button className="like-button" onClick={onButtonClick}>{likes}</button>
}

function VideoPlayer() {
	const[numLikes, setLikes] = useState(null); 
	function handleClick() {
		setLikes(numLikes + 1)
	}
	return(
		<>
			<div className="video-player">
				<VideoPlayer value="vidId" />
			</div>
			<div className="interactions">
				<LikeButton />
				<LikeButton />
				<Subscribe />
			</div>
	)
```
- We have lifted up the responsibility of tracking the number of likes from each instance of LikeButton to the broader component VideoPlayer and passed down the values into the buttons as **"props"** 