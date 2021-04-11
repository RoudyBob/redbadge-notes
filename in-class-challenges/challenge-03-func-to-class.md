# Challenge 03 Func to Class

```jsx
import React, { Component } from 'react';
import { Alert, Container } from 'reactstrap';

class ClassComponentProps extends Component {
    
    render() {
        const { numbers } = this.props;

        // function displayAlerts() {
        //     return numbers.map((num, index) => (
        //         <Alert key={index} color={num % 2 === 0 ? "success" : "danger"}>
        //         The number is {num}{" "}
        //         </Alert>
        //     ));
        // };

        const displayAlerts = () => numbers.map((num, index) => <Alert key={index} color={num % 2 === 0 ? "success" : "danger"}>The number is {num}</Alert>)

        return (
            <Container>
                <h3>From the Class Component</h3>
                {displayAlerts()}
          </Container>
        )
    }

}

export default ClassComponentProps;
```

* If you're using method calls in your JSX, don't forget the keyword of ".this".
* 
