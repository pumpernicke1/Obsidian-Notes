tags: [[React Index]], [[WebDev Notes]] #react #webdev

# Note: This is the easy way but not the correct way!
For development: paste the following lines
```
<head>
	<script crossorigin src="https://unpkg.com/react@17/umd/react.development.js </script>
	<script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
	<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
	<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
</head>
<body>
	<script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
</body>
```

When your code is ready for production, change the script lines in head to the following:

```
<head>
	<script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
	<script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
	<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
</head>
```

Importing these scripts creates a global ReactDOM object which we can call in our js file to edit the DOM directly through JS

---
Install dependencies locally and then paste the two lines into your JS file:
```
import React from "react"
import ReactDOM from "react-dom/client"
```
