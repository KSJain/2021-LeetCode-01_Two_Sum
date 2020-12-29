This is a simple solution to the famous "2 Sum" problem. If you like feel free to  download and  tinker with the XCode Playground file from my Github repository link https://github.com/KSJain/2021-LeetCode-01_Two_Sum

I would be perodically keep solving as many questions  as I could, to keep everyday interesting. I miss school days.

### As of posting date the Stats are as following
**Runtime**: 36 ms, faster than 73.77% of Swift online submissions for Two Sum.
**Memory Usage**: 14.4 MB, less than 39.16% of Swift online submissions for Two Sum.

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
