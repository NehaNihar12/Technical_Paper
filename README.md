# ES6
# Introduction
ECMAScript, or ES, is a standardized version of JavaScript. The terms ECMAScript and JavaScript are interchangeable.
>
JavaScript is a scripting language you can use to make web pages interactive. It is one of the core technologies of the web, along with HTML and CSS, and is supported by all modern browsers. 
>
Here we will talk about `Data Types` and `In-Built Data Structures`
# Javascript Variables
In JavaScript, a variable stores the data value that can later vary.
>
There are 4 ways to declare a variable
>* var
>* let
>* const

## let
>* Can Not be redeclared
>
>```
> let x = true;
>
> let x = 0;
>
>#SyntaxError: 'x' has already been declared 
>```
>* Block scope
>```
>{
>  let x = 2;
>}
># x can NOT be used here
>```
## var
>* Can be redeclared
>
>```
> var x = true;
>
> var x = 0;
>
>```
>* Global Scope and Function Scope.
>```
>{
>  var x = 2;
>}
>#x CAN be used here
>```
## const
>* Can NOT be redeclared
>* Can NOT be reassigned
>```
>const A = 2;
>A = 6;      # This will give an error
>A = A + 10;   # This will also give an error
>```
>* Must be assigned a value when they are declared:
>```
>const TIME = 2;
>```

Difference between var, let and const :
| Parameter         | var       | let         | const        |
| :---              |    :----: |   :------:  |  -----:      |
| Scope             | functional| block       | block        |
| Updated in the scope| Yes     | Yes         | No           |
| Redeclared in the scope| Yes  | No          | No           |
| Declared without initialization| Yes| Yes | No|
| Can be accessed without initialization| Yes(default: undefined)| No| No|


# Javascript DataTypes
## Dynamic Typing
JavaScript has dynamic types. This means that the same variable can be used to hold different data types.
> let x; #Now x is undefined
>
> x = 4.17; #Now x is a Float value
>
> x = "John"; #Now x is a String
## Types
Javascript data type are broadly categorised into 
* ### Primitive Types
    * ### Boolean : It has two values `true` and `false`
    >```
    >let a = 3
    >let t = 4
    >(x===y) #returns false
    >let a = true
    >``` 
    * ### Null : It has exactly one value `null`
    >```
    >let a = null
    >```
    * ### Undefined : A variable that has not been assigned a value has the value `undefined`.
    >```
    >let a;    
    >#Value is undefined, type is undefined
    >```
    * ### Number : An integer or floating point number.
    >```
    >let x1 = 34.00;     # floating point
    >let x2 = 34;        # integer
    >let y = 123e5;      # 12300000 in scientific (exponential) notation
    >let z = 123e-5;     # 0.00123 in scientific (exponential) notation
    >```
    * ### BigInt : BigInt is a numeric data type that can represent integers in the `arbitrary precision format`
    >```
    >const aInt = 9007199254740991n
    >```
    >```
    >#It can also be declared as object
    >
    >const hugeNo = BigInt(9007199254740991)
    >#9007199254740991n
    >
    >const hString = BigInt("9007199254740991")
    >#9007199254740991n
    >
    >const hHex = BigInt("0xab")
    >#171n
    >
    >const hugeOctal = BigInt("0o377777777777777777") #9007199254740991n
    >```
    * ### String
    >```
    >let s = "Hi, Paul."
    >let t = 'Text 23hg'
    >```
    
* ### Objects : Objects can be seen as a collection of properties. They are useful for storing data in a structured way, and can represent real world objects, like a cat.
    >```
    >const cat = {
    >"name": "Whiskers",
    >"legs": 4,
    >"tails": 1,
    >"enemies": ["Water", "Dogs"]
    >};
    >```
## `typeof` Operator  
The `typeof` operator is used to find the type of a JavaScript variable. e.g
```
typeof "John"         #Returns "string"
typeof 314            #Returns "number"
typeof true           #Returns "boolean"
```

