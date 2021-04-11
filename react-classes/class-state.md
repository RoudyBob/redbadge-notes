# Class State

```jsx
import React, { Component } from 'react';

class StateExample extends Component {
    render () {
        return (
            <div>
                <h2>Hello from StateExample</h2>
            </div>
        )
    };
};

export default StateExample;
```

* If we are going to use state we MUST have a constructor



```jsx
import React, { Component } from 'react';

class StateExample extends Component {

    constructor(props) {
        super(props);
        this.state = {currentTemp: "78"}
    }
    
    render () {
        return (
            <div>
                <h2>Hello from StateExample</h2>
            </div>
        )
    };
};

export default StateExample;
```

* If you are not assigning props, you don't need the props in super\(\);
* You must always have super\(\) in your class component!
* As a standard, you'll see super\(props\) even though you might not need it.
* Keyword super refers to the parent class.
* Constructor is the first thing that gets called when the class is initialized.

```jsx
import React, { Component } from 'react';

class StateExample extends Component {

    constructor(props) {
        super(props);
        this.state = {currentTemp: "78"}
    }

    render () {
        return (
            <div>
                <h2>Hello from StateExample</h2>
                <p>The current temp is {this.state.currentTemp}. </p>
            </div>
        )
    };
};

export default StateExample;
```

## How to access state?

* must use "this" when referencing state
* example: this.state.currentTemp

## How to change/update state?

* Never update state directly. Example: this.state.currentTemp = "48"
* Can't predict when state will change.
* use this.setState\(\) to change state
* Never setState in constructor!
* What goes in the setState? An object - key/value pairs

```jsx
import React, { Component } from 'react';

class StateExample extends Component {

    constructor(props) {
        super(props);
        this.state = {currentTemp: "78"}
        this.handleClick = this.handleClick.bind(this);
    }

    handleClick() {
        this.setState({currentTemp: "48"})

    }

    render () {
        return (
            <div>
                <h2>Hello from StateExample</h2>
                <p>The current temp is {this.state.currentTemp}. </p>
                <button onClick={this.handleClick}>Click Me to Change Temp</button>
            </div>
        )
    };
};

export default StateExample;
```

## Handling Events

* [https://reactjs.org/docs/handling-events.html](https://reactjs.org/docs/handling-events.html)
* If setState is inside of a method we must bind it

  ```jsx
  this.handleClick = this.handleClick.bind(this);
  ```

## Final Notes

* Think of setState as a request instead of an immediate command.
* React may delay the update. Then update several components at once.
* You only need to put the values you need in setState - i.e., if you have multiple state things you're keeping track of.
* Think of setState as taking a set of key/values

