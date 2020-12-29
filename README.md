This is a simple solution to the famous "2 Sum" problem. If you like feel free to  download and  tinker with the XCode Playground file from my Github repository link https://github.com/KSJain/2021-LeetCode-01_Two_Sum

I would be perodically keep solving as many questions  as I could, to keep everyday interesting. I miss school days.

### As of posting date the Stats are as following
**Runtime**: 36 ms, faster than 73.77% of Swift online submissions for Two Sum.
**Memory Usage**: 14.4 MB, less than 39.16% of Swift online submissions for Two Sum.
**Big-O Time Complexity**: O(n)

*Feel free to comment and/or improve. I would like to learn and  improve  alongside my peers : )* 

### Happy Coding

```
func twoSum(_ nums: [Int], _ target: Int) -> [Int] {
    guard nums.count > 1 else { return [-1, -1] }
    
    var directory = [Int: Int]()
    
    for num in nums.enumerated() {
        let counter = target - num.element
        if let otherIndex = directory[counter] {
            return [min(num.offset, otherIndex), max(num.offset, otherIndex)]
        } else {
            directory[num.element] = num.offset
        }
    }
    
    return [-1, -1]
}
```

Code in a nutshell:
1. guard checks if there  are atleast two numbers in the array input, if not eary termination with placeholder result of  invalid indices [-1,-1]
2. Initalize a local directory to store indices corresponding for discovered values in array input (key: number, value: index)
3. Uses swift *for-in loop*, with nums.enumerated(),which gets  captured in num variable as an (element, offset) tuple
4. counter value is determined subtracting current element value from the target value provided to the function
5. directory is  queried for key value : *counter*
5a.If the value exists (*not nil*) it is captured in otherIndex variable and returned in as a pair*. **The function terminates here**
5b. If the value didnt exist (nil value) simply store it for the  future usage
6. Finally if the list is exhausted - meaning no pair was found - return [-1, -1] as a placeholder


Ideally one would return a nil or Result type instead of placeholder value if there was an error. But this  is just an easy code challange :p

**If you like  - come to my page https://codinginferno.com/ for more fun learning. I love to learn while sharing, so feel free to ask.**
