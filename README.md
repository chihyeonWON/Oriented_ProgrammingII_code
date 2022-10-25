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

## 4장

### 복소수를 나타내는 Complex 클래스를 정의하라
```c++
#include <iostream>
using namespace std;

class Complex {
public:
	double r;
	double i;
	void print();
};

void Complex::print() {
	if (i > 0) {
		cout << r << "+" << i << "i" << endl;
	}
	else if (i < 0)
		cout << r << "-" << -i << "i" << endl;
}

int main()
{
	Complex c;
	c.r = 5;
	c.i = -4;
	c.print();

	return 0;
}
```

### 삼각형을 나타내는 Triangle 클래스를 정의하여 보아라.
```c++
#include <iostream>
using namespace std;

class Triangle {
private:
	int b, h;
public:
	Triangle(int width, int height) {
		b = width;
		h = height;
	};
	int area(int a, int b);
};

int Triangle::area(int a, int b) {
	int area; 
	return area = a * b/2;

}
int main()
{
	int width, height;

	cout << "삼각형의 밑변 : ";
	cin >> width;

	cout << "삼각형의 높이 : ";
	cin >> height; 

	Triangle tri(width,height);

	cout << "밑변이 " << width << "높이가 " << height << "인 삼각형의 면적: " << tri.area(width, height) << endl;
	return 0;
}
```

## 5장

### 영화를 나타내는 Movie라는 이름의 클래스를 설계, 제목, 감독, 평점을 나타내는 멤버 변수를 가진다.

1. 멤버 변수는 전용멤버로 한다.
2. Movie 클래스의 생성자를 중복 정의
3. 접근자와 생성자를 비롯한 필요한 멤버 함수 정의
4. main()에서 Movie 객체를 여러개 생성하고 접근자와 설정자를 호출하여 보라

```c++

#include <iostream>
#include <string>
using namespace std;

class Movie {
private:
	string title;
	string director;
	int rating;
public:
	Movie() {
		title = "";
		director = "";
		rating = 0;
	}
	Movie(string t, string d, int r) {
		title = t;
		director = d;
		rating = r;
	}
	string getTitle() { return title; }
	string getDirector() { return director; }
	int getRating() { return rating; }

	void setTitle(string t) { title = t; }
	void setDirector(string d) { director = d; }
	void setRating(int r) { rating = r; }

	void print();
};

void Movie::print() {
	cout << "영화 제목: " << title << endl;
	cout << "영화 감독: " << director << endl;
	cout << "영화 평점: " << rating << endl;
}

int main()
{
	Movie m1;
	Movie movie2("타이타닉", "하이", 1);
	movie2.print();

	return 0;
}
```

## 6장

### 정수입력받고 벡터에 저장한다음 최대값과 최소값을 출력하는 프로그램

```c++
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main()
{
	int num;
	int max, min;

	cout << "정수의 개수: ";

	cin >> num;

	vector<int> list(num);

	for (auto& e : list) {
		cout << "정수를 입력하시오: ";

		cin >> e;
	}

	max = min = list.front();

	for (auto& e : list) {
		if (max < e)
			max = e;
		if (min > e)
			min = e;

	}

	cout << "최대값: " << max << endl;
	cout << "최솟값: " << min << endl;
}
```


### 학생의 이름, 성적을 멤버 변수로 가지는 클래스의 동적 배열을 만들고 성적 순으로 학생들의 정보를 출력하라.

```c++
#include <iostream>
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

class Student {
private:
	string name; // 이름 
	double marks; // 성적
public:
	Student() {
		name = "";
		marks = 0;
	}
	Student(string n, double m) {
		name = n;
		marks = m;
	}
	// 접근자
	string getName() {
		return name;
	}
	double getMarks() {
		return marks;
	}
	
	// 설정자
	void setName(string n) {
		name = n;
	}
	void setMarks(double m) {
		marks = m;
	}

	void print() {
		cout << "이름 :" << name << endl;
		cout << "학점 :" << marks << endl;
	}
};

bool compare(Student& p, Student& q)
{
	return p.getMarks() > p.getMarks();
}
int main()
{
	vector<Student> list;
	list.push_back(Student("최자영", 4.3));
	list.push_back(Student("김영희", 3.8));
	list.push_back(Student("김철수", 3.9));

	sort(list.begin(), list.end(), compare);

	for (auto& e : list) {
		e.print();
	}

	return 0;
}
```

#### 연락처를 나타내는 Contact클래스에 3개의 Content 객체를 저장하는 동적배열을 정의하고 이름을 받아서 전화번호를 출력하는 프로그램 작성
```c++
#include <iostream>
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

class Contact {
private:
	string name; // 이름
	string tel; // 전화번호
public:
	Contact() {
		name = "";
		tel = "";
	}
	Contact(string n, string t) {
		name = n;
		tel = t;
	}
	// 접근자
	string getName() { return name; }
	string getTel() { return tel; }
	// 설정자
	void setName(string n) { name = n; }
	void setTel(string t) { tel = t; }
};

int main()
{
	string name;
	string tel;

	vector<Contact> list(3);

	for (auto& e : list) {
		cout << "이름을 입력하시오:";
		cin >> name;
		cout << "전화번호를 입력하시오.";
		cin >> tel;

		e = Contact(name, tel);
	}

	cout << "탐색하고 싶은 이름을 입력하시오: ";
	cin >> name;
	for (auto& e : list) {
		if (name == e.getName()) {
			cout << "전화번호 : " << e.getTel();
		}
	}
}



```
