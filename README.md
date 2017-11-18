## Equal Sides Of An Array

A code wars kata that find the index where the sum of the numbers on the left are equal to the sum of the numbers on the right.

```javascript
function findEvenIndex(array) {
    /**find sum total of array */
    const sum = array.reduce((x, y) => x + y, 0);
    
    /** running total while iterating through array */
    let accumulator = 0;
    for (let i=0; i<= array.length; i++) {
       
        /** test if left and right of present index are equal  */        
        if (accumulator == (sum - array[i]) / 2) {

            /** return index of array when this condition was met */
            return i            
        }
        
        accumulator += array[i];
    }
    /** if nothing found return -1 */
    return -1
}
```

```javascript
findEvenIndex([1,2,3,4,3,2,1]) // returns 3
findEvenIndex([1,100,50,-51,1,1])// returns 1
findEvenIndex([1,2,3,4,5,6]) // returns -1
findEvenIndex([20,10,30,10,10,15,35]) // returns 3
```

## Square Every Diget

Take every diget and square it and then join together

```javascript
function squareDigits(num){
  const str = num
     .toString()
     .split('')
     .map(x => (x * x)) 
     .join('')
     
     const result = parseInt(str, 10)
     
     return result    
     }
```
```javascript
     squareDigits(9119) // returns 811181
```


## Highest and Lowest

A code wars kata. The function returns the highest and lowest number in a given string.

```javascript
function highAndLow(numbers){
const array = numbers.split(' ')
  const max = Math.max(...array);
  const min = Math.min(...array);
  return max + " " + min;
  ```

```javascript
highAndLow("1 2 3 4 5"); // return "5 1"
highAndLow("1 2 -3 4 5"); // return "5 -3"
highAndLow("1 9 3 4 -5"); // return "9 -5"
```

## The Longest

Take 2 strings s1 and s2 including only letters from a to z. Return a new sorted string, the longest possible, containing distinct letters.

```javascript
function longest(s1, s2) {
  const result = (s1 + s2)
    .split('')
    .filter((el, pos, arr) => arr.indexOf(el) == pos)
    .sort()
    .join('')

  return result
}
```
