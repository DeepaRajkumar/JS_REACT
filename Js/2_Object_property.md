                 About Object

Object has many property: 

1.Object.assign() 
2.Object.keys()     
3.Object.values()
4.Object.entries()
5.Object.freeze()
6.Object.seal() 
7.Object.preventExtensions() 
8.Object.isFrozen()
9.Object.isSealed()  
10.Object.isExtensible() 
11.Object.defineProperty()
12.Object.defineProperties() 

1. Object.assign() 
i have an object i want to copy object from multiple source . 

```JS 
let a={name:"Deepa"} 
console.log(a) // { name: 'Deepa' } 

let b = [{phone:8899988,hobby:"For Now Learning JS",passion:"For now Learning Object"}] 
c ={a:7,b:9,c:90}
// Object.assign(target,source1,...source2)  
// if the source object store the objects in the array then use ...b other wise use b directly 
// ...b here we call it as spreading the elements

Object.assign(a,...b,c)

console.log(a) 
//output
{
  name: 'Deepa',
  phone: 8899988,
  hobby: 'For Now Learning JS',
  passion: 'For now Learning Object',
  a: 7,
  b: 9,
  c: 90
}

```
2.Object.keys() 

Return the all the keys in the object in a array

```JS 
let a = {
  name: 'Deepa',
  phone: 8899988,
  hobby: 'For Now Learning JS',
  passion: 'For now Learning Object',
  a: 7,
  b: 9,
  c: 90
} 
 
b = Object.keys(a)  
console.log(b) 

//output
[ 'name', 'phone', 'hobby', 'passion', 'a', 'b', 'c' ]

``` 

3.Object.values() 

Return the values of object in a array. 

```JS 
let a = {
  name: 'Deepa',
  phone: 8899988,
  hobby: 'For Now Learning JS',
  passion: 'For now Learning Object',
  a: 7,
  b: 9,
  c: 90
} 
 
b = Object.values(a)  
console.log(b) 

//output
[
  'Deepa',
  8899988,
  'For Now Learning JS',
  'For now Learning Object',
  7,
  9,
  90
]

``` 

4.Object.entries() 
   return the key and value in pair
   

   ```JS 
   let a = {
  name: 'Deepa',
  phone: 8899988,
  hobby: 'For Now Learning JS',
  passion: 'For now Learning Object',
  a: 7,
  b: 9,
  c: 90
} 
 
b = Object.entries(a)  
console.log(b)


// outout 

[
  [ 'name', 'Deepa' ],
  [ 'phone', 8899988 ],
  [ 'hobby', 'For Now Learning JS' ],
  [ 'passion', 'For now Learning Object' ],
  [ 'a', 7 ],
  [ 'b', 9 ],
  [ 'c', 90 ]
]
   ``` 

 5.Object.freeze() 

  It freeze the object dont allow to insert , delete , edit . only allow to read the entries. 

  ```JS 
  let a = {
  name: 'Deepa',
  phone: 8899988,
  hobby: 'For Now Learning JS',
  passion: 'For now Learning Object',
  a: 7,
  b: 9,
  c: 90
} 
  Object.freeze(a)    
  // insert new entry
 a.d=99 
console.log(a)  

// output
//  {
//   name: 'Deepa',
//   phone: 8899988,
//   hobby: 'For Now Learning JS',
//   passion: 'For now Learning Object',
//   a: 7,
//   b: 9,
//   c: 90
// }

// edit the entry

a.c = 100
console.log(a)  

//output
// {
//   name: 'Deepa',
//   phone: 8899988,
//   hobby: 'For Now Learning JS',
//   passion: 'For now Learning Object',
//   a: 7,
//   b: 9,
//   c: 90
// }

// delete the entry

delete a.c 
console.log(a) 

// output
// {
//   name: 'Deepa',
//   phone: 8899988,
//   hobby: 'For Now Learning JS',
//   passion: 'For now Learning Object',
//   a: 7,
//   b: 9,
//   c: 90
// }

  ```

  6.Object.seal()   

   It seal the object dont allow to insert , delete  . but  allow to read and edit  the entries.  

   ```JS 
   let a = {
  name: 'Deepa',
  phone: 8899988,
  hobby: 'For Now Learning JS',
  passion: 'For now Learning Object',
  a: 7,
  b: 9,
  c: 90
} 
  Object.seal(a)    
  // insert new entry
 a.d=99 
console.log(a)  
//output 
// {
//   name: 'Deepa',
//   phone: 8899988,
//   hobby: 'For Now Learning JS',
//   passion: 'For now Learning Object',
//   a: 7,
//   b: 9,
//   c: 90
// }

// edit the entry

a.c = 100
console.log(a)  
//output
// {
//   name: 'Deepa',
//   phone: 8899988,
//   hobby: 'For Now Learning JS',
//   passion: 'For now Learning Object',
//   a: 7,
//   b: 9,
//   c: 100
// }

// delete the entry

delete a.c 
console.log(a)
//output 
// {
//   name: 'Deepa',
//   phone: 8899988,
//   hobby: 'For Now Learning JS',
//   passion: 'For now Learning Object',
//   a: 7,
//   b: 9,
//   c: 100
// }

   ```

   7.Object.preventExtensions() 

      It doesnt allow to insert the new entries . but allow to delete, update and read the entries.  

      ```JS
         let a = {
  name: 'Deepa',
  phone: 8899988,
  hobby: 'For Now Learning JS',
  passion: 'For now Learning Object',
  a: 7,
  b: 9,
  c: 90
} 
  Object.preventExtensions(a)    
  // insert new entry
 a.d=99 
console.log(a)  

//output
{
  name: 'Deepa',
  phone: 8899988,
  hobby: 'For Now Learning JS',
  passion: 'For now Learning Object',
  a: 7,
  b: 9,
  c: 90
}

// edit the entry

a.c = 100
console.log(a)  

//output 
// {
//   name: 'Deepa',
//   phone: 8899988,
//   hobby: 'For Now Learning JS',
//   passion: 'For now Learning Object',
//   a: 7,
//   b: 9,
//   c: 100
// }

// delete the entry

delete a.c 
console.log(a)
//output
// {
//   name: 'Deepa',
//   phone: 8899988,
//   hobby: 'For Now Learning JS',
//   passion: 'For now Learning Object',
//   a: 7,
//   b: 9
// }
      ``` 

 8.Object.isSealed() 

 all the freeze object is seal object . but all seal object is not freeze . 
 It return true or false. if the object is sealed then retrun true otherwise false 

