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
