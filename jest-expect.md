### https://bigfrontend.dev/problem/jest-assertion/discuss?sort=time

```
/**
 * interface Matcher {
 *  toBe(data: any): void
 * }
 */
/**
 * @param {any} input
 * @returns {Matcher & {not: Matcher}}
 */
function myExpect(input) {
  // your code here
  
  function toBe(expected, negate=false) {
    if(!negate && !Object.is(input, expected)) {
       throw Error()
    }
    if(negate && Object.is(input, expected)) {
       throw Error()
    }
    return true;
  }

  return {
    toBe,
    not: {
      toBe: (value) => {
        return toBe(value, true)
      }
    }
  }
  
}
```