```JS 
let a = {
  name: 'Deepa',
  phone: 8899988,
  hobby: 'For Now Learning JS',
  passion: 'For now Learning Object',
  a: 7,
  b: 9,
  c: 90
} 

Object.seal(a) 
let b  = Object.isSealed(a)  
let c = Object.isFrozen(a)
console.log(b)  // true
console.log(c) // false
``` 

Object.isFrozen() 

 all the freeze object is seal object . 

 It return true or false. if the object is forzen then retrun true otherwise false  

```JS
let a = {
  name: 'Deepa',
  phone: 8899988,
  hobby: 'For Now Learning JS',
  passion: 'For now Learning Object',
  a: 7,
  b: 9,
  c: 90
} 

Object.freeze(a) 
let b  = Object.isSealed(a)  
let c = Object.isFrozen(a)
console.log(b)  // true
console.log(c)  // true     
 
 ```


 10.Object.isExtensiable() 

 return false if the object is preventExtensions otherwise true 


 ```Js  
let a = {
  name: 'Deepa',
  phone: 8899988,
  hobby: 'For Now Learning JS',
  passion: 'For now Learning Object',
  a: 7,
  b: 9,
  c: 90
}  
let aa ={name:"Simpler"}

Object.preventExtensions(a) 
let b  = Object.isSealed(a)  //false 
let c = Object.isFrozen(a) //false
console.log(b)  
console.log(c) 
let d = Object.isExtensible(a) //false
console.log(d) 
console.log(Object.isExtensible(aa)) //true 
 ``` 

 **So far we target the single object. what if we want to controller the single entries in the object?** 

11. Object.defineProperty() 

used to define the single enteries in an object. 
1. using this create the entries for the object , make thema s uneditable 
2. if create entries using defineProperty , by default enumerable:false. if make enumerable: true then only entries show explicitily  

```JS 
//    (object name, property name, values)
      let a ={
        name:"Deepa", 
        job:"Developer",
    }
    Object.defineProperty(a,"name",{writable:false}) 
    a.name="May" 
    a.job = 'Full stack developer'
    Object.defineProperty(a,"rate",{value:89,writable:false}) 
    console.log(a) //{ name: 'Deepa', job: 'Full stack developer' 
    console.log(a.rate) // 89
    Object.defineProperty(a,"hobby",{value:"For now learning JS",enumerable:true}) 
    console.log(a) //output
//     {
//   name: 'Deepa',
//   job: 'Full stack developer',
//   hobby: 'For now learning JS'
// }
```
12.Object.defineProperties() 

using defineProperty can do here also for multiple entries  

```JS
    let a ={
        name:"Deepa", 
        job:"Developer",
    }
    Object.defineProperties(a,
        {
         name:{
            value:"May", 
            writable:false
         }, 
         rate:{
            value:908, 
            enumerable:true
         }

        }
    ) 
    
    console.log(a) //
// { name: 'May', job: 'Developer', rate: 908 } 

```