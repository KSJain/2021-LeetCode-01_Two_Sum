# 2021-LeetCode-01_Two_Sum

This is a simple solution  to the problem. If you like feel free to  download the  XCode Playground file from the following link

As of posting date the Stats are as following

Feel free to comment and/or improve. I would like to learn and  improve  alongside my peers : ) 

Happy Coding

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
