# Monkey

## Setup
1. Download and install Go
2. Install *direnv* (https://direnv.net). ```brew install direnv```. We use it to set the GOPATH env variable inside ```.envrc```.

## Run Tests
1. From the root of the project file
2. Run tests. E.g. ```go test monkey/lexer```

## Run REPL

run ```go run src/monkey/main.go``` from the root dir of project

## Go Notes
### What is ```:=```
In Go, := is for declaration + assignment, whereas = is for assignment only.

For example, var foo int = 10 is the same as foo := 10.

### When to use pointers?
1. Structs are passed into functions by value. That is, a copy of a structure is made when passing it into a function.
2. If I want to pass a structure by reference, then I would instead use a pointer argument in the function definition, and use the addressof operator when calling the function.
3. The reason why I would want to pass in a structure by reference is because either the structure I'm passing in is large, and it would be taxing on memory to pass it by value (unlikely) or if I want to make changes to the copy that I'm passing in (more likely).
Keep in mind, Go is concurrent language and passing by reference in goroutines make them all read same structure which is safe, but also make them modify same structure which is dangerous.
4. As a corollary to 3.), I should pass by value unless I have one of the reasons above to pass by reference.

### Visibility
An identifier that starts with a capital letter is exported from the package, and can be accessed by anyone outside the package that declares it.
If an identifier starts with a lower case letter, it can only be accessed from within the package.

## Book Source Code

https://github.com/mmyoji/go-monkey


## Upto
Page 48

2.6 - Parsing Expressions
