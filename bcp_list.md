# Листинги программ #
> Task 1
```cpp
#include <iostream>
using namespace std;

bool x[] = { 0, 1, 1, 0, 1, 0, 0, 1, 0, 0, 0, 1 };

int test1()
{
	for (int i = 1; i < sizeof(x) - 1; ++i)
	{
		bool flag = 0;
		for (int j = 0; j < i; ++j)
			if (x[j] == 0)
				flag = not flag;
		if (flag == 1)
			for (int j = i + 1; j < sizeof(x); ++j)
				x[j] = not x[j];
	}
	for (int i = 0; i < sizeof(x); ++i)
		cout << x[i] << " ";
	cout << endl;
	return 0;
}
```
> Task2
```cpp
#include <iostream>
using namespace std;

//задание 1
int a = 3, b = 1, c = 2;

int test2()
{
	//пункт а
	bool ba, cb, ca;
	if (b - a > 0)
		ba = 1;
	else
		ba = 0;
	if (c - b > 0)
		cb = 1;
	else
		cb = 0;
	if (c - a > 0)
		ca = 1;
	else
		ca = 0;
	switch (ba)
	{
	case 1:switch (cb)
	{
	case 1:cout << "a b c" << endl;
		break;
	case 0:if (ca) cout << "a c b" << endl;
		   else cout << "c a b" << endl;
		break;
	}
		   break;
	case 0:switch (cb)
	{
	case 1:if (ca) cout << "b a c" << endl;
		   else cout << "b c a" << endl;
		break;
	case 0:cout << "c b a" << endl;
		break;
	}
		   break;
	}

	//пункт б (bad alloc)
	/*int x[3] = { a, b, c };
	char y[] = { 'a', 'b', 'c' };
	char tmp;
	for (int i = 0; i < 3; ++i)
		for (int j = 0; j < 3; ++j)
			if (x[i] > x[i + 1])
			{
				tmp = y[i];
				y[i] = y[i + 1];
				y[i + 1] = tmp;
			}
	for (int k = 0; k < 2; ++k)
		cout << y[k] << " ";
	cout << endl;*/
	return 0;
}
```
> Task3
```cpp
#include <iostream>
using namespace std;

const char* call = "it's just a fucking game";

int fact(int x);

int test3()
{
	int count = 0;
	for (int i = 0; i < strlen(call); ++i)
		if (call[i] == ' ')
			count += 1;
	int C = fact(count+1);
	cout << "count of words = " << count+1 << "; count of calls = " << C << endl;
	
	//пункт а
	const char* b = " dfg sdklj  kl k";
	int count = 0;
	for (int k = 1; k < 15; ++k)
	{
		if (b[k] == ' ')
			count += 1;
	}
	cout << "count of spaced symbol = " << count << endl;

	return 0;
}

int fact(int x)
{
	if (x == 0) return 1;
	return x * fact(x - 1);
}
```
> Task4
```cpp
#include <iostream>
using namespace std;

bool ab[10] = { 0, 0, 1, 0, 1, 1, 1, 0, 0, 1 };

int test4()
{
	int ns = 0, ne = 9;
	for (int i = 1; i < 9; ++i)
	{
		if (ab[i] == 1 && ab[i + 1] == 1 && ab[i - 1] == 0)
		{
			ns = i;
		}
		if (ab[i] == 1 && ab[i - 1] == 1 && ab[i + 1] == 0)
		{
			ne = i;
		}
	}
	if (ab[0] == 1 && ab[1] == 1)
		ns = 0;
	if (ab[9] == 1 && ab[8] == 1)
		ne = 9;
	cout << "start point = " << ns << " , end point = " << ne << endl;
	
	
	return 0;
}
```
> Task5
```cpp
#include <iostream>
using namespace std;

const unsigned int N = 6;
unsigned int n = 2;
int s[6] = { 3, 10, 2, 1, 9, 5 };

int test5()
{
	int xk;
	int y[6];
	unsigned int lowIdx, highIdx;
	for (unsigned int i = 0; i < N; ++i)
	{
		xk = 0;
		if (i < n)
			lowIdx = 0;
		else
			lowIdx = i - n;
		if (i + n >= N)
			highIdx = N - 1;
		else
			highIdx = i + n;
		for (unsigned int j = lowIdx; j <= highIdx; ++j)
			xk = xk + s[j];
		xk = xk / (2 * n + 1);
		y[i] = round(xk);
	}
	for (unsigned int k = 0; k < N; ++k)
		cout << "y[" << k << "] = " << y[k] << endl;
	return 0;
}
```
> Task6
```cpp
#include <iostream>

//задание 6
int a[5] = { 100, 12, 3, 11, 4 };

int test6()
{
	int b[5];
	for (int i = 0; i < 5; ++i)
	{
		int j = 0;
		while (1)
		{
			if (j != a[i])
			{
				j += 1;
			}
			else
			{
				b[i] = a[i];
				break;
			}
		}
	}
	for (int k = 0; k < 5; ++k)
	{
		std::cout << "a[" << k << "] = " << b[k] << std::endl;
	}
	return 0;
}
```
> Task7
```cpp
#include <iostream>

int test7()
{
	int a, b, c;
	std::cout << "a (1:3) = ";
	std::cin >> a;
	std::cout << "b (1:3) = ";
	std::cin >> b;

	switch (a)
	{
	case 1:switch (b)
	{
	case 1: c = 1;
		break;
	case 2: c = 2;
		break;
	case 3: c = 3;
		break;
	}
		   break;
	case 2:switch (b)
	{
	case 1: c = 2;
		break;
	case 2: c = 4;
		break;
	case 3: c = 6;
		break;
	}
		   break;
	case 3:switch (b)
	{
	case 1: c = 3;
		break;
	case 2: c = 6;
		break;
	case 3: c = 9;
		break;
	}
		   break;
	}
	std::cout << "c = a * b = " << c << std::endl;
	return 0;
}
```
> Task8
```cpp
#include <Windows.h>
#include <iostream>
using namespace std;

HANDLE console = GetStdHandle(STD_OUTPUT_HANDLE);

int x[5][5] = { {0,1,1,0,0}, {2,1,0,1,5}, {4,0,0,1,1}, {0,3,2,1,0}, {1,2,3,0,0} };

int main()
{
	int xtmp[5][5] = { {0,0,0,0,0}, {0,0,0,0,0}, {0,0,0,0,0}, {0,0,0,0,0}, {0,0,0,0,0} };
	int tmp = 0;
	int d = 0, l = 0;
	for (int i = 0; i < 5; ++i)
		for (int j = 0; j < 5; ++j)
		{
			for (int k = 0; k < 5; ++k)
				xtmp[i][j] += x[i][k];
			for (int m = 0; m < 5; ++m)
				xtmp[i][j] += x[m][j];
			xtmp[i][j] -= x[i][j];
		}
	for (int p = 0; p < 5; ++p)
		for (int q = 0; q < 5; ++q)
			if (xtmp[p][q] > tmp)
			{
				tmp = xtmp[p][q];
				d = p;
				l = q;
			}
	for (int z = 0; z < 5; ++z)
	{
		for (int y = 0; y < 5; ++y)
		{
			if (z == d && y == l)
			{
				SetConsoleTextAttribute(console, 10);
				cout << " " << x[z][y] << " ";
			}
			else
			{
				SetConsoleTextAttribute(console, 7);
				cout << " " << x[z][y] << " ";
			}
		}
		cout << endl << endl;
	}
	SetConsoleTextAttribute(console, 10);
	cout << endl << "  " << "max priority for element x[" << d << "][" << l << "] = " << x[d][l] << endl;
	SetConsoleTextAttribute(console, 7);
	return 0;
}
```
> Task9
```cpp
#include <iostream>

bool a7 = 0;
bool b7 = 1;

bool func1(bool x);
bool func2(bool x);

int test9()
{
	if (!func1(func2(a7)))
		std::cout << "a = 1, b = 0" << std::endl;
	else
		std::cout << "a = 0, b = 1" << std::endl;
	return 0;
}

bool func1(bool x)
{
	return x;
}

bool func2(bool x)
{
	return not x;
}
```
> Task10
```cpp
#include "stdio.h"
#include "test5impl.h"

#include <ctime>
#include <iostream>
using namespace std;

int x = 1;

int test10()
{

	srand(time(0));

	printf("\n your dessision is ");
	printf("%d\n", iter(&x));

	cout << "runtime = " << clock() / 1000.0 << endl;
	system("pause");

	return 0;
}


#ifndef TEST5IMPL_H
#define TEST5IMPL_H

//задание 10 - заголовок исполнителя
extern int x;

struct MyStruct
{
	int* y;
};

int iter(int* input);

#endif

//задание 10 - заголовок исполнитель

#include "test10r.h"

int iter(int* input)
{
	MyStruct str;
	str.y = input;
	return x << *str.y;
}
```
> Task11
```cpp
#include <Windows.h>
#include <iostream>
#include <string>
using namespace std;

HANDLE console = GetStdHandle(STD_OUTPUT_HANDLE);

string parol = "1000";

int test11()
{
	string take;
	bool flag = 0;
	while (1)
	{
		flag = 0;
		SetConsoleTextAttribute(console, 7);
		cout << "Parol: ";
		getline(cin, take);
		cout << "wait" << endl;
		Sleep(5000);
		for (int k = 0; k < 4; ++k)
			if (take == parol)
				flag = 1;
		if (flag == 1)
		{
			SetConsoleTextAttribute(console, 10);
			cout << " COMPLETE : your can proceed" << endl;
			break;
		}
		else
		{
			SetConsoleTextAttribute(console, 4);
			cout << " eror : your parol fake" << endl;
		}
	}
	return 0;
}
```
> Task12
```cpp
#include <iostream>
using namespace std;
#include <Windows.h>

bool x[3][4] = { {0,1,1,0},{1,0,1,0},{1,1,0,1} };
bool y[4][3] = { {1,0,1},{0,0,1},{0,1,1},{1,0,1} };

bool matr_plex();

int test12()
{
	if (!matr_plex())
	{
		cout << " error: your decision incorrect" << endl;
		return 1;
	}
	else
		cout << "proceed" << endl;
	return 0;
}

bool matr_plex()
{
	bool z[3][3];
	bool tmp[4];
	for (int k = 0; k < 3; ++k)
	{
		for (int i = 0; i < 3; ++i)
		{
			for (int j = 0; j < 4; ++j)
			{
				tmp[j] = x[k][j] and y[j][i];
			}
			z[k][i] = tmp[0] xor tmp[1] xor tmp[2] xor tmp[3];
			cout << z[k][i] << " ";
			Sleep(2000);
		}
		cout << endl;
		Sleep(2000);
	}
	return true;
}
```
> Task13
```cpp
#include <iostream>
using namespace std;
#include <Windows.h>
#include <string>

HANDLE console = GetStdHandle(STD_OUTPUT_HANDLE);

bool waits(int* mode); //wait for entering to shell
bool jobs(int* mode); //choosing process
bool ret(int mode); //outer check
bool shootdown();

int test13()
{
	int mode;
	while (true)
	{
		if (!shootdown())
			return 0;
		else {
			if (!waits(&mode)) //shell login error
				return -1;
			while (true)
			{
				if (!jobs(&mode))  //shell early escaping
					return 1;
				if (!ret(mode)) //shell expected escaping
					break;
			}
		}
	}
}



bool waits(int* mode) {
	string enter;
	while (1)
	{
		Sleep(2000);
		SetConsoleTextAttribute(console, 3);
		cout << "startx to continue, enter to break" << endl;
		getline(cin, enter);
		if (enter == "$/>") {
			Sleep(1500);
			break;
		}
		if (enter == "~") {
			Sleep(2000);
			SetConsoleTextAttribute(console, 12);
			cout << endl << "shell start error" << endl;
			SetConsoleTextAttribute(console, 7);
			return false;
		}
	}
	return true;
}


void job1(); // work with shell
void job2(int* mode); //check for outing

bool jobs(int* mode) {
	Sleep(1500);
	SetConsoleTextAttribute(console, 14);
	cout << "mode: (1 - to work with shell;\n       2 - to escape) " << endl;
	cin >> *mode;
	switch (*mode) {
	case 0: Sleep(5000);
		SetConsoleTextAttribute(console, 4);
		cout << "error: erlier escape" << endl;
		SetConsoleTextAttribute(console, 7);
		Sleep(2000);
		return false;
		
	case 1: job1();
		break;

	case 2: job2(mode);
		break;
	}
	return true;
}

void job1() {
	Sleep(5000);
	SetConsoleTextAttribute(console, 10);
	cout << "job1 is done" << endl;
}

void job2(int* mode) {
	Sleep(1000);
	SetConsoleTextAttribute(console, 5);
	cout << "your actualy want to escape? (0 - yes) " << endl;
	cin >> *mode;
}


bool ret(int mode) {
	if (mode == 0)
		return false;
	else
		return true;
}


bool shootdown() {
	string shdn;
	while (true)
	{
		Sleep(2000);
		SetConsoleTextAttribute(console, 7);
		cout << "logout to shootdown, enter to continue" << endl;
		getline(cin, shdn);
		if (shdn == "~")
			break;
		if (shdn == "logout")
			return NULL;
	}
	return true;
}
```
> Task14
```cpp
#include "fun.h"

typedef struct {
	int line;
} chan ;

typedef struct {
	int line;
} chen;

int test14()
{
	chan ch;
	chen ce;
	int* pid[2];
	pid[0] = &ch.line;
	pid[1] = &ce.line;
	fun(pid[0]);
	tr(pid[0], pid[1]);
	view(pid[1]);
	return 0;
}

#include <iostream>
using namespace std;

#ifndef FUN_H_
#define FUN_H_

static void fun(int* arg) {
	cin >> *arg;
}
static void tr(int* st, int* ed) {
	*ed = *st;
}
static void view(int* arg) {
	cout << *arg;
}

#endif // 
```
> Task15
```cpp
#include <iostream>
using namespace std;

#include "types.h"
#include "run.h"

#include <Windows.h>
#include <ctime>

HANDLE console = GetStdHandle(STD_OUTPUT_HANDLE);

int test15()
{
	//start timer
	int start = clock();

	//create object of delay buffer
	delay buffer;
	init(&buffer);
	
	//start delay process
	if (!run(&buffer))
		return 1;

	//stop timer
	int end = clock();
	int time = end - start;
	SetConsoleTextAttribute(console, 12);
	cout << "\n execution time is " << time / 1000 << "s" << endl;
	SetConsoleTextAttribute(console, 7);

	return 0;
}

#ifndef TYPES_H_
#define TYPES_H_

#ifndef LENBUF
#define LENBUF 10 //length of delay buffer
#endif

typedef int word; //type of symbol in buffer
typedef int* point; //type of enumerate in buffer

typedef struct {
	point startpoint;
	point endpoint;
	word buf[LENBUF];
} delay; //type of delay buffer

static void init(delay* obj) {
	obj->startpoint = &obj->buf[0];
	obj->endpoint = &obj->buf[LENBUF - 1];
}

#endif //TYPES_H_


#include "types.h"

#ifndef RUN_H_
#define RUN_H_

bool run(delay* arg); //delay process

#endif // !RUN_H_

#include "run.h"

#include <Windows.h>

extern HANDLE console;

void imi(point writepoint); //imitation of input symbol
void out(point readpoint); //gettin output symbol
void desh(word* arr); //shift delay buffer

bool run(delay* arg) {
	for (int i = 0; i < LENBUF; ++i)
	{
		imi(arg->startpoint);
		desh(arg->buf);
	}
	for (int i = 0; i < LENBUF; ++i)
	{
		out(arg->endpoint);
		desh(arg->buf);
	}
	return true;
}

void imi(point writepoint) {
	//Sleep(1000 / LENBUF);
	*writepoint = rand() % 100;
}

void out(point readpoint) {
	//Sleep(1000 / LENBUF);
	SetConsoleTextAttribute(console, 10);
	cout << *readpoint << " ";
}

void desh(word * arr) {
	for (int j = LENBUF - 1; j > 0; --j) {
		Sleep(1000 / LENBUF);
		arr[j] = arr[j - 1];
	}
}
```
