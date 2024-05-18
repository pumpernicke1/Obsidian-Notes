tags: [[React Index]], [[WebDev Notes]] #react #webdev
- React bypasses the need for editing the DOM through JS and instead creats a virtual DOM to edit quickly
	- Also, these changes can be made without being rendered, allowing for multiple changes to be made at once or atleast it can appear that way to users
- Modularizes code allowing for easier editing
- React needs to know when components have been changed in order to decide whether it needs to be re-rendered, making you more mindful of creating immutable code