# Big O Notation, what is it ?

The Big O Notation are a set of notations that aim to say how much a function or algorithm is scalable in relation to the execution time, thus it is categorized into several types of notations that are: constants O(1), linear O(n ), quadratics O(n^2), logarithms O(log n) , exponentials O(2^n) and factorials O(n!)

## Why is Big O important ?

The importance of big o regarding the creation of a code is to determine what is the best way to use the data in relation to the performance of the time, that's why it is usually used in the creation or refactoring of codes that manipulate data, which are usually involved in loops , for this reason it is important that your scalability is at high performance, or the best possible performance for that situation

#### Example in the algorithm

As an example, I'm going to use a function with algorithmic scalability, but you don't need to pay attention to the terms, but to the example and the use of the function.

This function aims to find an element without an array.

```js
const findElement = (array, element) => {

let elementFind

  for(let j = 0; j < array.length; j++){
      for (let i = 0; i < array.length; i++){
        if (element === array[i]) {
          elementFind = array[i]
        }
      }
  }

  return elementFind || 'There is no such element in the array'
}
```

What do you think of her ? Does it look optimized?

If you don't know the concepts of time complexity you may say that you don't have any problem with it, or that maybe one adjustment or another would be good, but I'll tell you for sure! This function is not performance-optimized with respect to its runtime and data handling.

Note, for each element that the forEach is passing from the array, a new for loop will be performed to finally compare the element and find it, Big O Notation would say that this situation is an 
O(n^2) but don't worry about the notation, I'll explain it again later.

Now look at this other function

```js
const findElement = (array, element) => {

  let elementFind

  for (let i = 0;  i < array.length; i++) {
    if (element === array[i]) {
      elementFind = array[i]
    }	
  }

  return elementFind || 'There is no such element in the array'
}
```

Now this is actually optimized, using only one loop for the same purpose, thus saving time and data usage.

It is still possible to optimize through the javascript find method, this method executes a loop checking if the requested condition is true, if it is the current loop element it will be returned, avoiding going to the end of the loop as our previous functions did.

The function would look like this:

```js
const findElement = (array, element) => {
  return array.find(currElement => currElement === element) ||  'There is no such element in the array'
}
```

## Constants O(1)

Constant algorithms or constant functions are those whose performance time will always be the same, in the case of a function, regardless of the number of entries in it, the time to execute it will be the same.

Note this function:

```js
const firstElement = (array) => {
  return array[0]
}

console.log(firstElement([0,1,2]))
// expected output: 0
```

Regardless of the number of elements in the array, this function will always return its first element, so its execution time will always be constant.

Another example of O(1) using javascript methods is the shift method, which will always remove the first element of the array, no matter how big the array is.

```js
const array1 = ["Green", "Blue", "Purple", "Black", "White", "Pink"]

array1.shift() 

console.log(array1)

// expected output: ["Blue", "Purple", "Black", "White", "Pink"]
```

#### Why does this constancy happen?

Methods such as forEach, find, map, filter, etc... Go through the elements of the array, this makes the amount of elements that will be traversed to increase depending on the amount in your input, this makes the runtime increase and consequently its complexity. However, in an O(1) notation method or algorithm, if there is one or more elements in its input, the execution will be at the same time, this happens because most of the times it is a method with fixed manipulation, that is, it it is always executed with the same element, the one that does not need to be traversed.

Note: The methods that occur in loop will be explained later
#### Demo chart

In this graph we can see the performance of operations by elements, later I will explain about the other notations, but note that the blue line that demonstrates the O(1) notation and note that regardless of the amount of incoming elements, the amount of operations remain the same and hence the runtime.

![o(1)](graphic.png)
