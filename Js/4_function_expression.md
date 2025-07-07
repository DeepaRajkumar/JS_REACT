# Function Express

```Js
const myFun = function fun(x){
 console.log("calling")
} 

myFun(10)
``` 
Different type of function expression 

Example 1: Named function expression 

```JS
const myFun = function fun(){
    console.log("Function Expression")
}
``` 
Example 2: Anonyms Function Expression:

```JS
const myFun = function (x){
    console.log("Function Expression")
}
```
Example 3: Arrow function/ Arrow Function Expression:

```JS
const myFun =  (x)=>{
    console.log("Function Expression")
}
```

Example 4: IIFE - Immediate invoke function expression

```JS
(function fun(x){
    console.log("Function Expression")
})(10)
``` 

Map() is part of array internal fucntion. it always expected a function as argument.  
map return new array

```JS 
let arr = [1,2,3,4,5];
const newArray = arr.map(function fun(element){
    return element*2;
}) 
console.log(newArray) //[2,4,6,8,10]
```

How To write the custom Map function: 


```JS
 let arr = [1,2,3,4,5];

function CustomMap(arr,fn){ 
    let newArray = []; 
    for(let i=0; i<arr.length;i++){
        newArray.push(fn(arr[i]))
    } 
    return newArray

} 

const mynewData = CustomMap(arr,function fn(element){
     return element*2
}) 

console.log(mynewData)
``` 

 
 # Should we use Named fucntion expression or anonymous fucntion expression: 

 - Named FE imporves readability of the code. Because anonymous fucntion expression dont have name, we have to read their whole logic to understand what they are doing,we have to read their whole logic to understand what they are doing where as if properly named, then named fucntion expression are more understandable directly by the name. 
 - Anonymous functions are hard to debug. Because when you check the call stack of the fuction, then you will not function any name for anonymous function expression.  

 console.trace("call stack")
 used to track the call stack 

 ```JS
    function fun(fn){
        const arr= [1,2,3,4,5]; 
        fn(arr);
    } 
    fun(function gun(arr){
        console.trace("call stack deepa")
    }) 
    // output 
//    VM45:6 call stack deepa
// gun	@	VM45:6
// fun	@	VM45:3
// (anonymous)	@	VM45:5
 ```


Anonymous fucntion expression: 
```JS 
 function fun(fn){
        const arr= [1,2,3,4,5]; 
        fn(arr);
    } 
    fun(function (arr){
        console.trace("call stack deepa")
    })
// output
// VM40:6 call stack deepa
// (anonymous)	@	VM40:6
// fun	@	VM40:3
// (anonymous)	@	VM40:5
``` 

# Arrow fucntion: 
This function expression is generally preferred for concise syntax. There is one very fundamental difference in using arrow functions and other fucntion expression. i.e in arrow fucntions the this keyword is resolved lexically whereas in other this keyword is resolved by the call site. 
If arrow fucntion has only one line logic i.e to return something then we dont need to use return keyword 

If google has 40000 Lakh line code. 
junior written code and manager review the code find junior assigned same function name which is already defined. 

To handle this issue temporarily we can use IIFE