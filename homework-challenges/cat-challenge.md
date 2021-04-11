# Cat Challenge

```jsx
import React from 'react';
import CatIndex from './CatIndex';
import { Container } from 'reactstrap';
 
const Cats = () => {
   return (
     <Container className="App">
       <br/>
       <h1 className="App-intro">
         To complete this challenge, complete and fix the existing code to have it do the following:
       </h1>

       <hr />
         
        <ul>
         <li>Render the list of cat breeds to the screen</li>
         <li>Use props correctly</li>
         <li>Use .map() correctly</li>
         <li>Ensure there are no errors</li>
        </ul>
        <hr />
       <CatIndex /> 
     </Container>
   );

}
 
export default Cats;
```

```jsx
import React, { Component } from 'react';
import CatList from './CatList';
 
class CatIndex extends Component {
 constructor(props) {
   super(props)
   this.state = {
     breeds: ['persian', 'siamese', 'maine coon', 'ragdoll', 'scottish fold', 'sphynx', 'british shorthair', 'bengal', 'american shorthair']
   }
 }
  render () {
    return (
      <div>
       <CatList cats={this.state.breeds} />
      </div>
    );
  }

}

export default CatIndex;

```

* Don't forget to add the constructor above the render\(\) to build out the class component.
* State for the component is initialized in the constructor using this.state - in this case, it's a single array of cat breeds.
* When you pass the state as a prop to the child component you do so with &lt;propname&gt;={this.state.&lt;statename&gt;}

```jsx
import React, { Component } from 'react';
 
class CatList extends Component {

  render() {

    return (
      <div>
        { this.props.cats.map((cat,index) => <li key={index}>{cat}</li>) } 
      </div>
    );
  };
};
 
export default CatList;

```

* You can use the prop \(in this case an array\) with the map function by referring to "this.props.cats". Cats is the name provided in the parent component when passing the prop.

