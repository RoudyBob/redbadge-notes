# State & Fetch

```jsx
import React, { Component } from 'react';

class ClassDeckFetch extends Component {

    constructor(props) {
        super(props);
        this.state = {deckID: ""};
    };

    fetchDeck() {
        // What's the URL to fetch?
        const url = "https://deckofcardsapi.com/api/deck/new/shuffle/?deck_count=1";

        // Store the data from the fetch.
        fetch(url)
        .then (res => res.json())
        // .then (data => this.setState({deckID: data}))
        .then (data => console.log(data))
    }

    componentDidMount() {
        this.fetchDeck();
    }

    render() {

        return(
            <div>Hello from ClassDeckFetch</div>
        );
    };
};

export default ClassDeckFetch;

```

1. Create the Class
2. Add the Render
3. Create the Constructor
4. Add State \(for deckID\) to store value from Fetch
5. Added method to conduct the Fetch
6. Added the componentDidMount to make the page fetch with it finished loading.

```jsx
import React, { Component } from 'react';

class ClassDeckFetch extends Component {

    constructor(props) {
        super(props);
        this.state = {deckID: "", cardUrl: ""};
    };

    fetchDeck() {
        // What's the URL to fetch?
        const url = "https://deckofcardsapi.com/api/deck/new/shuffle/?deck_count=1";

        // Store the data from the fetch.
        fetch(url)
        .then (res => res.json())
        .then (data => this.setState({ deckID: data.deck_id }))
    }

    fetchCard() {
        const url = `https://deckofcardsapi.com/api/deck/${this.state.deckID}/draw/?count=1`;

        // Store the data from the fetch.
        fetch(url)
        .then (res => res.json())
        .then (data => this.setState( {cardUrl: data.cards[0].image}))
    }

    componentDidMount() {
        this.fetchDeck();
    }

    componentDidUpdate(prevProps, prevState) {
        if (prevState.deckID != this.state.deckID) {
            this.fetchCard();
        }
    }

    render() {

        return(
            <div>
                <h2>Hello from ClassDeckFetch</h2>
                <img src={this.state.cardUrl} />
            </div>
        );
    };
};

export default ClassDeckFetch;
```

## Final Thoughts

* If you want to call a method on page load, it must be in the componentDidMount.
* In a class component, the methods are called in the following order:
  * constructor
  * render
  * componentDidMount
  * 

