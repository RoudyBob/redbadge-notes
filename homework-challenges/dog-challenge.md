# Dog Challenge

{% tabs %}
{% tab title="Dogs.js" %}
```typescript
import React from 'react';
import {Container} from 'reactstrap';
import DogIndex from './DogIndex';
 
const Dogs = () => {

  return (
    <Container className="App">
      <br />
      <h1 className="App-intro">
        For this challenge, write the logic to accomplish the following:
      </h1>
      <hr/>
      <ul>
        <li>Fetch a random image from this api: <a href="https://dog.ceo/dog-api/">here</a></li>
        <li>Save this image URL to the state of the DogIndex component</li>
        <li>Render the image to the screen</li>
        <li>Have a button that fetches a new image</li>
        <li>Make sure to include some good practice error handling</li>
      </ul>
      <hr />
      <DogIndex />
    </Container>

  );

}
 
export default Dogs;
```
{% endtab %}

{% tab title="DogIndex.js" %}
```typescript
import React, { Component } from 'react';

class DogIndex extends Component {
    constructor(props) {
        super(props);
        this.state = { imgurl: '' }
    }

    getDogImage = () => {
        let url = "https://dog.ceo/api/breeds/image/random";
        fetch(url)
        .then((response) => response.json())
        .then((data) => {
            this.setState({ imgurl: data.message });
            console.log(this.state.imgurl);
        })
        .catch((error) => alert(error))
    };

    handleClick = () => {
        this.getDogImage();
    }

    componentDidMount () {
        this.getDogImage();
    }


    render() { 
        return (
            <div>
                <img src={this.state.imgurl} alt="" height="300"/>
                <br />
                <br />
                <button onClick={this.handleClick}>Fetch!</button>
            </div>
        );
    }
}
 
export default DogIndex;
```
{% endtab %}
{% endtabs %}

* Define imgurl as state for the class component
* Create a function which performs a fetch to the API URL and then saves the img URL in state - generate a window alert if there is an error
* Create an onClick trigger for the button to call a handleClick function. Ran into an issue where I tried to call getDogImage\(\) from the onClick and this caused the component to mount over and over again. Not sure why doing the exact same thing in function works though.

