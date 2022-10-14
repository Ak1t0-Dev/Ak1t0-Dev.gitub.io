# Splice() and Slice()

Let's find out how to use a splice and slice method.  
This two methods are used for an array when you want to manipulate it.  

## splice(start<font color="blue">, deleteCount, item1, item2, itemN</font>)  
This method can change the contents of an array such as removing, replacing, and adding elements with using in-place.  
The method will overwrite the origin array so additional memory is hardly used.  

    start: set an index which is start of the change
    deleteCount: the number of elements to remove from start
    item1, …, itemN: the elements to add to the array from start
    return value: this method itself return the deleted elements

**・the case that deleteCount is unspecified**  
&emsp;If deleteCount is unspecified, the delete range will be to the end of the array.  
```JavaScript
let fruits = ["apples", "bananas", "grapes", "oranges", "strawberries"];
console.log(fruits.splice(0)); // [ 'apples', 'bananas', 'grapes', 'oranges', 'strawberries' ]
console.log(fruits); // []
```

**・the case that deleteCount is specified**  
&emsp;If deleteCount is specified, the end of the delete range will be the number counting from the start  
&emsp;In the code below, start position is specified by 1 so the beginning of the delete range will start from the index[1].  
```JavaScript
let fruits = ["apples", "bananas", "grapes", "oranges", "strawberries"];
console.log(fruits.splice(1, 2)); // ['bananas', 'grapes' ]
console.log(fruits); // [ 'apples' ,'oranges', 'strawberries' ]
```

**・the case that items are specified**    
&emsp;The items will be added from the start position.  
&emsp;In the code below, "apples" (fruits[1]) and "kiwis" (fruits[2]) were removed and items ("kiwis" and "mangoes") were added from fruits[1], which was the start position.  
```JavaScript
let fruits = ["apples", "bananas", "grapes", "oranges", "strawberries"];
console.log(fruits.splice(1, 2, "kiwis", "mangoes")); // [ 'bananas', 'grapes' ]
console.log(fruits); // [ 'apples', 'kiwis', 'mangoes', 'oranges', 'strawberries' ]
```

**・the case that start is a negative number**  
&emsp;A negative number will be started from the end of the array to the beginning.  
&emsp;-1 refers index[n], -2 refers index[n-1], -3 refers index[n-2], ...  
&emsp;In the code below, start position is -2 and deleteCount is 2 so the delete range will be the second from end to end.  
```JavaScript
let fruits = ["apples", "bananas", "grapes", "oranges", "strawberries"];
console.log(fruits.splice(-2, 2)); // [ 'oranges', 'strawberries' ]
console.log(fruits); //[ 'apples', 'bananas', 'grapes' ]
```

## slice(<font color="blue">start, end</font>)  
This method can extract the elements from array without using in-place (not in-place).

    start: set an index which is start of the exraction
    end: set an index which is end of the exraction (the end element will not be included in the exraction)
    return value: A new array containg the extracted elements


**・the example using slice()**  
&emsp;In the code below, the exraction range will be fruits[0] to fruits[2]. (the end position 3 is excluded)
&emsp;slice() method is not in-place so origin of the array is not modified.
```JavaScript
let fruits = ["apples", "bananas", "grapes", "oranges", "strawberries"];
console.log(fruits.slice(0, 3)); // [ 'apples', 'bananas', 'grapes' ]
console.log(fruits); // [ 'apples', 'bananas', 'grapes', 'oranges', 'strawberries' ]
```

**・the case using a negative number**  
&emsp;A negative number will be started from the end of the array to the beginning.  
&emsp;-1 refers index[n], -2 refers index[n-1], -3 refers index[n-2], ...  
&emsp;In the code below, the exraction range will be fruits[3], which is the second element from end, to fruits[4]. (the end position 5 is excluded)
```JavaScript
let fruits = ["apples", "bananas", "grapes", "oranges", "strawberries"];
console.log(fruits.slice(-2, 5)); // [ 'oranges', 'strawberries' ]
```

### references
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice