# Oriented_ProgrammingII_code
객체지향프로그래밍II C++ 연습문제 코드 정리 1장~6장

## 1장

## 주사위 게임 프로그램 작성

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

## 사용자의 나이를 물어보고 10년 후에는 몇 살이 되는지 출력하는 프로그램 작성
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

## 1평은 3.3058 이다. 평을 평방미터로 환산하는 프로그램 작성
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

## 시, 분, 초로 표현된 시간을 초 단위의 시간으로 변환하는 프로그램 작성
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