# Javascript In-Built Data Structure
## Array
Array is an object which enables us to store a collection of multiple items under a single variable name. JavaScript arrays are resizable and can contain a mix of different data types. e.g.
```
const arr = [1, 2.5, "cat"]
```
### Creating an Array
* Using an array literal
> Syntax : const array_name = [item1, item2, ...]; 
>e.g.
>```
>const arr = [1,2,3,4.5,"abc"]
>#or
>const clubs = [];
>clubs[0] = "dance";
>clubs[1] = "music";
>```
* Using keyword `new`
```
const arr = new Array(1,2,3.4);
```
### Accessing Array Elements
```
const names = ["Sita", "Ram", "John","Fareed"];
let name = names[0];
#OUTPUT : Sita
```
### Changing an Array Element
```
names[1] = "Riya";
console.log(names[1]);
#OUTPUT : Riya
```
### Access the entire Array at once
```
console.log(names)
#OUTPUT : ["Sita", "Riya", "John","Fareed"]
```
### Array Properties and Methods
* ### Static methods
    * Array.from(arrayLike, mapFn) : Creates a new Array instance from an array-like object or iterable object.
    ```
    console.log(Array.from('foo'));
    #expected output: Array ["f", "o", "o"]
    ```

    * Array.isArray(value) : Returns true if the argument is an array, or false otherwise.
    ```
    Array.isArray([1, 2, 3]);  #true
    ```

* ### Instance Propeties
    * Array.prototype.length : Returns the number of elements in that array. e.g
    ```
    let arr =[1,2,6.7]
    #arr.length = 3
    ```
* ### Instance Methods
    1. Array.prototype.concat() 
    ```
    const array1 = ['a', 'b', 'c'];
    const array2 = ['d', 'e', 'f'];
    const array3 = array1.concat(array2);

    console.log(array3);
    #expected output: Array ["a", "b", "c", "d", "e", "f"]
    ```    
    2. Array.prototype.every() : Tests whether all elements in the array pass the test. It returns a Boolean value.
    ```
    const isBelowThreshold = (currentValue) => currentValue < 40;

    const array1 = [1, 30, 39, 29, 10, 13];

    console.log(array1.every(isBelowThreshold));
    #expected output: true
    ```
    3. Array.prototype.fill() 
    ```
    const array1 = [1, 2, 3, 4];

    #fill with 0 from position 2 until position 4
    console.log(array1.fill(0, 2, 4));
    #expected output: [1, 2, 0, 0]
    ```
    4. Array.prototype.filter() : Creates a new array with all elements that pass the test implemented by the provided function.
    ```
    const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

    const result = words.filter(word => word.length > 6);

    console.log(result);
    #expected output: Array ["exuberant", "destruction", "present"]
    ```
    5. Array.prototype.find() :  Returns the first element in the provided array that satisfies the provided testing function.
    ```
    const array1 = [5, 12, 8, 130, 44];

    const found = array1.find(element => element > 10);

    console.log(found);
    #expected output: 12

    ```
    6. Array.prototype.forEach() : The forEach() method executes a provided function once for each array element.
    ```
    const array1 = ['a', 'b', 'c'];

    array1.forEach(element => console.log(element));

    #expected output: "a"
    #expected output: "b"
    #expected output: "c"
    ```
    7. Array.prototype.includes() : Determines whether an array includes a certain value among its entries, returning true or false as appropriate.
    ```
    const array1 = [1, 2, 3];
    console.log(array1.includes(2));
    #expected output: true
    ```
    8. Array.prototype.indexOf() : The indexOf() method returns the first index at which a given element can be found in the array, or -1 if it is not present.
    ```
    const beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];

    console.log(beasts.indexOf('bison'));
    #expected output: 1
    ```
    9. Array.prototype.join() : The join() method creates and returns a new string by concatenating all of the elements in an array (or an array-like object), separated by commas or a specified separator string.
    ```
    const elements = ['Fire', 'Air', 'Water'];

    console.log(elements.join());
    #expected output: "Fire,Air,Water"

    console.log(elements.join(''));
    #expected output: "FireAirWater"
    ```
    10. Array.prototype.lastIndexOf() : Returns the last index at which a given element can be found in the array, or -1 if it is not present.
    ```
    const animals = ['Dodo', 'Tiger', 'Penguin', 'Dodo'];

    console.log(animals.lastIndexOf('Dodo'));
    #expected output: 3
    ```
    11. Array.prototype.map() : The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.
    ```
    const array1 = [1, 4, 9, 16];

    #pass a function to map
    const map1 = array1.map(x => x * 2);
    console.log(map1);
    #expected output: Array [2, 8, 18, 32]
    ```
    12. Array.prototype.pop() : The pop() method removes the last element from an array and returns that element.
    ```
    const plants = ['broccoli', 'cauliflower', 'cabbage', 'kale', 'tomato'];

    console.log(plants.pop());
    #expected output: "tomato"

    console.log(plants);
    #expected output: Array ["broccoli", "cauliflower", "cabbage", "kale"]
    ```
    13. Array.prototype.push() : The push() method adds one or more elements to the end of an array and returns the new length of the array.
    ```
    const animals = ['pigs', 'goats', 'sheep'];

    const count = animals.push('cows');
    console.log(count);
    #expected output: 4
    ```
    14. Array.prototype.shift() : The shift() method removes the first element from an array and returns that removed element. This method changes the length of the array.
    ```
    const array1 = [1, 2, 3];

    const firstElement = array1.shift();

    console.log(array1);
    #expected output: Array [2, 3]
    ```
    15. Array.prototype.unshift() : The unshift() method adds one or more elements to the beginning of an array and returns the new length of the array.
    ```
    const array1 = [1, 2, 3];

    console.log(array1.unshift(4, 5));
    #expected output: 5
    ```
    16. Array.prototype.slice() : The slice() method returns a shallow copy of a portion of an array into a new array object selected from start to end (end not included).
    const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];
    ```
    console.log(animals.slice(2));
    #expected output: Array ["camel", "duck", "elephant"]

    console.log(animals.slice(2, 4));
    #expected output: Array ["camel", "duck"]
    ```
    17. Array.prototype.sort() : The sort() method sorts the elements of an array in place and returns the sorted array.
    ```
    const months = ['March', 'Jan', 'Feb', 'Dec'];
    months.sort();
    console.log(months);
    #expected output: Array ["Dec", "Feb", "Jan", "March"]
    ```
    18. Array.prototype.splice() : The splice() method changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.
    ```
    const months = ['Jan', 'March', 'April', 'June'];
    months.splice(4, 1, 'May');
    #replaces 1 element at index 4
    console.log(months);
    #expected output: Array ["Jan", "Feb", "March", "April", "May"]
    ```

