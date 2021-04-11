# Mini Challenge TS

```typescript
// PROBLEM 1
//Fix the error with out altering lines 10 through 14

let myAddress: {
  number: string;
  streetName: string;
  city: string;
  zipcode: string;
} = {
  number: "1245",
  streetName: "Coding Plains Ct",
  city: "Indianapolis",
  zipcode: "46239",
};
```

```typescript
// PROBLEM 2

function convertToDegreeCelcus(temps: string[]) {
  return temps.map((singleTemp) => Math.floor(((+singleTemp - 32) * 5) / 9));
}

const dailyTemps = ["93", "78", "88"];
console.log(convertToDegreeCelcus(dailyTemps));
```

```typescript
// Fix problem without altering StateInitials
interface IStateInitials {
    alabama: string,
    alaska: string,
    arizona: string,
    indiana: string,
    florida: string,
    newjersey: string,
 }
 
 let StateInitials: IStateInitials = {
   alabama: "AL",
   alaska: "AK",
   arizona: "AZ",
   indiana: "IN",
   florida: "FL",
   newjersey: "NJ"
 }
```

```typescript
// Problem 4
// Keep the return type string

function subtractNums(num1: string, num2: String): string {
  let numberSub = +num1 - +num2;
  return numberSub.toString();
}

console.log(subtractNums("10", "5"));
```

