```javascript
function rotateImage(a) {
    let rotateMatrix = a[0].map((values, index) => a.map(row => row[index]).reverse());
    return rotateMatrix 
}

rotateImage(a:
[[1,2,3], 
 [4,5,6], 
 [7,8,9]])
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
const lengthOfLongestSubstring = (s) => {
    let map = {}
    let start = 0
    let maxLen = 0
    let arr = s.split('')
    
    for (i=0; i < s.length; i++) {
        let current = map[arr[i]]
        if (current!== undefined && start <= current) {
            start = current + 1
        } else {
            maxLen = Math.max(maxLen, i - start + 1)
        }
        
        map[arr[i]] = i
    }
    
    return maxLen
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
