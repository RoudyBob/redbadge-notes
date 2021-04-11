# Challenge 04 Func to Class

```jsx
import React, { Component } from 'react';
import { Button, Container } from "reactstrap";

class ClassClickCounter extends Component {

    constructor(props) {
        super(props);
        this.state = {countValue: this.props.initialValue};
        // this.handleClick = this.handleClick.bind(this);
    };

    handleClick = () => {
        if (this.state.countValue > 0) {
            let tempCount = this.state.countValue - 1;
            this.setState({countValue: tempCount});
        };
    };

    render () {
        return (
            <Container>
            <p>The total clicks left are {this.state.countValue}</p>
            <Button onClick={this.handleClick}> Click Me From Function</Button>
          </Container>
        );
    };
};

export default ClassClickCounter;
```



