## Scope and Closure

##### Javascript Variable Hoisting

http://stackoverflow.com/questions/9085839/surprised-that-global-variable-has-undefined-value-in-javascript

```javascript
//example 1

var arg = 1;
function funcTest(){
    console.log(arg); //undefined
    var arg = 2;
    console.log(arg); //2
}
funcTest();

function funcTest2(){
    console.log(arg); //1
}
funcTest2();
```

Explaination:
_Javascript Variable Hoisting_

something to do with js lexical scoping

whatever variable you declare are always *hoisted* to the top of your closure. even you declared your variable after the first `console.log`, it's still considered as if you had declared it before that. only the declaration part is being hoisted, the assignment is not.

first example actually 
```
function funcTest(){
    var arg;
    console.log(arg);

    arg = 2;
    console.log(arg);
}
```

in `funcTest2()`, since no declaration of `arg`, it use global variable intead.

##### Scope

JavaScript uses *lexical scoping*. This means that functions are executed using the variable scope that was in effect when they were defined, not the variable scope that is in effect when they are invoked.

(Modern compiler works the same i think...)

new scope chian is created with `new`, `with`, `let` and `catch`. (http://stackoverflow.com/questions/2730858/in-javascript-when-is-a-new-scope-created-with-a-new-function-and-in-a-with)

