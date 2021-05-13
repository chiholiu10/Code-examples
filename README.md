```javascript
function rotateImage(a) {
    let rotateMatrix = a[0].map((values, index) => a.map(row => row[index]).reverse());
    return rotateMatrix 
}
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


