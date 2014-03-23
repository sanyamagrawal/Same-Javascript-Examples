How to create Block Scope in Javascript?

Javascript variables have function scope against traditional languages which have block scope.

Block Scope:
//A small function in JAVA

ipublic static void main(String[] args) {
    int bar =5;
    { // block starts
        int foo = 4;
    } // block ends
    System.out.println(foo); // Error: cannot find symbol
}

In the above code foo is accessible only inside the block which declares and/or defines it . It is not accible outside the block.

But IN JAVASCRIPT. 
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
