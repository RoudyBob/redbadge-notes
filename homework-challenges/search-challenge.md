# Search Challenge

{% tabs %}
{% tab title="Search.js" %}
```jsx
import React from 'react';
import SearchIndex from './SearchIndex';
import { Container } from 'reactstrap';
 
const Search = () => {
   return (
     <Container className="App">
     <br />
       <h1 className="App-intro">
     In this challenge your goal is to use the existing code to create the following: 
       </h1>
       <hr />
       <ul>
         <li>
           ability to accept a search term from a user
         </li>
         <li>
            ability to filter the array in the state by that term
         </li>
         <li>
            ability to display only the terms that match the search, or all if no search term is provided
         </li>
       </ul>
       <hr />
       <SearchIndex />
     </Container>
   );

}
 
export default Search;

```
{% endtab %}

{% tab title="SearchIndex.js" %}
```jsx
import React, { Component } from 'react';
import { Input } from 'reactstrap';
 
class SearchIndex extends Component {

  constructor(props) { 
    super(props);
    this.state = {
      things: ['pen', 'marker', 'eraser', 'notebook', 'pencil', 'scissors', 'highlighter', 'stapler', 'paper clip', 'binder', 'hole punch', 'laminator', 'laminating sheets', 'protective sheets', 'index cards'],
      results: ['pen', 'marker', 'eraser', 'notebook', 'pencil', 'scissors', 'highlighter', 'stapler', 'paper clip', 'binder', 'hole punch', 'laminator', 'laminating sheets', 'protective sheets', 'index cards'],
    };
  };

 searchFunction = (e) => {
   e.preventDefault();
   console.log(e.target.value);
   if (e.target.value !== '') {
      let tmpArray = this.state.things.filter((element) => {
        return element.toLowerCase().indexOf(e.target.value.toLowerCase()) !== -1
      })
      this.setState({results: tmpArray})
   } else {
     this.setState({results: this.state.things})
   }
 }

 render() {
    return(
     <div>
       <Input placeholder='Search Here' onChange={this.searchFunction}/>
       <h3>Results:</h3>
       <ul>
            {this.state.results.map((item,i) => <li key={i}>{item}</li>)}
       </ul>
     </div>
    );
 };

};
 
export default SearchIndex;
```
{% endtab %}
{% endtabs %}

* Fixed several issues in the file - const instead of class for declaring the class, missing default in export, constructor/state not created properly, etc.
* Used the onChange trigger for the input element - combined with array.filter to create a new array containing the matching items from the things array.
* set results equal to things as the default \(before any onChange triggers\) and then also a check inside of the SearchFunction to see if all of the text had been deleted from the search box. If it had been, reset the results array to the things array.
* Used .map to map over the results array and list results as &lt;li&gt;.

