## C++ auto
해당 자료형은 초깃값의 형식에 맞춰 변수의 형식이 자동으로 맞춰진다. 이를 타입 추론(type inference)라고 하고 덕분에 더욱 간편한 코드 작성이 가능해진다.
```c++
auto i = 1; // int i = 1
auto c = 'a'; // char c = 'a'
auto list = {1, 2, 3, 4}; // int[4] = {1, 2, 3, 4}
```
<u>주의사항</u> : `auto`는 함수의 매개 변수(parameter)에 사용 불가

```c++
#include <iostream>

int addAndPrint(auto x, auto y){ // compile error
  std::cout<<x + y;
}
```
<br>
<br>

## C++에서의 새로운 반복문
C언어와 달리 새로운 반복문 형태를 사용할 수 있음
```c++
#inlcude <string>
using namespace std

string s;

for(auto i : s){

} // s의 객체를 하나씩 i에 복사하여 반복 실행
```
<br>
<br>

## isupper(), islower()
문자를 판단하는 함수로 `isupper()`은 대문자인지, `islower()`은 소문자인지 판단함. 각각 참이면 1을 반환
```c++
char i = 'A';

if(i.isupper()){
  // i가 대문자이므로 해당 body 실행
}

if(i.islower()){
  // i가 대문자이므로 해당 body 실행 x
}
```