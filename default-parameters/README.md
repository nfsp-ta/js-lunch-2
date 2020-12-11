# Default Parameters
## Intro

Javascript introduced default function parameters as part of the ES2015 spec. This allows setting a value for a function parameter that is used is a value is not provided by the caller.

## The Old Way

```javascript
function multiply(a, b) {
  return a * b
}

multiply(5, 2)  // 10
multiply(5)     // NaN !
```

```javascript
function multiply(a, b) {
  if(b === undefined)  {
      b = 1
  }
  
  return a * b
}

multiply(5, 2)  // 10
multiply(5)     // 5
```

## Why are Default Parameters Needed?
Default parameters are a simpler syntax for ensuring a default value is used if one is not provided. It also allows for better tool support as the optional nature of the parameters is explicit as is the overall number of supported parameters.

## The New Way
```javascript
function multiply(a, b = 1) {
  return a * b 
}

multiply(5, 2)          // 10
multiply(5)             // 5
multiply(5, undefined)  // 5
multiply(5, null)       // 0??
```
## Is there an equivalent in C#/Java?
* C#
```c#
public void Multiply(int a, int b = 10) {
    return a * b;
}
```

## Potential Pitfalls
default parameters are only used if the value received is undefined whether by not passing anything or by passing undefined explicitly. Passing null will not result in the default value being used and if this is desired a runtime check within the function is required.

## Q & A
