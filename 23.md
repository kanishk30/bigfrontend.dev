## https://bigfrontend.dev/problem/create-a-sum

```
/**
 * @param {number} num
 */



function sum(num) {
  const innerSum = function(num2) {
    return num2 ? sum(num+ num2) : num;
  } 
  innerSum.valueOf = () => num;
  return innerSum;

}

``
