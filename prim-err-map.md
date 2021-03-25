# Primitives, Errors and scanning 

##Primitives and objects 

Primitives (byte, short, int, long, float, double boolean, char) are stored directly in the stack and represent raw data. Objects on the other hand such as ` Integer i = 1;` live in the heap and are slightly slower to access. 

##errors 

If an error is encountered during runtime and exception is throw. You can use try/catch/finally to handle these. For example: 

`try { 
//An error could occur here. 
}` 

`catch (<err to catch>){ 
//do something specific if a specific error is thrown. 
}` 

`finally{ 
//this is guarantied to run and can be sued to do stuff like clean up used recourses close files etc. before exiting. 
}` 

## Scanning 

Scanning is used to read and parse files. It is worth noting locals for things that may need to be parsed in a specific way such as an int “54,321” else it may not know how to use the ‘,’. 

 