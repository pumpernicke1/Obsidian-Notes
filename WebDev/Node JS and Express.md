- Front End
	- Capabilities
		- Making simple apps
		- Displaying data
	- Limitations
		- No way to store data
		- No user authentication and authorization
- Backend: An Intro
	- Node.js
		- It is a server environment that allows programmers to run javascript on a webserver
		- Node is useful for its extensive library of frameworks that come in handy when coding
	- How does the backend communicate with the front end?
		- Front end sends a request to the web server -> Web server retrieves data from database -> Web server sends back info from database -> Front end displays info
		-  Node.js Modules
			- Pieces of reusable code that you can use in your application
			- Examples of modules: datascience for data8, Math, pandas
			- How to import in js: require(*insert module name*)
			- npm - Node Package Manager
				- Manages dependencies within a project
				- Lists all dependencies on a project found in the code so you don't have to worry about manually downloading all dependencies
			- Running npm:
				- npm init
					- Creates packages.json
				- npm install
					- Installs module
					- Updates package.json
- Middleware:
	- An intro
		- Middleware is everything besides frontend and backend
		- Express is an example of middleware, used by programmers to communicate between front-end and backend
		- Allows for abstraction of the backend when using info in the frontend
	- Express
		- Think of it like the lacquer on a wooden table (the wooden table is Node.js)
		- Makes it easier to create APIs
	- 