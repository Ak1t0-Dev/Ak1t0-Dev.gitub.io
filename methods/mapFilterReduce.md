# The methods use for manipulating the data of array


# map
> The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.

```javascript
const array = [1, 2, 3, 4];
const resultMap = array.map(item => item * 2);
console.log(resultMap); // [2, 4, 6, 8]
```

In the example above, you can see that inside the map method has a parameter (which is named item) and takes each element of the array in the function.  

# filter
> The filter() method creates a shallow copy of a portion of a given array, filtered down to just the elements from the given array that pass the test implemented by the provided function.

```javascript
const array = ['abc', 'abcd', 'abcde', 'abcdef', 'abcdefg'];
const resultFilter = array.filter(item => item.length < 5);
console.log(resultFilter); // ['abc', 'abcd']
```

As in the description, the filter method is a shallow copy, so if you change the original array, you will get the changed result because of sharing the same references.  

# reduce
> The reduce() method executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.  

```javascript
const array = [1, 2, 3, 4, 5];

const initialValue = 1;
const resultReduce = array.reduce(
  (accumulator, currentValue) => accumulator * currentValue,
  initialValue
);

console.log(resultReduce); // 120
```

As a side note, "reducer" is a function that accepts two arguments and base on those two arguments, returns a new state value.  
In the above example, the default value of "accumulator" will be "intialValue" and then the result of the calculation at each element is assigned to "accumulator". Finally, the sum of the results is returned.

Besides, an accumulator and a current value, reduce can have a current index and an array itself as a parameter.  

```javascript
array.reduce(
  (accumulator, currentValue, currentIndex, array) => { /*...*/ }
  initialValue
);
```

### reference
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce
