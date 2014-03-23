#How to create Block Scope in Javascript?

Javascript variables have function scope against traditional languages which have block scope.

###Block Scope:###
A small function in JAVA

```java
public static void main(String[] args) {
    int bar =5;
    { <!--block starts-->
        int foo = 4;
    } // block ends
    System.out.println(foo); **// Error: cannot find symbol**
}
```
In the above code foo is accessible only inside the block which declares and/or defines it . It is not accible outside the block.

###But IN JAVASCRIPT.###

  ```javascript
 function main() {
    {
        //Block Starts
        var foo = 5;
    }
    console.log(foo);
}
```
Here foo outputs 5 , and is accessible across main() function.

THere are situations where you might want to limit a scope to a certain block example limit the scope to a else condition in a if-else statement.

##Comes the Power of IIFE ( Immediately Invoked Function Expression)
<br />

```javascript
if(something){
    //Do Something
}else {
    (function(){
        var b = 5;
        console.log(b); //5
    }{});
}
console.log(b) // Undefined
```

As the name suggest, any function that is invoked as soon as it is defined is called an IIF , E stands for the fact that it needs to be an expression to be involed because as soon as the parser sees a function it expects it to be a function declaration , and function declaration cannot be immediately invoked.

Therefor we need to make a function declaration an expression. So what are the possible ways of making an expression in javascript?

**Adding a () arround a statement will make it expression.**

```javascript
(function(){
    Do Something
}());
```

**If you dont want to add a (), you can also use the ! or void operator
**

```javascript
!function(){
    Do Something
}();
```

```javascript
void function(){
    *Do Something*
}();
```
**You dont need to add any of the above if the statement is already a function expression.
**

```javascript
var something = function(){}();
```

**This also is a function expression** HOW? Give your brain a spin.*

<br /><br /><br />
##TODO: Writeup of practicle applications of IIFE