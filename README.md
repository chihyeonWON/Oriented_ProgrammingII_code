# Oriented_ProgrammingII_code
객체지향프로그래밍II C++ 연습문제 코드 정리 1장~6장

## 1장

### 주사위 게임 프로그램 작성

1. 2개의 주사위를 던져서 주사위의 합을 표시하는 프로그램
2. 주사위를 던지면 랜덤한 수가 나와야한다.

```c++
#include <iostream> // 입출력 파일
#include <ctime> // 난수발생seed
#include <cstdlib>
using namespace std;

int main()
{
  srand(time(NULL));
  int dice1 = (rand() % 6) + 1;
  int dice2 = (rand() % 6) + 1;
  
  cout << "두 주사위의 합 " << dice1 + dice2 << endl;
  return 0;
}
```

### 사용자의 나이를 물어보고 10년 후에는 몇 살이 되는지 출력하는 프로그램 작성
```c++
#include <iostream>
using namespace std;

int main()
{
	int age; // 나이

	cout << "사용자의 나이는 몇살입니까? : ";

	cin >> age;

	cout << "10년 후에는 " << age+10 << "살이 됩니다." << endl;

	return 0;
}
```

### 1평은 3.3058 이다. 평을 평방미터로 환산하는 프로그램 작성
```c++
#include <iostream>
using namespace std;

int main()
{
	const double SIZE_METER = 3.3058; //평방미터
	double size; // 평

	cout << "평: ";
	cin >> size;

	cout << "평방미터: " << size * SIZE_METER << endl;

	return 0;
}
```

### 시, 분, 초로 표현된 시간을 초 단위의 시간으로 변환하는 프로그램 작성
```c++
#include <iostream>
using namespace std;

int main()
{
	int hour, minute, second;
	cout << "시: ";
	cin >> hour;
	cout << "분: ";
	cin >> minute;
	cout << "초: ";
	cin >> second;

	cout << "전체 초: " << hour * 3600 + minute * 60 + second << endl;

	return 0;

}
```

### 2장

### 비밀 코드 맞추는 프로그램
```c++
#include <iostream>
using namespace std;

int main()
{
	char code;
	char secret_code = 'h';

	cout << "비밀코드 맞춰보세요: ";
	cin >> code;
	if (code > secret_code) {
		cout << code << "앞에 있음" << endl;
	}
	else if (code < secret_code) {
		cout << code << "뒤에 있음" << endl;
	}
	else {
		cout << "맞췄습니다." << endl;
	}
	return 0;
}
```

### 세 개의 정수 중에서 큰 수 찾는 프로그램

```c++
#include <iostream>
using namespace std;

int main()
{
	int a, b, c, largest;
	cout << "3개의 정수를 입력하세요." << endl;
	cin >> a;
	cin >> b;
	cin >> c;
	if (a > b && a > c) {
		largest = a;
	}
	else if (b > a && b > c) {
		largest = b;
	}
	else {
		largest = c;
	}

	cout << "가장 큰 수는 " << largest << endl;
	return 0;
}
```

### 숫자 맞추기 게임
```c++
#include <iostream>
#include <ctime>
using namespace std;

int main()
{
	srand(time(NULL));

	int answer = rand() % 100; // 문제
	int guess;
	int tries = 0;

	do {
		cout << "정답을 추측하여 보세요: ";
		cin >> guess;
		tries++;

		if (guess > answer) {
			cout << "추측한 값이 정답보다 큽니다\n";
		}
		else if (guess < answer) {
			cout << "추측한 값이 정답보다 작습니다\n";
		}
	} while (answer != guess);

	cout << "축하합니다. 시도 횟수=" << tries << endl;
	
	return 0;
}
```

### 배열에서 최대값을 찾는 프로그램 작성

```c++
#include <iostream>
#include <ctime>
using namespace std;

int main()
{
	int list[10];
	int max;

	for (int& elem : list) {
		elem = rand() % 100 + 1;
		cout << elem << " ";
	}

	cout << endl;
	max = list[0];

	for(int& elem : list){
		if (elem > max) {
			max = elem;
		}
	}
	cout << "배열의 최대값은: " << max << endl;
 
	return 0;
}
```

## 구구단 4단까지 출력하는 프로그램

```c++
#include <iostream>
#include <ctime>
using namespace std;

int main()
{
	int table[4][9];
	int r, c;

	for (r = 0; r <4; r++)
		for (c = 0; c < 9; c++)
			table[r][c] = (r + 1) * (c + 1);
	
	for (r = 0; r < 4; r++) {
		for (c = 0; c < 9; c++) {
			cout << table[r][c] << ", ";
		}
		cout << endl;
	}
}
```

## 피보나치 수열을 계산하는 프로그램 작성

```c++ 
#include <iostream>

using namespace std;

int main()
{
	int a = 0, b = 1;
	int temp;
	int input;

	cout << "피보나치 몇자리? :";
	cin >> input;

	cout << a << " " << b << " ";

	for (int i = 2; i < input; i++) {
		temp = b;
		b = a + b;
		a = temp;

		cout << b << " ";
	}
	return 0;
}
```

## 3장

### 동전을 100번 던져서 동전의 각면이 나타나는 횟수를 세어 출력하는 프로그램

```c++
#include <iostream>
#include <ctime>
using namespace std;

int flip() {
	return rand() % 2;
}


int main()
{
	srand(time(NULL));

	int front = 0;
	int rear = 0;

	for (int i = 0; i < 100; i++) {
		if (flip() == 0) {
			front++;
		}
		else {
			rear++;
		}
	}
	cout << "동전의 앞면 :" << front << endl;
	cout << "동전의 뒷면 :" << rear << endl;

	return 0;
}

```

### 문자열의 문자 빈도를 계산하여 출력하는 프로그램

```c++
#include <iostream>
#include <ctime>
#include <string>
using namespace std;


int main()
{
	int counter[256] = { 0 };
	string s;
	cout << "문자열을 입력하세요: ";
	getline(cin, s);

	for (int i = 0; i < s.size(); i++) {
		counter[s[i]]++;
	}

	for (int i = 90;  i < 123; i++) {
		cout << (char)i << ": " << counter[i] << endl;
	}

}
```

#### 암호 안에 대문자, 소문자, 숫자가 모두 들어있어야 안전한 패스워드로 간주하는 프로그램

```c++
#include <iostream>
#include <ctime>
#include <string>
using namespace std;

bool is_UPPER(string s) {
	for (auto& e : s) {
		if (isupper(e))
			return true;
		return false;
	}
}

bool is_Lower(string s)
{
	for (auto& e : s)
		if (islower(e))
			return true;
	return false;
}

bool is_Number(string s)
{
	for (auto& e : s)
		if (48 <= e && e <= 57)
			return true;
	return false;
}

int main()
{
	string code;
	cout << "암호를 입력하시오: "; 
	cin >> code;

	if (is_UPPER(code) && is_Lower(code) && is_Number(code)) {
		cout << "안전합니다.";
	}
	else {
		cout << "안전하지 않습니다.";
	}

}
```
