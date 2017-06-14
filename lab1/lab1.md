CS240 Lab1
Ji Ma

### Q1
The nature of the a.out is the binary code compiled by gcc.<br>
Steps:

1. Preprocess - process the # statement like include libs
2. Compile - Compile the main.c file into machine language.
3. Link - link the existed libs and remix it in the compiled code.


If I change the declared function head main to test, the gcc compiler will throw the error msg: undefined reference to 'main'. It won't generate an executable.

If you change the int to void, nothing will happen on the screen, but there will be no return specified in this function.

### Q2

```
> whereis stdio.h

```

The string that does not contain %d is literal, and the part %d is reserved for integer vars in this case.