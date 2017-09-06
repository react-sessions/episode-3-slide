<img src="img/react.svg" class="spin logo logo--small" />

## Setting up a React project by hand

---

[Clone this repository as a starting point](https://github.com/react-sessions/react-barebones)

Includes `index.html` which has a path to a script at `/bundle.js`, and a JavaScript file (`index.js`) with some basic React content.

---

### npm init

Run `npm init` and run through the setup process in order to set this directory up ready for adding modules from npm.

This will add a `package.json` file to your project.

---

### Install React and ReactDOM

(optionally) Install `yarn` package manager

```
npm i -g yarn
```

Install `react` and `react-dom`

```
yarn add react react-dom
```

---

### Install `babel` (and presets) for transpilation

```
yarn add babel-core babel-loader --dev
```

```
yarn add babel-preset-env babel-preset-react --dev
```

---

### Install `webpack` and `webpack-dev-server` for bundling

```
yarn add webpack webpack-dev-server --dev
```

---

### Create Webpack config

[Copy this code](https://gist.github.com/DamianMullins/cf2a11b01d9e14f65add055e71eb8bf4)

---

### Babel config

Create a file called `.babelrc` in thre root of the project and pass in the presets

```
{
    "presets": [
        "env",
        "react"
    ]
}
```

---

### Add npm script

Add a `"scripts"` property to the `package.json` file like so

```js
"scripts": {
    "start-dev": "webpack-dev-server"
}
```
---

### Run the project!

Type `yarn run start-dev` and your new React website will be ready to run at http://localhost:8080
