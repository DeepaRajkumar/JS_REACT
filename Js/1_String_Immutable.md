                 About constant 

 
 const dont allow to only declration of variable. must assign the value for the const variable while declaration. 

```JS
const a;  // error - SyntaxError: Missing initializer in const declaration 
```

 valid const assignment 

```JS
const a = null ;   
const b = 10;
const ab = {name:"Deepa Rajkumar",job:"Developer"}
```

 const dont allow the reassignment   

```JS
 a = 8; // TypeError: Assignment to constant variable. 
 ```


                const in Object   


```JS
const cs = {a:"1",b:"2"} 
 ```

 cs object is assigned as const 

  as our above statment const dont allow re-assignment, so it does not allow to add new entries to object  

```Js
cs.rate =89  

console.log(cs)  //{ a: '1', b: '2', rate: 89 }
 ``` 

 see the result showing that we can edit the object means here re-assignment is working right? ,but it is not true. 

 Object is the object ; if we assign the value to object then object doesnot directly store the value to memory in the object name   

 instead of that value stored in one place(call value address) that address is assign to object value.  

 when ever we try to access cs object, it call refernce in the cs object.  

 in the above we added rate to cs ; this rate added in the  value address.  

 ```Js
 cs = {a:89};//TypeError: Assignment to constant variable.  
 ```



see above value gives error why  

 the new value is stored in new memory (call second value memory) and try to remove vale memory ref stored in the cs Object and add its second value memory ref in the Object. This is called the assignment to object . this behavior is not allowed in const in object 


                 String Immutable 


How the string is immutable? 

```JS 
let a = "Deepa Rajkumar"  
console.log(a)  //Deepa Rajkumar 

a = "New Deepa Rajkumar" 
console.log(a) // New Deepa Rajkumar 


```


**Const dont allow to re-assignment.String is immutable means it does not means it doesnt allow re - assignment** 

Then what is immutable in the string? 



```JS 

for(let i in a){
    console.log(a[i])
} 

//Output 
N
e
w

D
e
e
p
a

R
a
j
k
u
m
a
r


```


If you see we in a string we can access single character of the string. 

If we try to modify the any one character, it doesnt allowable. This property of string we are calling immutable of string. 

```JS  
a = "New Deepa Rajkumar" 
console.log(a) //New Deepa Rajkumar 

a[0] = "M" 
console.log(a[0]) // N
console.log(a) // New Deepa Rajkumar 
``` 

see above example we changed string index 0 n -> M even after reassignment still showing N. 

This property we call it as string immutable property. 


      Difference between for and for..in and for..of 

1. for 
 
```JS
a = [1,3,4,5];
b = "Learning JS"; 
for(let i=0; i<a.length; i++){
    console.log(a[i]) 
} 
```

we know that array always store the vaalue in the continous memory location. To access the value we need to access its index. like 0,1.... 

In a string if we need to access each character same we can access using index  

In the object, key is unique and it value can be duplicate .
In array , index is the key and value is the value (cab be duplicate value)


2. for.. in 

in for we need to mention the length.  
but in the for .. in we need to metion the length

```JS 
a = ["deepa",96,{myname:"May"}]
for(let i in a){
    console.log(i) // index
    console.log(a[i]) // value of index
    
} 
// output 
0
deepa
1
96
2 
{ myname: 'May' }  



// access the object 
b = {name:"Deepa",job:"developer",learning:"JS"}
for(let i in b){
    console.log(i) // key
    console.log(b[i]) // value of key
} 
//output 
name
Deepa
job
developer
learning
JS
```

3. for .. of 

for.. of works for array , it access the value of the array directly. 

```JS 
let a = [7,8,9,"Testing","Data"] 
for(let i of a){
    console.log(i)
} 

//output 
7
8
9
Testing
Data

```