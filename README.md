# Maps and Set Exercise 
### Quick Question #1
What does the following code return?
```javascript
new Set([1,1,2,2,3,4])
```
### Solution #1
Return iterable object with uniques values
```javascript
{
1,2,3,4
}
```

===

### Quick Question #2
What does the following code return?
```javascript
[...new Set("referee")].join("")
```
### solution #2 
return string 
```javascript
ref
```

===

### Quick Questions #3
What does the Map m look like after running the following code?
```javascript
let m = new Map();
m.set([1,2,3], true);
m.set([1,2,3], false);

```
### solution #3
```javascript

{
  [1,2,3]: true
  [1,2,3]: false
}
```

=== 

### hasDuplicate
Write a function called hasDuplicate which accepts an array and returns true or false if that array contains a duplicate
```javascript
hasDuplicate([1,3,2,1]) // true
hasDuplicate([1,5,-1,4]) // false
```
### hasDuplicate Solution
```javascript
function hasDuplicate(arr){
  return [...new Set(arr)].length === arr.length ? true : false
}

const hasDuplicate = arr => [..new Set(arr)].length === arr.length ? true : false
```

=== 

### vowelCount
Write a function called vowelCount which accepts a string and returns a map where the keys are numbers and the values are the count of the vowels in the string.
```javascript
vowelCount('awesome') // Map { 'a' => 1, 'e' => 2, 'o' => 1 }
vowelCount('Colt') // Map { 'o' => 1 }
```
### vowelCount Solution 
```javascript 
function vowelCount(str){
   return new Map(Object.entries(Array.from(str).filter(vow => "aeiou".indexOf(vow) > -1)
   .reduce((acc,next)=>{
     acc[next] = (acc[next] || 0) + 1
     return acc
   },{})))
}

function vowelCount(str){
  const myMap = new Map()

  for(let char of str){
    const lowerChar = char.toLowercase()
    if("aeiou".includes(lowerChar)){
      if(myMap.has(lowerChar)){
        myMap.set(lowerChar,myMap.get(lowerChar) + 1)
      }else{
        myMap.set(lowerChar,1)
      }
    }
  }

  return myMap
}
```