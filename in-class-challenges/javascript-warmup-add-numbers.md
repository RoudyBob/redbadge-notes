# Javascript Warmup - Add Numbers

```markup
<!-- Insert Basic HTML starter with "!Tab" -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

</head>
<body>
    
    <!-- Create two input fields -->
    <!-- Add single button -->
    <!-- Give ID to the input fields (number1 and number2) -->
    <!-- Give ID of button (btn) -->
    <!-- Don't forget to add the basic.js as your source -->
    <input id='number1' type='text' placeholder='Number 1'></input>
    <input id='number2' type='text' placeholder='Number 2'></input>
    <button type='button' id="btn">Click Me</button>

    <script src='basic.js'></script>
</body>
</html>
```

```javascript
// create 3 variable  button, input1 , input2
// use getElementById method to store the "btn", "number1", "number2"
const button = document.getElementById('btn');
const input1 = document.getElementById('number1')
const input2 = document.getElementById('number2');
console.log(input1);

// Add eventlistner to button that will just do call a function handleClick.
button.addEventListener('click', handleClick);

// make a function called addNumbers that takes two parameters (num1, num2)
// the function addNumbers should return num1+num2
function addNumbers(num1, num2) {
    let sum = parseFloat(num1) + parseFloat(num2)
    return sum;
}

// inside function handleClick call the addNumbers function and console log the result comingback from addNumbers
function handleClick() {
    console.log(`Sum of Numbers: ${addNumbers(input1.value, input2.value)}`);
}
```

