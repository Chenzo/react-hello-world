# Chenzo's Hello World React.JS app

*I'm not entirely sure I like reactjs*

Notes and Updates here:

https://github.com/Chenzo/react-hello-world/wiki/Learning-ReactJS-by-jumping-into-the-deep-end...




Really. I don't know if I like that my HTML is in the JS. Doesn't google want it's content on the page BEFORE JS runs? Also, I'm getting weird compilation errors. 

```
bundle.js:1 Warning: It looks like you're using a minified copy of the development build of React. When deploying React apps to production, make sure to use the production build which skips development warnings and is faster. See https://fb.me/react-minification for more details.
```

What? What does that mean? 

This project was created via this tutorial https://www.codementor.io/reactjs/tutorial/beginner-guide-setup-reactjs-environment-npm-babel-6-webpack - but I think it's dated 


Update - 09.20.16 - found that I needed this in my webpack:

```
var config = {
  ...
  plugins: [
  	new webpack.DefinePlugin({
	  "process.env": { 
	     NODE_ENV: JSON.stringify("production") 
	   }
	})
  ],
  ...
};
```
and then in my packages.json my buid script needed the NODE_ENV variable so now it packs up without errors:

```json
...
  "scripts": {
      "dev": "webpack -d --watch",
      "build" : "NODE_ENV=production webpack -p --colors"
    },
...
```

next is to make it work with a simple node server locally. I was also pointed to this webpage with a crapton of information on it:
http://developer.telerik.com/featured/5-steps-for-learning-react-application-development/?utm_source=javascriptweekly&utm_medium=email


