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
➜  lab1 git:(master) ✗ whereis stdio.h  
stdio: /usr/include/stdio.h

```

The string that does not contain %d is literal, and the part %d is reserved for integer vars in this case.

if I run gcc with option -c, which means<br>
-c                       Compile and assemble, but do not link<br>

```
➜  v2 git:(master) ✗ gcc -c main.c 
➜  v2 git:(master) ✗ ls  
main.c  main.o

```
I'm not sure main.o is the same as main.out.

### Q3
& is a pointer in C, so when you are trying to assign value in scanf()<br>

```cmake
scanf("%d %d",&x,&y) 
```

You are trying to assign integer values into the correct address.


If I remove & in front of vars. 
```cmake
scanf("%d %d",x,y) 
```
```
➜  v3 git:(master) ✗ gcc main.c 
main.c:9:1: warning: return type defaults to ‘int’ [-Wimplicit-int]
 main()
 ^
main.c: In function ‘main’:
main.c:14:9: warning: format ‘%d’ expects argument of type ‘int *’, but argument 2 has type ‘int’ [-Wformat=]
   scanf("%d %d",x,y);
         ^
main.c:14:9: warning: format ‘%d’ expects argument of type ‘int *’, but argument 3 has type ‘int’ [-Wformat
```

```
➜  v3 git:(master) ✗ a.out     
1 2
[1]    3565 segmentation fault  a.out

```

### Q4
& refers to address, if you use &var in the printf(), you will print address.
```cmake
// print result
  printf("%d plus %d = %d\n", &x, &y, &z);

```

```
➜  v3 git:(master) ✗ a.out
1 2
1148769420 plus 1148769424 = 1148769428
```

