# Learning Swift for iOS Development

What you Need:

- XCode (Apple's first-party IDE) on your Mac in App Store
- Cocoapods `brew install cocoapods` (Package Manager for Apple)

## Creating New Project

As a beginner, you would want to create a App Playground to learn the basics of creating an app. But as time goes on, you would want to create your own project.

## 2 Different UIs for iOS development

1. SwiftUI
2. UIKit

SwiftUI is currently new, therefore it is good to learn both UIKit and SwiftUI

# Introduction to the Swift Language

### Recomended Resources

1. [The Swift Programming (By Apple Inc)](https://books.apple.com/us/book/the-swift-programming-language-swift-5-7/id881256329)
2. [Swift Playground App](https://apps.apple.com/us/app/swift-playgrounds/id908519492)

### Swift Data Types

Data Types are essentials of any programming languages we learn, these are what data types are in Swift fundamentally and how we could utilise them.

```swift
var highscore: Int = 0 //Type Integer
var percentHigh: Double = 0.76 // Double, precision to 15dp
var percentLow: Float = 0.33 // Float, precision to 6dp
var thoughts: String = "David" // Type String
var smart: Bool = false // Type bool, true or false
```

There are many other types in Swift, we can create our own types through classes or structs like `var david : Person = Person(named: "david")`

Swift is also smart to do a **Type Inferencing** without explicitly stating its data typing. For example `var highscore = 0` it automatically knows the type is Integer.

### Swift Variable & Constants

Variables and Constants capture values and stores them in the codebase.

Variables -> Values are mutable (they can be changed)

Constants -> More Safety and Performant, but immutable (Values can't be changed)

```swift
var highscore = 0 // Variable
highscore = 100 // Can Happen
let name = "david" // Constant
name = "huan yin" // Cannot Happen, IDE will show error
```

### Swift Array

Arrays are an important data structure for any programming language.
Arrays are like an list of values stored in a variable/constant. They are ordered, meaning their positions of the values are fixed.

```swift
var ages: [Int] = [] // Can declare it this way
var ages = [21, 23, 42, 22] // or this way
ages.count // will show length of array, it will show 4
ages.first // show the first index of the array, 21
ages.last // show last index, 22
ages[2] // shows the third index, 42 (first index is always 0)

ages.append(99) // add 99 to the end of the array
ages.insert(55, at:2) // add 55 at index 2 in the array
```

### Swift Sets

Sets are another data structures important for any programming languages. Similar to arrays that they store a list of values. However, they are unordered and also does not allow any duplicates. They are usually much more performant in speed by having faster data lookup time.

```swift
var ages = [12, 32, 23, 12] // Have 12 as duplicate
// var agesSet: Set<Int> = [] can declare it this way
var agesSet = Set(ages) // the order is gone and also will only have one 12

agesSet.contains(12) // true
ageSet.insert(101) // no append or at where cause unordered
```

Order is not guaranteed cause it has to conform to `Hashable` in order for any values to be inserted into a set. That is why Sets are faster as it looks up in constant time compared to arrays will check through the length of the array.

### Swift Dictionary

Dictionaries are an important data structure. Dictionary are a collection of data with labels with them, often called a key-value pair. `[key: value]`
Like a real life dictionary where the word is the key and the definition being the value.

```swift

let devices: [String: String] = [
	"phone": "iPhoneX",
	"laptop": "Macbook Pro",
	"tablet": "iPad Pro"
] // dictionary are initialised something like this

devices["laptop"] // to look up value of laptop
```

It has a constant lookup time, similar to sets.

### Swift Functions

Functions are compartmentalised sets of code. Functions are mainly used for reusable codes.

```swift
func printName(){
	return "David Koh"
} // defining the function

printName() // functional call

func printParamName(name: String){
	return name
} // defining function with parameters/arguments

printParamName(name: "huan yin") // function call

func add(firstNum: Int, to secondNum:Int) -> Int {
	return firstNum + secondNum
} // function with argument label and function signature

add(firstNum: 2, to: 1)
```

### Swift If/else statements

If-else statements are mainly used in control flows of the codebase. They provide conditions on how the code should flow.

```swift
var isDarkModeOn = true
// if isDarkModeOn == true
if isDarkModeOn {
	return "Dark Mode On"
} else{
	return "Light Mode attract bugs"
}

var highscore = 100
if highscore > 500{
	return "Good"
} else if highscore > 250 {
	return "Not Bad"
} else {
	return "Try better next time"
}
```

Anything that can evaluates into a true or false can be a conditional. A == operator is used as a comparator between the value and the compared value to ascentain the truth of the logic.

### Swift Iterative Loops

For this guide, I will only show For Loops as it would be the iterative loops that we would use 95% of the time. There are while loops and repeat..while loops as well but those are not often used.

```swift
/**
** For Loops
**/
let allStars = ["James", "Lebron", "Kobe", "Bryant"]

for players in allStars{
	print(players) // will print the entire list
}

for players in allStars where players == "Lebron"{
	print(players) // will only print Lebron
}

for i in 0...3{ // For looping in ranges [0,3]
	print(i)
}

for i in 0..<3 { // Looping in ranges [0,3)
	print(i)
}
```

### Swift Enums

Enums are a set of constant values that are related with one another with type safety. Enums would improve on code readability as well.

```swift
enum Phone: String{
	case iPhone11 = "this is my phone"
	case iPhoneSE = "Phone is too small"
	case pixel = "pixel is good"
	case nokia "you're old school"
}

func getOpinion(on phone: Phone){
	print(phone.rawValue)
}

getOpinion(on: .pixel) // will return pixel is good

```

### Swift Switch-Case

Switch statements behaves like if-else statement and oftenly paired with enums.
It is a neater and cleaner way to write a if-else statement.

```swift
 let ELORank = 300

 func determinePlayerLeague(from rank: Int){
	switch rank{
		case 0:
			print("Play a game")
		case 1..<50:
			print("Bronze League")
		case 50..<100:
			print("Silver League")
		case 100..<350:
			print("Gold League")
		default:
			print("League of your own")
	}
 }

 determinePlayerLeague(from: ELORank) // will return Gold League
```

### Swift Operators

There are multiple operators in Swift. `+` is the addition operator, `-` is the subtraction operator, `*` is the multiplication operator and `/` is the division operator. One thing to note about Math operator are its data type whether it's a Int or a Float/Double especially when it comes with division.

There's special operators like `%` modulo operator gives the remainder. `==` is a comparator operator which evaluates the 2 values whether its true or false. There's also `!` operator which negates the conditional from true to false, It can also be appended to become `!=` operator stating "not equals to".

There's also comparators operators such as `&&` and `||` which means the AND operator and OR operator. AND operator means all conditions have to be true for the code to execute, OR operator means one of the condition can be true for the code to execute.

There's one last important operator called the `?` optional operator which allows the value to be nil. It allows the developer to unwrap the optional.
