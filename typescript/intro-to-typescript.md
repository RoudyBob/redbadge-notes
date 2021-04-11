# Intro to Typescript

## Installing TS

* Check to see if you have Typescript installed: tsc --version
* Have to install it globally if it's not installed.
* Mac users: have to use sudo.
* \[sudo\] npm install -g typescript
* A couple of VSC extensions which are helpful:
  * eslint and path intellisense

## How to compile your TS File

* tsc &lt;name of file&gt;

## Types and Inference

```javascript
let number1;
let name1;
let stringExample: string;

stringExample = "Hello"

//Type Inference
let number2 = 5;

// number2 = "45"; //This will cause an error.

let restaurant = {
    name: "McDonalds",
    dineIn: false,
    foodItems: ["hamburgers", "fries", "apple pie"]
};

restaurant.foodItems.forEach((item) => {
    console.log(item.toUpperCase());
});

let unionStringNumber: number | string;
unionStringNumber = 5;
unionStringNumber = "5";
```

## Types of Types

* string 
* boolean
* number
* any

#### Union Types

* Union types allow you to combine several types to a variable
* Use the "pipe" to tell typescript what the possible types **ex: string\|number**
* You can even have **"Literal Types"** where you are clear about the exact value it should have.

```javascript

let unionStringNumber: number | string;
unionStringNumber = 5;
unionStringNumber = "5";
```

## Types with Functions

```javascript
function tradeStock (stockName: string, quantity: number|string, action: "sell-stock"|"buy-stock") {
    let total: number = +quantity * 15;
    // if (action === "buy-stock") {
    //     var statement: string = `You just bought ${quantity} stocks of ${stockName} for a total of ${total}`;
    // } else if (action === "sell-stock") {
    //     var statement: string = `You just sold ${quantity} stocks of ${stockName} for a total of ${total}`;
    // }
    let status = action === "sell-stock" ? "sold" : "bought";
    return `You just ${status} ${quantity} stocks of ${stockName} for a total of $${total}`;
}

tradeStock("Bank of America", 200, "sell-stock");
```

## Interfaces

* typically use PascalCase
* usually only used with Objects
* can use ? to make things optional

```typescript
interface IWeather {
    // used to describe an object - it's not an object!
    temp: number, // semi-colons or commas
    cloudConditions: string,
    next5dayTemps?: number[] // this is an array // question mark makes it optional
}

// let weather = {
//     temp: 78,
//     cloudConditions: 'overcast',
//     next5dayTemps: [81.74,79,81,81]
// }

let weather: IWeather = {
    temp: 55,
    cloudConditions: "sunny",
    next5dayTemps: [81.74,79,81,81]
}

```