## Set
The Set object lets you store unique values of any type, whether primitive values or object references.
|Method| Description| example |         |
| ---- | -----------| ------  | ------- |
|new Set()|	Creates a new Set|const letters = new Set(["a","b","c"]);|
|add()	|Adds a new element to the Set|letters.add("a");|
|delete()|	Removes an element from a Set| letters.delete("b")|
|has()	|Returns true if a value exists in the Set| letters.has("a")|
|forEach()|	Invokes a callback for each element in the Set|letters.forEach (function(value) {text += value;})|
|values()|	Returns an iterator with all the values in a Set| letters.values() |

|Property|	Description|
| -----  | ------------|
|size	|Returns the number of elements in a Set|
## Object
The Object class represents one of JavaScript's data types. It is used to store various keyed collections and more complex entities. Objects can be created using the Object() constructor or the object initializer / literal syntax.
### Create an object
```
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
  fullName:	function() {return this.firstName + " " + this.lastName;}
};
```
### Accessing Object Properties
Syntax : *objectName.propertyName* or *objectName["propertyName"]*
>
e.g 
```
person.lastName;
person["lastName"];
```
### `this` Keyword
* In an object method, `this` refers to the object.
* Alone, `this` refers to the global object.
### Accessing Object Methods
You access an object method with the following syntax:
Syntax : *objectName.methodName()*
>
e.g
```
name = person.fullName();
```

## Map
A Map holds key-value pairs where the keys can be any datatype.

A Map remembers the original insertion order of the keys.
|Method|	Description|
|------|   ----------  |
|new Map()|	Creates a new Map|
|set()|	Sets the value for a key in a Map||
|get()|	Gets the value for a key in a Map|
|delete()|	Removes a Map element specified by the key|
|has()	|Returns true if a key exists in a Map|
|forEach()|	Calls a function for each key/value pair in a Map|
|entries()|	Returns an iterator with the [key, value] pairs in a Map|

|Property|	Description|
| -----  | ---------   |
|size|	Returns the number of elements in a Map|

1.Create a Map
```
// Create a Map
const fruits = new Map([
  ["apples", 500],
  ["bananas", 300],
  ["oranges", 200]
]);
```
2. Add elements to a Map
```
const fruits = new Map();

// Set Map Values
fruits.set("apples", 500);
fruits.set("bananas", 300);
fruits.set("oranges", 200);
```
3. Get the value of a key in a Map
```
fruits.get("apples");    // Returns 500
```
4. Return the number of elements in a Map
```
fruits.size;
```
5. Remove a Map element:
```
fruits.delete("apples");  
```
6.  Find if a key exists in a Map:
```
fruits.has("apples");
```
7. Call a function for each key/value pair in a Map
```
// List all entries
let text = "";
fruits.forEach (function(value, key) {
  text += key + ' = ' + value;
})
```
## References
* [w3schools](https://www.w3schools.com/js/js_maps.asp)
* [developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)