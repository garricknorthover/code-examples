## Equal Sides Of An Array

A code wars kata that find the index where the sum of the numbers on the left are equal to the sum of the numbers on the right.

```javascript
function findEvenIndex(array) {
    const sum = array.reduce((x, y) => x + y, 0);
    let accumulator = 0;
    for (let i = 0; i <= array.length; i++) {
        if (accumulator == (sum - array[i]) / 2) {
            return i
        }
        accumulator += array[i];
    }
    return -1
}

/** The reduce method is used to find the sum of the array
 * The next pass of the array is accumulated as it iterates.
 * The condition is met when the accumulator is half of the sum 
 * after the present iteration value is taken away from the sum
 * The final return of -1 is if the condition is never met
 */
```

```javascript
findEvenIndex([1,2,3,4,3,2,1]) // returns 3
findEvenIndex([1,100,50,-51,1,1])// returns 1
findEvenIndex([1,2,3,4,5,6]) // returns -1
findEvenIndex([20,10,30,10,10,15,35]) // returns 3
```

## Exes and Ohs

```javascript
function XO(str) {
    let result = str
        .toLowerCase()
        .split('')
        .reduce((x, y) => {
            if (y == 'x') {
                x++
            }
            if (y == 'o') {
                x--
            }
            return x
        }, 0)

    return result == 0 ? true : false
}
```
```javascript
XO("ooxx") => true
XO("xooxx") => false
XO("ooxXm") => true
XO("zpzpzpp") => true // when no 'x' and 'o' is present should return true
XO("zzoo") => false
```

## Square Every Digit

Take every digit and square it and then join together

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

```javascript
longest("loopingisfunbutdangerous", "lessdangerousthancoding") //returns "abcdefghilnoprstu"
longest("inmanylanguages", "theresapairoffunctions") //returns "acefghilmnoprstuy"
```
