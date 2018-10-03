# Douglas Souza
# Hacker Rank - JavaScript Challenges - Submissions (Medium/Hard)

[![Hacker Rank Logo](https://hrcdn.net/hackerrank/assets/brand/h_mark_sm-9c05999c62674028552f4e813728e591.svg)](https://www.hackerrank.com/douglas15) - [![Golden Badges](../badges.png)](https://www.hackerrank.com/douglas15)

Day 0: Hello, World! (https://www.hackerrank.com/challenges/js10-hello-world/problem)

```js
function greeting(parameterVariable) {
    // This line prints 'Hello, World!' to the console:
    console.log('Hello, World!');
    console.log(parameterVariable);
    // Write a line of code that prints parameterVariable to stdout using console.log:
    
}
```


Day 0: Data Types (https://www.hackerrank.com/challenges/js10-data-types/problem)

```js
function performOperation(secondInteger, secondDecimal, secondString) {
    // Declare a variable named 'firstInteger' and initialize with integer value 4.
    const firstInteger = 4;
    
    // Declare a variable named 'firstDecimal' and initialize with floating-point value 4.0.
    const firstDecimal = 4.0;
    
    // Declare a variable named 'firstString' and initialize with the string "HackerRank".
    const firstString = 'HackerRank ';
    
    // Write code that uses console.log to print the sum of the 'firstInteger' and 'secondInteger' (converted to a Number        type) on a new line.
    console.log(parseInt(firstInteger) + parseInt(secondInteger));
    
    // Write code that uses console.log to print the sum of 'firstDecimal' and 'secondDecimal' (converted to a Number            type) on a new line.
    console.log(parseFloat(firstDecimal) + parseFloat(secondDecimal));
    
    // Write code that uses console.log to print the concatenation of 'firstString' and 'secondString' on a new line. The        variable 'firstString' must be printed first.
    console.log(firstString + '' + secondString);
    
}
```

Day 1: Arithmetic Operators (https://www.hackerrank.com/challenges/js10-arithmetic-operators/problem)

```js
/**
*   Calculate the area of a rectangle.
*
*   length: The length of the rectangle.
*   width: The width of the rectangle.
*   
*	Return a number denoting the rectangle's area.
**/
function getArea(length, width) {
    let area;
    // Write your code here
    
    area = length * width;
    
    return area;
}

/**
*   Calculate the perimeter of a rectangle.
*	
*	length: The length of the rectangle.
*   width: The width of the rectangle.
*   
*	Return a number denoting the perimeter of a rectangle.
**/
function getPerimeter(length, width) {
    let perimeter;
    
    // Write your code here
    perimeter = (length + width)*2;
    
    return perimeter;
}
```


Day 1: Functions (https://www.hackerrank.com/challenges/js10-function/problem)

```js
function factorial(n){
    if(n > 1){
        return n * factorial((n-1));
    }
    return n;
}
```


Day 1: Let and Const (https://www.hackerrank.com/challenges/js10-let-and-const/problem)

```js
function main() {
    // Write your code here. Read input using 'readLine()' and print output using 'console.log()'.
    
    const PI = Math.PI;
    let radius = parseFloat(readLine());
    
    // Print the area of the circle:
    console.log(PI * Math.pow(radius, 2));
    
    // Print the perimeter of the circle:
    console.log(2 * PI * radius);

	//try catch block hard coded...
}
```


Day 2: Conditional Statements: If-Else (https://www.hackerrank.com/challenges/js10-if-else/problem)

```js
function getGrade(score) {
    let grade;
    // Write your code here
    
    if(score > 25 && score <= 30){
        grade = 'A';
    } else if(score > 20 && score <= 25){
        grade = 'B';
    } else if(score > 15 && score <= 20){
        grade = 'C';
    } else if(score > 10 && score <= 15){
        grade = 'D';
    } else if(score > 5 && score <= 10){
        grade = 'E';
    } else if(score >= 0 && score <= 5){
        grade = 'F';
    }
    
    return grade;
}
```


Day 2: Conditional Statements: Switch (https://www.hackerrank.com/challenges/js10-switch/problem)

```js
function getLetter(s) {
    let letter;
    // Write your code here
    
    //console.log(s[0]);
    switch(String(s[0]).toLowerCase()){
        case 'a':
        case 'e':
        case 'i':
        case 'o':
        case 'u':
            letter = 'A';
            break;
        case 'b':
        case 'c':
        case 'd':
        case 'f':
        case 'g':
            letter = 'B';
            break;
        case 'h':
        case 'j':
        case 'k':
        case 'l':
        case 'm':
            letter = 'C';
            break;
        case 'n':
        case 'p':
        case 'q':
        case 'r':
        case 's':
        case 't':
        case 'u':
        case 'v':
        case 'w':
        case 'x':
        case 'y':
        case 'z':
            letter = 'D';
            break;
    }
    
    return letter;
}
```


Day 2: Loops (https://www.hackerrank.com/challenges/js10-loops/problem)

```js
function vowelsAndConsonants(s) {
    
    let vowels = /[aeiou]/i;
    
    for(let i=0; i<s.length; i++){
        
        let d = String(s).charAt(i);
        
        if(vowels.test(d)){
            console.log(d);
        }
        
    }
    
    for(let i=0; i<s.length; i++){
        
        let d = String(s).charAt(i);
        
        if(!vowels.test(d)){
            console.log(d);
        }
        
    }
    
}
```


Day 3: Arrays (https://www.hackerrank.com/challenges/js10-arrays/problem)

```js
function getSecondLargest(nums) {
    // Complete the function
    
    let highestNumber =0;
    let secondHighestNumber =0;
    
    nums.forEach(num=>{
        
        //console.log('num: ' + num + ' highestNumber: ' + highestNumber + ' secondHighestNumber: ' + secondHighestNumber);
        
        if(num > highestNumber){
            secondHighestNumber = highestNumber;
            highestNumber = num;
        } else if (num < highestNumber && num > secondHighestNumber){
            secondHighestNumber = num;
        }
    });
    
    return secondHighestNumber;
    
}
```


Day 3: Try, Catch, and Finally (https://www.hackerrank.com/challenges/js10-try-catch-and-finally/problem)

```js
function reverseString(s) {
    
    try{
        s=s.split("").reverse().join("");
    } catch (e){
        console.log(e.message);
    }
    
    console.log(s);
    
}
```


Day 3: Throw (https://www.hackerrank.com/challenges/js10-throw/problem)

```js
function isPositive(a) {

    if(a < 0){
        throw new Error('Negative Error');
    } else if(a === 0){
        throw new Error('Zero Error');
    }
    
    return 'YES';
}
```

Day 4: Create a Rectangle Object (https://www.hackerrank.com/challenges/js10-objects/problem)

```js
function Rectangle(a, b) {
    
    let length = a;
    let width = b;
    let perimeter = 2 * (length+width);
    let area = (length*width);
    
    let rectangle = {
        'length': length,
        'width': width,
        'perimeter': perimeter,
        'area': area
    };
    
    return rectangle;
    
}
```

Day 4: Count Objects (https://www.hackerrank.com/challenges/js10-count-objects/problem)

```js
function getCount(objects) {
    
    let totalEqualPairs = 0;
    
    for(let o of objects){
        if(typeof o != undefined && o.x == o.y){
           totalEqualPairs++;
        }
    }
    
    return totalEqualPairs;
}
```


Day 4: Classes (https://www.hackerrank.com/challenges/js10-class/problem)

```js
class Polygon {
    
    constructor(sideLengths){

        this.sideLengths = sideLengths;
        this.perimeterSum = 0;
        
        if(typeof sideLengths != undefined){
            for(let side of sideLengths){
                this.perimeterSum += side;
            }
        }
        
    }
    
    perimeter() {
        return this.perimeterSum;
    }
    
}
```


Day 5: Inheritance (https://www.hackerrank.com/challenges/js10-inheritance/problem)

```js
Rectangle.prototype.area =function () {
    return this.w * this.h;
}

class Square extends Rectangle {
    
    constructor(length){
        super(length, length);    
    }
    
}
```


Day 5: Template Literals (https://www.hackerrank.com/challenges/js10-template-literals/problem)

```js
function sides(literals, ...expressions) {
//    console.log(literals);
//    console.log(expressions);
    
    let area = expressions[0];
    let perimeter = expressions[1];
    let s1 = (perimeter + (Math.sqrt(Math.pow(perimeter, 2)-(16*area))))/4;
    let s2 = (perimeter - (Math.sqrt(Math.pow(perimeter, 2)-(16*area))))/4;
    
    let ret = [s1,s2];
    
    return ret.sort();
}
```


Day 5: Arrow Functions (https://www.hackerrank.com/challenges/js10-arrows/problem)

```js
function modifyArray(nums) {
    
    //let modifiedNums = nums.map(o=>(o%2==0)?o*2:o*3);
    
    let modifiedNums = nums.map(o=>{
        if(o % 2 == 0){
            return o*2;
        } else {
            return o*3;
        }
    });
    
    return modifiedNums;
    
}
```


Day 6: Bitwise Operators (https://www.hackerrank.com/challenges/js10-bitwise/problem)

```js
function getMaxLessThanK(n, k){
    
    //We want to know the maximum bitwise AND value of any two integers, a and b (where a<b), in sequence  that is also less than a given k integer, .
    
    let maxBit = 0;
    
    //console.log(`n: ${n}, k: ${k}`);
    
    for(let a=1; a<=n; a++){
        for(let b=n; b>a; b--){
            //console.log(`a: ${a}, b: ${b}, a&b: ${a&b}, maxBit: ${maxBit}`);
            let current = a&b;
            if(current < k && current > maxBit){
                maxBit = current;
            }
        }
    }
    
    return maxBit;
    
}
```


Day 6: JavaScript Dates (https://www.hackerrank.com/challenges/js10-date/problem)

```js
function getDayName(dateString) {
    
    const locale = 'EN-US';
    
    let date = new Date(dateString);
    let dayName = date.toLocaleDateString(locale, { weekday: 'long' });
    
    return dayName;
    
}
```


Day 7: Regular Expressions I (https://www.hackerrank.com/challenges/js10-regexp-1/problem)

```js
function regexVar() {
    /*
     * Declare a RegExp object variable named 're'
     * It must match a string that starts and ends with the same vowel (i.e., {a, e, i, o, u})
     */
    
    let re = /^a.*a$|^e.*e$|^i.*i$|^o.*o$|^u.*u$/i;

    /*
     * Do not remove the return statement
     */
    return re;
}
```


Day 7: Regular Expressions II (https://www.hackerrank.com/challenges/js10-regexp-2/problem)

```js
function regexVar() {
    /*
     * Declare a RegExp object variable named 're'
     * It must match a string that starts with 'Mr.', 'Mrs.', 'Ms.', 'Dr.', or 'Er.', 
     * followed by one or more letters.
     */
    //String  starts with the prefix Mr., Mrs., Ms., Dr., or Er.
    //The remainder of string  (i.e., the rest of the string after the prefix) consists of one or more upper and/or lowercase English alphabetic letters (i.e., [a-z] and [A-Z]).
    
    //let re = /^M[r,s]\.[a-zA-Z]+|^Mrs\.[a-zA-Z]+|^[D,E]r\.[a-zA-Z]+/;
    let re = /^(?:Mr|Mrs|Ms|Dr|Er)\.(?:[a-z]|[A-Z])+$/;
    
    /*
     * Do not remove the return statement
     */
    return re;
}
```


Day 7: Regular Expressions III (https://www.hackerrank.com/challenges/js10-regexp-3/problem)

```js
function regexVar() {
    /*
     * Declare a RegExp object variable named 're'
     * It must match ALL occurrences of numbers in a string.
     */
    let re = /[0-9]+/g;
    
    /*
     * Do not remove the return statement
     */
    return re;
}
```


Day 8: Create a Button  (https://www.hackerrank.com/challenges/js10-create-a-button)

```html
<!-- Enter your HTML code here -->
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <link rel="stylesheet" href="css/button.css" type="text/css">
        <title>Button</title>
    </head>
    <body>
        <button id="btn">0</button>
        <script src="js/button.js" type="text/javascript"></script>
    </body>
</html>
```

```css
button{
    width: 96px;
    height:48px;
    font-size:24px;
}
```

```js
document.onload = function (){
    let btn = document.getElementById('btn');
    btn.innerHTML = '1';
}

document.getElementById('btn').addEventListener('click', src=>{
    let btn = document.getElementById(src.target.id);
    let currentValue = parseInt(btn.innerHTML);
    btn.innerHTML = (currentValue+1);
});
```


Day 8: Buttons Container (https://www.hackerrank.com/challenges/js10-buttons-container)

```html
<!-- Enter your HTML code here -->
<!DOCTYPE html>
<html>
    
    <head>
        <meta charset="utf-8">
        <link rel="stylesheet" href="css/buttonsGrid.css" type="text/css">
        <title>Buttons Grid</title>
    </head>
    
    <body>
        
        <div id="btns"></div>

        <script src="js/buttonsGrid.js" type="text/javascript"></script>
        
    </body>
    
</html>
```


```css
#btns{
    position:relative;
    width:75%;
}

.btn {
    position:relative;
    width:30%;
    height:48px;
    font-size:24px;
}
```

```js
let container = document.getElementById('btns');

for(let i=1; i<=9; i++){
    
    let newBtn = document.createElement('button');
    
    newBtn.setAttribute('id', `btn${i}`);
    newBtn.setAttribute('class', 'btn');
    newBtn.innerText=i;
    
    container.insertBefore(newBtn, null);
}

document.getElementById('btn5').addEventListener('click', e=>rotateClockWise());

function rotateClockWise(){
    let changeEvents = [];//{objectSource, innerTextValue}
    
    for(let i=1; i<=9; i++){
        
        if(i == 5){
            continue;
        }
        
        let currentBtn = document.getElementById(`btn${i}`);
        let newValue = calculateNewValue(currentBtn.innerText);
        
        changeEvents.push({
            "objectSource": currentBtn, 
            "innerTextValue": newValue
        });
        
    }
    
    for(let event of changeEvents){
        event.objectSource.innerText = event.innerTextValue;
    }

}

function calculateNewValue(currentBtnText){

    let newValue = 0;

    switch(currentBtnText){
        case '1':
            newValue = 4;
            break;
        case '2':
            newValue = 1;
            break;
        case '3':
            newValue = 2;
            break;
        case '4':
            newValue = 7;
            break;
        case '6':
            newValue = 3;
            break;
        case '7':
            newValue = 8;
            break;
        case '8':
            newValue = 9;
            break;
        case '9':
            newValue = 6;
            break;
    }

    return newValue;

}
```


Day 9: Binary Calculator (https://www.hackerrank.com/challenges/js10-binary-calculator)

```html
<!-- Enter your HTML code here -->
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <link rel="stylesheet" href="css/binaryCalculator.css" type="text/css">
        <title>Binary Calculator</title>
    </head>
    
    <body>
        
        <div id="res"></div>
        <div id="btns">
            <button id="btn0">0</button>
            <button id="btn1">1</button>
            <button id="btnClr">C</button>
            <button id="btnEql">=</button>
            <button id="btnSum">+</button>
            <button id="btnSub">-</button>
            <button id="btnMul">*</button>
            <button id="btnDiv">/</button>
        </div>
        
        
        <script src="js/binaryCalculator.js" type="text/javascript"></script>
        
    </body>
    
</html>
```

```css
body{
    width: 33%;
}

#res {
    background-color: lightgray;
    border: solid;
    height: 48px;
    font-size: 20px;
}

#btn0, #btn1 {
    background-color: lightgreen;
    color: brown;
}

#btnClr, #btnEql {
    background-color: darkgreen;
    color: white;
}

#btnSum, #btnSub, #btnMul, #btnDiv {
    background-color: black;
    color: red;
}

#btns button {
    width: 25%;
    height: 36px;
    font-size: 18px;
    margin: 0px 0px 0px 0px;
    float: left;
}
```

```js
class BynaryCalculator {
    
    constructor(){
        this.stage = this.loadInitialState();
        this.stageHTMLRef = null;
    }
    
    loadInitialState(){
        return {
            resultArea: '',
            operationStack: [] //{operation: undefined, value: undefined}
        };
    }
    
    setStageHTMLRef(stageHTMLRef){
        this.stageHTMLRef = stageHTMLRef;
    }
    
    addDigit(event, value){
        
        if(typeof value != undefined){
            this.stageHTMLRef.innerHTML += value;
        }
        
    }
    
    clear(){
        this.stage = this.loadInitialState();
        this.stageHTMLRef.innerHTML = "";
    }
    
    equal(){
        
        let result = 0;
        
        if(this.stage.operationStack.length > 0){
            this.operation('=');
        }
        
        if(this.stage.operationStack.length > 1){
            
            for(let i=0; i < this.stage.operationStack.length; i+=2){
                
                let operand = this.stage.operationStack[i];
                
                let operand2 = this.stage.operationStack[i+1];
                
                if(typeof operand != 'undefined' && typeof operand2 != 'undefined'){
                    
                    let a = this.convertBynaryToNatural(operand.value);
                    let b = this.convertBynaryToNatural(operand2.value);
                    
                    switch(operand.operation){
                        case '+':
                            result = this.convertNaturalToBinary(a+b);
                            break;
                        case '-':
                            result = this.convertNaturalToBinary(a-b);
                            break;
                        case '*':
                            result = this.convertNaturalToBinary(a*b);
                            break;
                        case '/':
                            if(b > 0){
                               result = this.convertNaturalToBinary(a/b);
                            }
                            break;
                    }
                    
                } else {
                    alert('Error: Undefined Operands.');
                }
                                
            }
            
            this.clear();
            this.addDigit(null, result);
            
        }
        
    }
    
    operation(action){
        
        if(this.stage.operationStack.length > 0 && action != "="){
            alert('This calculator only supportes two operands at a time.');
            return;
        }
        
        if(typeof action == 'undefined'){
            throw Error('Invalid Action.');
        }
        
        let stageContent = this.stageHTMLRef.innerHTML;
        
        if(typeof stageContent == 'undefined'){
            throw Error('Invalid Action.');
        }
        
        const operationActionRegex = /\+|\-|\*|\/|\=/;
        
        stageContent = stageContent.substring(this.stage.resultArea.length);
        stageContent = String(stageContent).replace(operationActionRegex, '');
        
        let lastDigit = stageContent[stageContent.length-1];
        
        if(stageContent.length < 1 || operationActionRegex.test(lastDigit)){
            throw Error('Invalid Action.');
        }
        
        this.stage.resultArea = stageContent;

        this.stage.operationStack.push({operation: action, value: stageContent});
        
        this.stageHTMLRef.innerHTML += action;
        
    }
    
    convertBynaryToNatural(binaryNum){
        return parseInt(binaryNum, 2);
    }
    
    convertNaturalToBinary(naturalNum){
        return parseInt(naturalNum).toString(2);
    }
    
}

const calculator = new BynaryCalculator();

window.addEventListener('load', ()=>{
    
    calculator.setStageHTMLRef(document.getElementById('res'));
    
    document.getElementById("btn0").addEventListener('click', (event)=>{
        calculator.addDigit(event, 0);
    });
    
    document.getElementById("btn1").addEventListener('click', (event)=>{
        calculator.addDigit(event, 1);
    });
    
    document.getElementById("btnSum").addEventListener('click', (event)=>{
        calculator.operation('+');
    });
    
    document.getElementById("btnSub").addEventListener('click', (event)=>{
        calculator.operation('-');
    });
    
    document.getElementById("btnClr").addEventListener('click', (event)=>{
        calculator.clear();
    });
    
    document.getElementById("btnEql").addEventListener('click', (event)=>{
        calculator.equal();
    });
    
    document.getElementById("btnMul").addEventListener('click', (event)=>{
        calculator.operation('*');
    });
    
    document.getElementById("btnDiv").addEventListener('click', (event)=>{
        calculator.operation('/');
    });
    
});
```

Douglas Souza
[![LinkedIn Logo](./Linked_in.png)](https://www.linkedin.com/in/douglas-souza-mba-it-developer/)https://www.linkedin.com/in/douglas-souza-mba-it-developer/