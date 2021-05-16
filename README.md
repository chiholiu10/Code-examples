```javascript
function rotateImage(a) {
    let rotateMatrix = a[0].map((values, index) => a.map(row => row[index]).reverse());
    return rotateMatrix 
}

rotateImage(a = [[1, 2, 3],
     [4, 5, 6],
     [7, 8, 9]])
```

```javascript
function firstNotRepeatingCharacter(s) {
    for(let i = 0; i < s.length; i++) {
        let char = s[i];
        
        if(s.indexOf(char) === i && s.indexOf(char, i + 1) === -1) {
            return char;
        }
    }
    return "_";
}

console.log(firstNotRepeatingCharacter('bbooop'))
```

```javascript
function firstDuplicate(arr) {
    const memory = {};
    
    for(let i = 0; i < arr.length; i++) {
        if(memory[arr[i]] !== undefined) {
            return memory[arr[i]];
        } else {
            memory[arr[i]] = arr[i]
        }
    }
    return -1;
}


firstDuplicate([2, 1, 3, 5, 3, 2])
```

```javascript
var lengthOfLongestSubstring = function(s) {
    let longest = 0;
    let current = "";
    
    for (let i = 0; i < s.length; i++) {
        current = current.substring(current.indexOf(s[i]) + 1)        
        current += s[i];
        
        if (current.length > longest) {
            longest = current.length;
        }
    }
    
    return longest;
};
```

```javascript
let p = new Promise((resolve, reject) => {
  let a = 2;
  if(a === 2) {
    console.log('Success');
  } else {
    console.log('Failed')
  }
});

p.then((message) => {
  console.log(message)
}).catch((message) => {
  console.log(message)
})
```

Example of a callback
```javascript 
const message = () => {
  console.log('Function is called after 3 seconds');
}

setTimeout(message, 2000)
```

```javascript 
// call, apply and bind
const test = {
  name: "Bob",
  surname: "Janssen"
}

let refer = function(extra) {
    console.log('Hello I am ' + this.name + " and my surname is " + this.surname + "and this is a" + extra);
  }

const test2 = {
  name: "Chiho",
  surname: "Liu"
}

// borrow function
refer.call(test2, 'call');
refer.apply(test2, ['applyFunction']);

// bind method
let bindFunc = refer.bind(test2, 'bind');
bindFunc();
```

```javascript
function isCryptSolution(crypt, solution) {
       let hasLeadingZeros = false;
    const decrypted = crypt.map(word => {
        const number = word.split('').map(letter => {
            return solution.find(key => key[0] === letter)[1];
        }).join('');
        
        if (number.startsWith('0') && number.length > 1) {
            hasLeadingZeros = true;
        }
        
        return Number.parseInt(number);
    });
    
    
    return !hasLeadingZeros && decrypted[0] + decrypted[1] === decrypted[2];
}

console.log(isCryptSolution(["SEND", 
 "MORE", 
 "MONEY"],
[["O","0"], 
 ["M","1"], 
 ["Y","2"], 
 ["E","5"], 
 ["N","6"], 
 ["D","7"], 
 ["R","8"], 
 ["S","9"]]));
```

```javascript
function removeKFromList(l, k) {
    let head = l
    let previous = null

  while(l){
    if(l.value === k){            
      if(previous===null){
          head = l = l.next
          continue
      } else {
          previous.next = l.next
          l = l.next
          continue
      }
    }
    previous = l
    l = l.next
  }
  return head
}
```

```javascript 
var findMedianSortedArrays = function(nums1, nums2) {
    const mergedArray = nums1.concat(nums2).sort((a, b) => a - b);
    const half = Math.floor(mergedArray.length / 2);
    
    if(mergedArray.length % 2) {
        // uneven length 1, 3, 5
        return mergedArray[half];
    } else {
        // ((3 - 1) + 3) / 2
        return (mergedArray[half - 1] + mergedArray[half]) / 2;
    }
};

findMedianSortedArrays([1,2], [3,4]);

```

```javascript
var combinationSum = function(candidates, target) {
  const output = [];
   //The goal is to use backtracking to find all combinations.
  const findCombination = (remain, path, start) => {
    if (remain < 0) {
      return;
    }
    if (remain === 0) {
      output.push([...path]);
      return;
    }
    for (let i = start; i < candidates.length; i++) {
      // create a new path array to run the subroutine. It's
      // cleaner than pushing and then reseting the array in 
      // javascript.
      findCombination(remain - candidates[i], [...path, candidates[i]], i);    
    }
  }
  findCombination(target, [], 0);
  return output;
};

```

```javascript
    const arr = [1, 2, 3, 4, 100];

const findMaxMin = (arr) => {
  let max = Math.max(...arr);
  let min = Math.min(...arr);
  
  return {
    "max": max,
    "min": min
  }
}
findMaxMin(arr);
```

```js
var missingNumber = function(nums) {
    let numsLen = nums.length;
    let expectedSum = 0;
    let actualSum = 0;
    for(let i = 0; i < numsLen; i++) {
        expectedSum += i + 1;
        actualSum += nums[i];
    }
    return expectedSum - actualSum;
};

missingNumber([9,6,4,2,3,5,7,0,1])
// missing number 8 
// when for instance [0], the output should be 1
```

```js
isPalindrome("racecar"); // true
isPalindrome("race Car"); // true

function isPalindrome(word) {
  // Replace all non-letter chars with "" and change to lowercase
  var lettersOnly = word.toLowerCase().replace(/\s/g, "");

  // Compare the string with the reversed version of the string
  return lettersOnly === lettersOnly.split("").reverse().join("");
}
```

```js
const es5 = {
  name: "Chiho",
  surName: "Liu",
  allName: function() {
    console.log(this.name); 
      var self = this;
      setTimeout(function() {
        console.log('es5 works now' + self.name)
      }, 1000)
  }
}

es5.allName();


const es6 = {
  name: "Chiho",
  surname: "Liu",
  allName: function() {
    console.log(this.name);
    setTimeout(() => {
      console.log('es6 works ' + this.name)
    })
  }
}

es6.allName();
```
