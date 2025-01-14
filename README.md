# Turing_Challenges
Repo created to add all the turing challenges solved

## 1. Frog Question
### Image sourced from Habib-uRehman
![turing coding challange 1](https://github.com/user-attachments/assets/6e7167f1-c3e4-4fcb-ad52-a8252760eb51)

## 1. Solution in JavaScript
```javascript
var frogGame = function(x, s, y) {
    const maxValue = Math.max(...y.concat(x)); // Maximum possible position
    const returnArr = []; // Result array

    for (let i = 0; i < x.length; i++) { // For each frog
        const left = Math.max(0, x[i] - s[i]); // Left bound of tongue range
        const right = Math.min(maxValue, x[i] + s[i]); // Right bound of tongue range
        let count = 0;

        for (let fly of y) { // For each fly
            if (fly >= left && fly <= right) { // Check if within range
                count++;
            }
        }
        
        returnArr.push(count); // Store the result for this frog
    }
    
    return returnArr;
};

console.log(frogGame([1, 4, 5], [2, 3, 5], [2, 3, 5]));
```
### 1. Summary
- **Time Complexity:** \( O(m * n) \)
- **Space Complexity:** \( O(n + m) \)
