#  2023/02 FII interview test


## 1. What’s the output of the following codes?

```
What’s the output of the following codes?

#define MUL(x, y) x * y

int main(void)

{

	printf(“%d, %d\n”, MUL(2, 5) , MUL(2+1, 2));

	return 0;

}

A) 10, 6 
B) 10, 5 
C) 10, 4 
D) 2, 5

Ans:  
```

</br>



## 2. What’s the output of the following codes?

```
/* assume memory address of var1 is 1234 in decimal. */

int var1 = 10;

/* assume memory address of var2 is 1238 in decimal. */

int var2 = 20;

void func(int* in1, int* in2)

{

	int var3 = 30;

	printf(“%d,%d,%d\n”, ++(*in1), (*in2)++, var3++);

}

int main(void)

{

	func(&var1, &var2);

	return 0;

}

A) 10,20,30 
B) 11,20,30 
C) 11,21,31 
D) 1235,1238,30

Ans: 
```




</br>




## 3. Which one (Var) is NOT equal to 4?
   
```

int Var = 0;

A) Var += 4;

B) (Var+1)*4;

C) Var = (++Var) << 2;

D) Var = (Var + 2) * 2;

Ans: 
```



</br>



## 4. What’s the output of the following codes?

```
void f(int x, int y)
{

	y=x*123;

}

int main()

{

	int x=2, y=3;

	f(x, y);

	printf(”%d”, y);

}

A) 369 
B) 246 
C) 3 
D) None of the above

Ans: 
```


</br>



## 5. What’s the output of the following codes?
```
int i=3;

switch (i)

{

	case 2:

		printf(“2 “);

	case 3:

		printf(“3 “);

	case 4:

		printf(“4 “);

	default:

		printf(“5 “);

}

A) 2 
B) 3 
C) 3 4 
D) 3 4 5

Ans: 

```



</br>


## 6. What will be output by printf()?

```
int power(int a, int b)

{

	int k;

	if (b == 0) { k=1; }

	else if (b == 1) { k = a; }

	else { k = a * power(a, b-1);}

	return k;

}

int main(void)

{

	printf(“%d\n”, power(4, 5));

	return 0;

}

Ans: 
```


</br>





## 7. What will be output by printf()?

```
int main(void)

{

	int i, array[5] = {5, 10, 15, 20, 25};

	i = 2;

	*(array+i) = *(array+4-i) + 5;

	printf(“%d ”, *(array+i));

	return 0;

}

Ans: 
```





</br>



## 8. What will be output by printf()?
```
int main(void)

{

	static char *s[] = {”black”, “white”, “pink”, “violet”};

	char **ptr[] = {s+3, s+2, s+1, s};

	printf(“%s”, **ptr+1);

	return 0;

}

Ans: 
```




</br>



## 9. What will be output by printf()?
```
int func1(void)

{

	static int value = 0;

	value++;

	return value;

}

int func2(void)

{

	int value = 0;

	value++;

	return value;

}

int main(void)

{

	int result1, result2;

	result1 = func1();

	result1 += func1();

	result2 = func2();

	result2 += func2();

	printf (“%d %d”, result1, result2);

	return 0;

}

Ans: 
```




</br>



## 10. What will be output by printf()?
```
#define DEF

int main(void)

{

	int x;

#ifndef DEF

	x = 10;

#else

	x = 5;

#endif

	x += 9;

#ifdef DEF

	x *= 6;

#endif

	printf (“%d”, x);

	return 0;

}

Ans: 
```




</br>





## 11. Code review and Correction:
```
#include <stdio.h>

#include <stdlib.h>

#include <string.h>

#define BUFF_SIZE 8

static char test_string [10] ="teststring";

int main (void)

{

	char *ptr;

	int len;

	ptr = malloc(BUFF_SIZE);

	strcpy(ptr, test_string);

	len = strlen(ptr);

	if (len = 0)

	{

		printf("Failed to copy string\n");

	}

	else

	{

		printf("The string is: %s\n", ptr );

	}

	return 0;

}

Ans:
```









