# Limesharp Developer Test

Please, **don't fork this repo**, clone it or download it locally and then commit changes after each task into a new repo of your own, and send us the link. We will get back to you shortly.

Languages accepted: Javascript or PHP.

### Task 1:

Make this work (repeat 3 times the contents of an array):

```javascript
repeat([1, 2, 3]) //[1,2,3,1,2,3,1,2,3]
```

Your solution:

###### If we type in our console your function and repeat([1,2,3]) then the result should be [1,2,3,1,2,3,1,2,3]

```javascript
const repeat = (array) => {
    let result = []
    for (let step = 0; step < 3; step++) {
        result = [...result, ...array]
    }
    return result
}

repeat([1, 2, 3])
```

### Task 2:

Make this work (no vowels, lowercase except the first letter):

```javascript
reformat('liMeSHArp DeveLoper TEST') //Lmshrp dvlpr tst
```

Your solution:

###### If we type in our console your function and reformat("liMeSHArp DeveLoper TEST") then the result should be Lmshrp dvlpr tst

```javascript
const reformat = (input) => {
    let sansVowels = input.replace(/[aeiou]/gi, '')
    return `${sansVowels.charAt(0).toUpperCase()}${sansVowels
        .substring(1)
        .toLowerCase()}`
}

reformat('liMeSHarp Developer TEST')
```

### Task 3 (optional, for bonus points):

Make this work (without using any built in functions, only a `for` loop, return the next binary number in a string or as an array)

```javascript
next_binary_number([1, 0]) // [1,1]

// possible test cases:
// [1,0] => [1,1]
// [1,1] => [1,0,0]
// [1,1,0] => [1,1,1]
// .......
// [1,0,0,0,0,0,0,0,0,1] => [1,0,0,0,0,0,0,0,1,0]
```

Your solution:

###### If we type in our console your function and next_binary_number([1,0,0,0,0,0,0,0,0,1]) then the result should look like 1,0,0,0,0,0,0,0,1,0 (or as an array).

```javascript
const next_binary_number = (input) => {
    for (let counter = input.length - 1; counter >= 0; counter--) {
        if (input[counter] === 0) {
            input[counter] = 1
            return input
        } else if (input[counter] === 1 && counter !== 0) {
            input[counter] = 0
        } else if (input[counter] === 1 && counter === 0) {
            input[counter] = 0
            input.unshift(1)
        }
    }
    return input
}

next_binary_number([1, 0, 0, 0, 0, 0, 0, 0, 0, 1])
```

---

If you get invited to the first interview read the "What to expect.md" file.
