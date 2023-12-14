# Dart

## Dart Web

- For installing dart

  - `choco install dart-sdk`

- Get CLI tools of and IDE (or both)

  - `pub global activate webdev`
  - `pub global activate stagehand`

- Create a web app

  - `mkdir darttemp1`
  - `cd darttemp1`
  - `stagehand web-simple`
  - `pub get`

- Run the app

  - `webdev serve`

- CLi Tools

- dart fix --dry-run
- dart fix --apply

* Dart is an object-oriented language with C-style syntax which can optionally trans compile into javascript
  It supports a varied range of programming aids like interfaces, classes, collections, generics and optional typing
  Dart can be extensively used to create single-page applications.

## Dart Features

- Optional, Dynamic Type System
- Single Inheritance
- Multiple Interfaces
- Concurrency with isolates and html5 web workers

## Check your Script online with DartPad

[Dart Pad](https://dartpad.dev/)

## setting local environment

- Install the dart sdk using choco
- download vscode and install dart extension
- dart2js

## identifiers in Dart

- Identifiers are names given to elements in a program like variable functions etc. The rules are identifiers are-
  Identifiers can include both characters and digits, however, the identifier cannot begin with a digit.
- Identifiers cannot include special symbols except for underscore (\_) or a dollar sign(\$)
- Identifiers cannot be keywords
- They must be unique
- Identifiers are case-sensitive
- Identifiers cannot contain spaces.

## Keywords in Dart

## Comments in Dart

- Single Line Comments: (//)
- Multi LIne COmments: (/\* \*/)

## Object Oriented Programming in Dart

- Object Oriented is a software development paradigm that follows real-world modelling. Object orientation considers a program as a collection of objects that communicate with each other via mechanism called methods.
- **Object** - An object is a real-time representation of any entity as per Grady, Brooch, Every object must have three features
  - **State** - Describes by the attributes of an object
  - **Behavior** - Describes how the object will act
  - **Identify** - a unique value that distinguishes an object from a set of similar such objects
- **Class** - A class in terms of OOP is a blueprint for creating objects. A class encapsulations data for the object.
- **Method** - Method facilitate communications between objects.

**For example**

```Dart
class TestClass{
void disp(){
  print("Hello world");
}
}
void main(){
  TestClass c = new TextClass();
  c.disp();
}
```

- The above example defines a class TestClass. The Class has a method Disp(). The method prints the string "Hello world" on the Terminal. THe new keyword creates an object of the class. The object invokes the method disp().

## Data Types

- **Numbers:** Numbers in Dart are used to represent numeric literals. The Number Dart come in two Flavours:

  - **Integer:** Integer values represent non-fractional values i.e. numeric values whiteout a decimal point. For example, the value "10" is an integer. Integer literals are represented using the int keyword.
  - **Double:** Dart also supports fractional numerical value i.e. values with decimal points. The DOuble Data type in Dart represents a 64-bit (double precision) floating point number. For example 10.10 the keyword "Double" is used to represent floating point literals.

- **String:** String represent a sequence of characters. For instance, if you were to store some data line name, address etc. the string data type should be used. A Dart string is a sequence of UTF-16 code units. **Runes** are used to represent a sequence of UTF-32 code units
  The keyword String is used to represent string literals. String values are embedded in either single or double Quotes.

- **Boolean:** The Boolean data type represent Boolean Values true and False. Dart uses the bool keyword to represent a Boolean Value.
- **List and Map:** The Data types list and map are used to represent a collection of objects. A List is an ordered group of objects. The list data type in Dart is Synonymous to the concept of any array in other programming languages. The Map data tpe represent a set of values as key-value pairs. The Dart:Core library enables creation and manipulation of these collections through the predefined List and Map classes respectively.
- **Dynamic Type:** Dart is an optionally typed langues. if the type of a variable is not explicitly specified, the variable's type is dynamic. The dynamic keyword can also be used as a type annotation explicitly.

## Variable

- A variable is "a named space in the memory"
