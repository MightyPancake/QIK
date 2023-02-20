![QIK](http:https://raw.github.com/MightyPancake/QIK/blob/main/logo/qikLogotypOrange.svg)
An easy to learn, fast and general use dynamically typed language with no keywords!

```qik
/*
    QIK Programming Language
    is an interpreted language that strives to be QICK, hence, the name!
    It is inspired by Lua in some aspects, but there are a lot of new features too!

    Why QIK?
    - Has no keywords! Yup!
    - Easy to use
    - Fast (I hope, lol. It's small for sure. Runs bytecode, so should be fast)
*/

// Syntax overview

// This is a single line comment

/*
    This is a 
    Multiline comment
*/

//Data types

number = 42
string = "A QIK brown fox jumps over a lazy dog"
boolean = (1>0)                     //Booleans are either (.) - true or (!) - false.
table = []                          //It acts almost the same as in Lua
function = ;a, b{^a+b}              //Calling C functions is also planned
empty = ()                          //This is like NULL, it means 'no value'. Assigning this to a value ereases it. Empty evaluates to false!
ref = @number                       //This is a reference. Refrences act like pointers, but you cannot take reference from refrence. No double pointers!
                                    //Basically, reference behaves like a normal variable, but "copies" actions made to it to the referenced variable

//Variables

a = 10                              //QIK is dynamically typed. This means a variables can have many types within it's lifespan
a = "another value"                 //But only one type at a time, right now 'a' is of type 'string'

var = "I'm a local variable"        //Inspired by GO, variable names starting with lowercase letters are local
Var = "I'm a global variable"       //If the variable name starts with an uppercase letter, it's global

//Basic math operators - (+, -, *, /)
//Basic logic operators - (==, !=, <, >, <=, >=, !)

//Basic operators work as you'd think they work. QIK implements operator assigning, for example:

a = 2                               //Assign 2 to 'a'
a *= 3                              //Multiply 'a' by 3

//Assigning a value returns it as well, so you can have something like this
a = (b = 1) + 2                     //'b' is 1, 'a' is 3

//There is also conditioned assigning

a ?= "had value" : "had no value"   //if 'a' evaluates to true (had value other than (!) or () ), assigns "had value", otherwise assigns "had no value"
a := "init"                         //if 'a'

//if, else, else-if (?)

1 > 2 ?
    print("1 is greater than 2")
: 1 == 2 ?
    print("1 equals 2")
:
    print("1 is smaller than 2")

//This is an if statement. If there is more than one line of code, you use brackets like so:

1 >= 2 ? {
    a = (.)
    print("1 is greater than 2")
}:{
    a = (!)
    print("1 is smaller than 2")
}

//If statements act like ternary statement, they return value!
a = 12
fact = a > 0 ? "a is positive" : "a is not positive"


//Loops (->)

//There is only one loop, as you may know, only one is needed!
//Of course, it's the while loop, here's how it looks!

i = 0
-> i < 10
    i++

//The loop above will check 'i<10' as condition and will perform 'i++' as long as the condition is true!
//Again, you can use brackets {...} if there are more lines of code
i = 0
-> i < 10 {
    i++
    print("Loopidy, loop!")
}

//What about the 'for' loop? It's a handy thing to have, right? Here's the solution!

-> i?=i++:0 < 10
    print(i)                    //This loop will print numbers from 0 to 9, just like a for!

//This concludes loops

//Functions

my_func = ;a, b{                //Semicolon ; defines start of a funcion. After that, you can specify parameters before '{'.
    ^ a+b                       //The returns keyword is replaced with ^. It works exactly the same
}

//Optionally, you don't need to specify paramater names
my_func_but_fancy = ;{^$1+$2}   //$1 and $2 are first and second parameter.

my_func_last = ;{               //You can also loop over paramaters, all of them
    -> $[i?=i++:0]              //Loop until a parameter is empty or false
        print("param ", i, " is ", $[i])
}

```
