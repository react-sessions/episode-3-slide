<img src="img/react.svg" class="spin logo logo--small" />

## Component lifecycle

---

### What are the lifecycle methods?

Each component has several "lifecycle methods" that you can override to run code at particular times in the process.

Methods prefixed with `will` are called right before something happens, and methods prefixed with `did` are called right after something happens.

<p><small>https://facebook.github.io/react/docs/react-component.html</small></p>

---

### Phases

- Mounting
- Updating
- Unmounting

---

### Mounting

![](img/mounting.svg)

[CodePen](https://goo.gl/DposJo)

---

constructor():
- Called when creating the component
- Should call `super(props)` at the top of the constructor, otherwise `this.props` will be undefined in the constructor and may lead to bugs
- Should set state here with `this.state = {...}`
- Can bind functions here with `this.methodName = this.Methodname.bind(this)` which ensures that the value of 'this' when the function is called refers to the containing class

---

componentWillMount():
- Invoked immediately before the component is rendered to the DOM
- `this.props` and `this.state` are available to use here
- Can prepare initial state here before the initial render - it will not trigger a re-render
- Making async API calls here could lead to problems such as undefined component state

---

componentDidMount():
- Invoked immediately after the component is rendered to the DOM
- DOM accessible from this method so all setup that requires the DOM done here.
- Good place for fetching data as component is already rendered with initial state
- Setting state here triggers a re-render

---

### Updating

![](img/updating.svg)

[CodePen](https://goo.gl/vXJD1o)

---

### Unmounting

![](img/unmounting.svg)

[CodePen](https://goo.gl/Lu8q1V)

---

componentWillUnmount():
- Invoked immediately before a component is destroyed
- Ideal for cleanup tasks like removing listeners, invalidating timers, removing previously added DOM elements

---

# TODO

Talk about each of these; when they are called, what you can and can't do in each, etc.

- constructor()
- componentWillMount()
- render()
- componentDidMount()

- componentWillReceiveProps()
- shouldComponentUpdate()
- componentWillUpdate()
- componentDidUpdate()

- componentWillUnmount()
