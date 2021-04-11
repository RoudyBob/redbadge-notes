# Basic React Classes



```jsx
import React, { Component } from 'react';

class PropsExample extends Component {

    render() {
        return (
            <div>
                Hello from Props Example
            </div>
        )
    }

}

export default PropsExample;
```

* This is the simplest form of a class that we can create.
* Must have a render \(it's a class component thing specific to react\) and a return in that render. In functional components you just need return.
* Don't forget the EXPORT. 

## Complete Props Example

```jsx
import React, { Component } from 'react';

class PropsExample extends Component {

    render() {
        let {name, business} = this.props;

        return (
            <div>
                {name} is the founder of {business}
            </div>
        )
    }

}

export default PropsExample;
```

```jsx
import React from "react";
import PropsExample from './components/PropsExample';
function App() {
  return <div><PropsExample name="Tom" business="MySpace" /></div>;
}

export default App;

```

* Make sure we use the keyword "this" to reference props from the parent.
* There is also an example of destructuring.

