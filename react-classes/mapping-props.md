# Mapping Props

{% tabs %}
{% tab title="App.tsx" %}
```jsx
import React from "react";
import PropsExample from './components/PropsExample';
import PropsMapping from './components/PropsMapping';

function App() {
  const visitedPlaces = ["New York","Chicago","San Francisco","Seattle","Los Angeles","Houston"];
  return (
    <div>
      <div><PropsExample name="Tom" business="MySpace" /></div>
      <div><PropsMapping visited={visitedPlaces}/></div>
    </div>
    )

}

export default App;
```
{% endtab %}

{% tab title="PropsMapping.jsx" %}
```jsx
import React, { Component } from 'react';

class PropsMapping extends Component {

    render() {
        const visitedPlaces = () => 
            this.props.visited.map((place) => <li>{place}</li>);
        return (
            <div>
                <h2>Places I've Visited</h2>
                <ul>{visitedPlaces()}</ul>
            </div>
        );
    };

};

export default PropsMapping;
```
{% endtab %}
{% endtabs %}

* Refer to props as this.props.
* Don't forget the \(\) when you call the function from the return!
* 
