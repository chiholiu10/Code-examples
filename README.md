```javascript
function rotateImage(a) {
    let rotateMatrix = a[0].map((values, index) => a.map(row => row[index]).reverse());
    return rotateMatrix 
}
```
