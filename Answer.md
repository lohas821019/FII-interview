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

Ans:  C 
```

MUL(2, 5) ＝  2*5 ＝ 10

MUL(2+1, 2) ＝ 2+1*2 ＝ 2+2 ＝4 

實際測試：https://onlinegdb.com/uTHCfg6Rq

</br>

## 補充說明

define 在預處理器(prepocessor)時執行

typedef 在編譯器(compiler)的時候執行

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

Ans: B
```

var1 = 10;  

&var1 = 1234;

var2 = 20;

&var2 = 1238;

var3 = 30;

</br>
++(*in1) ＝ 1 +10 ＝ 11 ,此時var1 ＝ 11 （前加）

(*in2)++ ＝ 20 , 此時var2 ＝ 21 （後加,做完print才加）

var3++ ＝ 30 , 此時var2 ＝ 31 （後加,做完print才加）

因此答案為 11,20,30 ,選 B

實際測試：https://onlinegdb.com/riSOybH0N

</br>




## 3. Which one (Var) is NOT equal to 4?
   
```

int Var = 0;

A) Var += 4;

B) (Var+1)*4;

C) Var = (++Var) << 2;

D) Var = (Var + 2) * 2;

Ans: B
```
### int Var = 0;
</br>

A) Var += 4;

=>  Var = Var + 4

=>  Var = 0 + 4  = 4

</br>
B) (Var+1)*4;

=>  (0+1)*4

=>  4 ,但是Var 還是等於0

</br>
C) Var = (++Var) << 2;

=>  Var  = (1) << 2; (用bitwise相當於*4)

=>  Var  = (1)*4;


</br>
D) Var = (Var + 2) * 2;

=> Var = (0 + 2) * 2;

=> Var = （2) * 2 ＝ 4


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

Ans:  C
```

int x=2, y=3;

f(x, y);

f(2, 3);

=> y = 2*123

=> y = 246  (但是這是在function裡面 ,並沒有回傳值,且沒有修改到原本的y)

所以 printf(”%d”, y);

y = 3 ;



實際測試： https://onlinegdb.com/OCl4UYIoz

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

Ans: D

```

因為沒有break, 所以下面的每個都會跑




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

Ans: 1024
```
power(4, 5);

power(4, 4)*4;

power(4, 3)*4 *4;

power(4, 2)*4 *4 *4;

power(4, 1)*4 *4 *4 *4;

if (b == 1) { k = a; },所以 ＝ 4

power(4, 0)*4 *4 *4 *4 *4;

b == 0) { k=1; },所以 

1*4 *4 *4 *4 *4 ＝ 256 *4 ＝1024

實際測試：https://onlinegdb.com/Mv8W3e49

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

Ans: 20
```
i = 2;

*(array+i) = array[i]

*(array+i) = *(array+4-i) + 5

*(array+4-2) + 5 = 15 + 5 = 20


實際測試 ：https://onlinegdb.com/EG2fs9_Q_

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

Ans:  "iolet"
```

**ptr+1  = > 指向字元指標的指標

**ptr ＝ ptr[0] = s+3

s+3 = s[3] = "violet"

**ptr+1 => 'v'

printf會顯示後面的字 ,答案為"iolet"

實際測試：https://onlinegdb.com/bi492M7DS



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

Ans: 3,2
```
</br>

考 static 跟一般的差異,static只會初始化一次,不會每次進入func就初始化

	result1 = func1();
    ＝> result1 = 1

	result1 += func1();
    ＝> result1 = result1 + func1()
    ＝> result1 = 1+2 = 3

	result2 = func2();
    ＝> result2 = 1

	result2 += func2();
    ＝> result2 = result2 + func2()
    ＝> result2 = 1+1 = 2

實際測試： https://onlinegdb.com/2-7AdB6： 

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

Ans: 84
```

    #define DEF

x = 5 , 因為已定義DEF  

x += 9;

x = 5+9 ＝ 14; 

    #ifdef DEF
	    x *= 6;
因為定義好了DEF,所以 x = 14 * 6 = 84


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

```
/* 
不確定是否為正確解答
*/

#include <stdio.h>

#include <stdlib.h>

#include <string.h>


#define BUFF_SIZE 8  // 定義BUFF_SIZE

static char test_string [10] ="teststring";  
//定義一個  static char 字元數組 test_string

int main (void)  
//主函數

{

	char *ptr;  
    //宣告一個字元指標  ,在數組中  a[i] = *(pa+i)

	int len;    
    //宣告整數變數len

    ptr = malloc(BUFF_SIZE * sizeof(char));
    //char * ptr = (char*)malloc(BUFF_SIZE * sizeof(char))

    if (ptr == NULL) {
        printf("Failed to allocate memory\n");
        return 1;
    }
    // 檢查一下是否成功分配

	strcpy(ptr, test_string); 
    // 將test_string 複製到 ptr 裡面 

	len = strlen(ptr); 
    //取得 ptr指向字串的長度

	if (len == 0)  
    //改成 (len == 0)
	{
		printf("Failed to copy string\n"); 
        //印出文字
	}
	else
	{
		printf("The string is: %s\n", ptr ); 
        //印出文字ptr的內容
	}
    
    	free(ptr); 
        //釋放資源
    
	return 0; 
    //因為宣告時是回傳int 所以return 0 ;

}
```









