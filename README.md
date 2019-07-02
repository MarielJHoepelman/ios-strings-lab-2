# Strings Lab 2

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.

## Question 1

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
var problem = "split this string into words and print them on separate lines"

// Your code
var problem = "split this string into words and print them on separate lines"
var problemSplit = problem.replacingOccurrences(of: " ", with: "\n")
print(problemSplit)

```

Example

Input:
`var problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```


## Question 2

Given a string `testString` create a new variable called `condensedString` that has any consecutive spaces in `testString` replaced with a single space.

```swift
let testString = "  How   about      thesespaces  ?  "
//condensedString = " How about thesespaces ? "

var condensedString = testString.replacingOccurrences(of: "[ ]+", with: " ", options: .regularExpression)
print(condensedString)
```


## Question 3

Given a string with multiple words. Reverse the string word by word.

Example:

Sample Input: `"Swift is the best language"`

Sample Output: `"language best the is Swift"`

```swift

let testString = "Swift is the best language"
var reversed = testString.split(separator: " ").reversed().joined( separator: " ")
print(reversed)
```


## Question 4

Given a string with multiple words. Write code that prints how many of them are palindromes.

Example:

Sample Input: `"danaerys dad cat civic bottle"`

Sample Output: `2`

```swift
var inputString = "danaerys dad cat civic"
var inputStringSplit = inputString.split(separator: " ")
var counter = 0

for w in inputStringSplit {
    if String(w) == String(w.reversed()) {
        counter += 1
    }
}

print(counter)
```


## Question 5

You are given a string representing an **attendance record** for a student. The record only contains the following three characters:

`'A' : Absent.`

`'L' : Late.`

`'P' : Present.`

If a student has more than one 'A' or more than 2 continuous 'L's that student should not be rewarded. Print true if student is to be rewarded and False if they shouldn't.

Example:

Sample Input: `"PPALLP"`

Sample Output: `true`

```swift
var studentRecord = "APPLLP"
var consecutiveLs = studentRecord.contains("LL")
var aCounter = 0

for c in studentRecord {
    if c == "A" {
        aCounter+=1
    }
}

if aCounter >= 1 && consecutiveLs == true {
    print("Student shall NOT be rewarded!")
} else {
    print("Student shall be rewarded!")
}
```



## Question 6

Given a tuple with two strings. The first string is a **ransom note**, the second string being the characters from a magazine. Determine whether or not you can construct the ransom note using the characters from the magazine.

Each letter from the magazine can only be used once. You can assume all letters are lowercased.

Examples:

Sample Input1: `("a", "b")`

Sample Output1: `False`

Sample Input2: `("aa", "aab")`

Sample Output2: `True`
