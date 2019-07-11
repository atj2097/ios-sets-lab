# Sets lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

Ms. Gabriel Williams is a botany professor at District College. One day, she asked her student Mickey to compute the average of all the plants with distinct heights in her greenhouse.

Input: heights of trees below:
`161 182 161 154 176 170 167 171 170 174`


`169.375`
group heights of trees
add every tree together
divide the sum by the amount of elements 
```swift
var treeHeight: Set<Int> = [162 , 182, 161, 154, 176, 170 , 167 , 171, 170 ,  174]
var sum =  0
var average = 0
for trees in treeHeight {
sum += trees
average = sum / treeHeight.count
}
print(average)


```



## Question 2

Determine if a String is a pangram. A pangram is a string that contains every letter of the alphabet at least once.

e.g `"The quick brown fox jumps over the lazy dog"` is a pangram
e.g `"The quick brown fox jumped over the lazy dog"` is NOT a pangram

create a variable of the alphabet 
```Swift
var alphabetSet: Set<Character> = ["a", "b", "c" , "d" , "e" , "f" ,"g" , "h", "i" , "j", "k", "l" , "m" , "n" , "o" , "p", "q", "r" , "s", "t", "u", "v" , "w" , "x" ,"y" , "z"]
var pangramSet: String = "The quick brown fox jumps over the lazy dog"
var letterCount = 0
var emptySet: Set<Character> = []

for letter in pangramSet.lowercased() {
emptySet.insert(letter)
emptySet.remove(" ")
}
//print(emptySet.count)
//print(alphabetSet.count)
print(emptySet == alphabetSet)


for letter in emptySet {
for letters in alphabetSet {
if emptySet.contains(letters) {
letterCount += 1

}
}
}
print(letterCount)
```
## Question 3

The set S originally contains numbers from 1 to n in ascending order. Unfortunately, due to the data error, one of the numbers in the set was duplicated to another number in the set. This results in the repetition of one number and loss of another number in the set.

You are given an array `nums` representing the data status of the set S after the error occurred. Your task is to first find the number occurs twice and then find the number that is missing from the sequence. Return these two values in the form of an array.

Example 1:
Output: `[2,3]`

Example 2:
Input: `nums = [1,1]`
Output: `[1,2]`

Example 3:
Input: `nums = [2,2]`
Output: `[2,1]` 
```swift
var nums = [1,2,2,4]
var numsSet = Set(nums)
var newNums = [Int]()
print(newNums)
//var numsCount = 0
var numCompare = 0
for (index, number) in nums.enumerated()  {
if number == numCompare  {
newNums.append(numCompare)
nums[index] = numCompare + 1
newNums.append(nums[index])
print(newNums)
}
else {
numCompare = number
}

}
```
## Question 4

Given the 4 arrays of Ints below, create a new array, sorted in ascending order, that contains all the values without duplicates.

```swift
let arr1: Set<Int>  = [2, 4, 5, 6, 8, 10, 12]
let arr2: Set<Int>  = [1, 2, 3, 4, 5, 6]
let arr3: Set<Int>  = [5, 6, 7, 8, 9, 10, 11, 12]
let arr4: Set<Int>  = [1, 3, 4, 5, 6, 7, 9]
let setUnion = (arr1).union(arr2).union(arr3).union(arr4)
let newArray = [setUnion.sorted()]
print(newArray)

using sets
turn these arrays into sets(using casting to Set <Int>)
combine them all using(.union)
why is union important? it will take out the duplicates(make sure there's only one of each value)
using .sorted to put these Ints in ascending order from low to high
```


## Question 5

Perform the following set operations on the lists below:

1. Find the intersection and print the result
2. Find the symmetric difference and print the result
3. Find the union and print the result
4. What is the outcome of subtracting `list2` from `list1`? Print the result

```swift
let list1: Set = [1, 3, 4, 6, 2, 7, 9]
let list2: Set = [3, 7, 13, 10, 4]
print(list1.intersection(list2))
print(list1.symmetricDifference(list2))
print(list1.union(list2))
print(list1.subtracting(list2))
```


## Question 6

What output will be produced by the code below? Select one answer.

```swift
var spaceships = Set()

spaceships.insert("Serenity")
spaceships.insert("Enterprise")
spaceships.insert("TARDIS")
spaceships.insert("Serenity")

print(spaceships.count)
//- This code will not compile
```

## Question 7

What output will be produced by the code below?

```swift
var spaceships1 = Set()

spaceships1.insert("Serenity")
spaceships1.insert("Enterprise")
spaceships1.insert("TARDIS")

let spaceships2 = spaceships1

if spaceships1.isSubset(of: spaceships2) {
print("This is a subset")
} else {
print("This is not a subset")
}
- This code will not compile
```

