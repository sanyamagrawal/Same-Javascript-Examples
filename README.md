#How to create Block Scope in Javascript?

Javascript variables have function scope against traditional languages which have block scope.

###Block Scope:###
//A small function in JAVA

public static void main(String[] args) {
    int bar =5;
    { // block starts
        int foo = 4;
    } // block ends
    System.out.println(foo); **// Error: cannot find symbol**
}

In the above code foo is accessible only inside the block which declares and/or defines it . It is not accible outside the block.

###But IN JAVASCRIPT.###
 function main() {
	{
		//Block Starts
		var foo = 5;
	}
	console.log(foo);
}

Here foo outputs 5 , and is accessible across main() function.

THere are situations where you might want to limit a scope to a certain block example limit the scope to a else condition in a if-else statement.

Comes the Power of IIFE ( Immediate Innovation Function Execution)

if(something){
	//Do Something
}else {
	(function(){
		var b = 5;
		console.log(b); //5
	}{});
}

console.log(b) // Undefined

#IIFE ( Immediately Invoked Function Expression)

As the name suggest, anything function that is invoked as soon as it is defined is called an IIF , E stands for the fact that it needs to be an expression to be involed as soon as it is defined because as soon as the parser sees a function it expects it to be a function declaration , and function declaration cannot be immediately invoked.

Therefor we need to make a function declaration an expression. THis is same as making an expression in java script. What are the possible ways of making an expression in javascript?

1. adding a () arround a statement will make it expression

(function(){
    //Do Something
}());

2. if you dont want to add a (), you can also use the ! or void operator

!function(){
    **Do Something**
}();

void function(){
    **Do Something**
}();

3. You dont need to add any of the above if the statement is already a function expression.

var something = function(){}(); **This also is a function expression** HOW? Give your brain a spin.

**TODO : Writeup of practicle applications of IIFE**

