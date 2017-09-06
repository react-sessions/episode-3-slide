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

------

### Mounting

![Mounting](img/mounting.svg)

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

------

### Updating

![Updating](img/updating.svg)

[CodePen](https://goo.gl/vXJD1o)

------

#### `componentWillReceiveProps(nextProps)`

- Invoked before a mounted component receives new props.
- Have access to `nextProps` which contains the incoming `props`.
- If you need to update the state in response to prop changes, you may compare `this.props` and `nextProps` and perform state transitions using `this.setState()` in this method.

---

#### `componentWillReceiveProps(nextProps)`

It is possible that React may call this method even if the `props` have not changed, this may occur when the parent component causes your component to re-render.

This method isn't called during initial render (when mounting), only when some of the component props may update.

------

#### `shouldComponentUpdate(nextProps, nextState)`

- Use to let React know if a component's output is not affected by the current change in state or props
- The default behavior is to re-render on every state change, and in the vast majority of cases you should rely on the default behavior.

---

#### `shouldComponentUpdate(nextProps, nextState)`

- Invoked before rendering when new props or state are being received.
- Default return value is `true`.

---

#### `shouldComponentUpdate(nextProps, nextState)`

- Returning false does not prevent child components from re-rendering when their state changes.
- if `shouldComponentUpdate()` returns `false`, then `componentWillUpdate()`, `render()`, and `componentDidUpdate()` will not be invoked.

------

#### `componentWillUpdate(nextProps, nextState)`

- Invoked immediately before rendering when new props or state are being received.
- Use this as an opportunity to perform preparation before an update occurs.
- This method is not called for the initial render.

------

#### `componentDidUpdate(nextProps, nextState)`

- Invoked immediately after updating occurs.
- This method is not called for the initial render.
- Use this as an opportunity to operate on the DOM when the component has been updated.
- This is also a good place to do network requests

------

### Unmounting

![Unmounting](img/unmounting.svg)

[CodePen](https://goo.gl/Lu8q1V)

---

- componentWillUnmount()

- Invoked immediately before a component is destroyed
- Ideal for cleanup tasks like removing listeners, invalidating timers, removing previously added DOM elements
