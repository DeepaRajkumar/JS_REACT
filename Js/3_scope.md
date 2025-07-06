#                   About Scope 

- global scope 
- Auto global scope
- function scope 
- block scope 
 
```JS 
var teacher = "Sanket singh" 
function fun(){
    content = "JS" 
    teacher = "Deepa Rajkumar"
    console.log("Wow",teacher,content)
}

```
 
 1. scope resolution: 
 teacher - sanket singh / global scope 
 fun - global scope  

 until here phase 1 is completed 

 now second phase is assignment with values: 

 content - is not a formal declaration 
 even though it is not formal declaration , js allow us to add scope. 
 first check fun scope have any content, if not check in global scope if there any. if not then create one global scope - with value "JS"
 

 **if the variable is not formal declaration. but it has LHS then in phase 2 it assign to global scope**

 now teacher - sanket singh (replace with Deepa Rajkumar) - global scope
 content - JS / global scope 

 ```JS
output :
Wow  Deepa Rajkuamr JS
 ```
  
second example:


```JS 
var teacher = 'Sanket singh' 
function fun(){
    teacher = "Deepa Rajkumar" 
    content = "JS" 
    console.log("WoW",content,teacher)
} 
console.log(teacher)
console.log(content)
fun();
``` 

phase 1: 
teacher - global scope 
fun - global scope  

phase 2:  
teacher - global scope - Sanket singh  

here function fun is not called yet so content and teacher will not assigned to global scope  

```JS
Sanket singh 
// error  
here content is not declared yet 
``` 

third problem:  

```JS
var x = 10; 
if(true){
    var x = 20;
    var y= 30; 
    console.log(x,y)
} 
console.log(x,y)
```

var - has global and function scope. 

phase1:
x - global scope 
y - global scope   

phase 2: 
x - 10 then assign to 20 
y = 30 

#  “use strict”

it doesnt allow auto global 


```JS 
"use strict"
var x = 10;  
consoel.log(x,y) // throw error
if(true){
     x = 20;
     y= 30; 
    console.log(x,y)
} 
console.log(x,y)
```
4th problem : 


```JS 
var x = 10 ; 
for(var x=1; x<3; x++){
    console.log(x)
}

console.log(x)// 3

``` 
phase 1 : 
x - global / again global 
phase 2: 
x -> 10 / again assign = 3


# let and var inside the function: 

```JS
function fun(){
    console.log(x)// undefined
    var x = 10 ; 
    console.log(x) //10 
}

``` 
Here the  var has function scope , if we defined the a variable with fucntion scope then we can access that variable anywhere in the function. 


```JS
function fun(){
    console.log(x)// throw error cannot access x before initalize
    let x = 10 ; 
    console.log(x) //10 
}

```  
here let has block scope, before declaration we cannot use the block scope variable. it throw error 

TDZ ( Temporal Dead zone): 
from the begining of the start of the block and the before the variable declaration is called the temooral dead zone 

# About process: 
once the code in the running state: 

- stack -> fucntion / local data 
- heap -> malloc, object 
- Text -> load all the code in the complied form(read only) 
- Data - store static and global variable 
- pc progrma counter ( store the address of the next instruction)


