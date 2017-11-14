## Highest and Lowest
A code wars kata that returns the highest and lowest  number in a string.

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
