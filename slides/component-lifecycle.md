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

### Updating

![](img/updating.svg)

[CodePen](https://goo.gl/vXJD1o)

---

### Unmounting

![](img/unmounting.svg)

[CodePen](https://goo.gl/Lu8q1V)

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
