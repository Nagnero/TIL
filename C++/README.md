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
<br><br>

---

## algorithm 헤더파일

다양한 알고리즘 관련 함수들이 정리되어있는 라이브러리

- `#include <algorithm>`을 통해 이용할 수 있음
- 두가지를 개체를 비교하는 `max`나 `min`
- 지정된 범위내 요소를 지정한 정렬 기준에 따라 정렬하는 `sort`
- 지정된 범위내 요소를 난수생성기로 순서를 섞는 `shuffle`
 
[공식홈페이지](https://docs.microsoft.com/ko-kr/cpp/standard-library/algorithm?view=msvc-170)
<br><br>

### sort 함수 (벡터)

다양한 정렬 알고리즘이 있지만 sort함수만큼 빠르지는 않음

- 기본적으로 오름차순 정렬을 수행 → 배열의 시작점 주소와 마지막 주소 ex)`sort(array.begin(), array.end())`
- 세번째 인자를 추가함으로 원하는 형태의 정렬을 정할 수 있음
    - 오름차순(default): `sort(v.begin(), v.end(), less<type>())`
    - 내림차순: `sort(v.begin(), v.end(), greater<type>())`
    - 사용자 정의함수: `compare`을 사용하고 따로 함수를 지정
        
        ```cpp
        #include <algorithm> // sort함수를 사용하기 위한 헤더파일
        
        bool compare(int a, int b)
        {
        	return a > b;
        }
        
        int main(void)
        	sort(v.begin(), v.end(), compare); // compare함수에 의해 내림차순 정렬이 됨
        
        ```
        
    
    → compare함수에서 왼쪽(a)이 오른쪽(b)보다 크다는 의미가 되므로 내림차순 정렬
<br><br>
    

### unique 함수

vector 배열에서 중복되지 않는 원소들을 앞에서부터 채워나가는 함수

- 실행 전 정렬되어 있어야함 (sort 함수)
- 중복되어 밀리게 된 원소의 시작 부분의 주소를 return
- 보통 sort함수와 unique, erase함수를 통해 중복 원소를 제거하는 데에 쓰임

```cpp
vector<int> v = {1, 2, 5, 3, 1, 2, 4, 4};

sort(v.begin(), v.end());
v.erase(unique(v.being(), v.end()), v.end());
```
<br>

### remove 함수

특정 범위 안에 있는 특정 값을 삭제할 수 있음

- `remove(first, last, 삭제하려는 값)` 으로 이용
- 반환값으로 삭제되지 않은 마지막 값의 바로 뒤 반복자를 return
- vector헤더파일의 `erase`와 비슷하지만 다름

+. 주의점

![](/image/remove함수.png)
출처: [https://velog.io/@cse_pebb/C-remove-함수-vs.-vector의-erase-함수](https://velog.io/@cse_pebb/C-remove-%ED%95%A8%EC%88%98-vs.-vector%EC%9D%98-erase-%ED%95%A8%EC%88%98)
<br><Br>

### find 함수

범위 안에 원하는 값을 찾는 함수

- `find(v.begin(), v.end(), val)`로 사용
- 범위 안 (begin부터 end까지)의 원소들 중에서 val과 일치하는 첫번째 값의 반복자 return
- 범위는 주소값으로 넣어줘야 함
<br><br>

---

## vector 헤더파일
<br>
자동으로 메모리가 할당되는 배열

- `#include <vector>`을 통해 이용할 수 있음
- 자료구조 스택과 비슷한 형태
- 중간값 삽입 및 삭제도 가능하지만, 배열기반이므로 비효율적

### 생성자와 연산자

- `vector<int> v` : 비어있는 벡터 v를 생성
- `vector<int> v(5)` : 기본값(0)으로 초기화된 5개의 원소를 가지는 벡터 v를 생성
- `vector<int> v(5, 2)` : 2로 초기화된 5개의 원소를 가지는 백터 v를 생성
- `vector<int> v2(v1)` : 벡터 v1을 v2에 복사하여 생성
- `vector<vector <int>> v` : 2차원 벡터 생성 (열과 행 모두 가변)
- `vector<int> v[]` : 2차원 벡터(배열 벡터) 생성 (열은 고정, 행은 가변)

### 멤버함수

- `v.at(idx)`와 `v[idx]` : idx번째 원소를 참조, 전자는 범위를 점검하므로 더 느리지만 안전함
- `v.front()` : 첫번째 원소를 참조; **값**을 반환
- `v.back()` : 마지막 원소 참조; **값**을 반환
- `v.begin()` : 벡터 시작점의 **주소값**를 반환
- `v.end()` : 벡터의 끝부분 + 1 의 **주소값**을 반환 (빈 벡터를 표현하기 위해) → **반복자**라는걸 반환
- `v.size()` : 원소의 개수를 반환
- `v.capacity()` : 할당된 공간의 크기를 반환
- `v.push_back()` : 마지막 원소 뒤에 괄호 안의 값을 삽입
- `v.clear()` : 모든 원소를 제거, 원소만 제거하고 메모리는 그대로 유지
- `v.erase(first, last)` : 범위 안에 속하는 모든 값들을 삭제 (last는 범위에 포함되지 않음)

---

## set 헤더파일
<br>

- `#include <set>` 을 통해 이용
- `set<type> 변수명` 을 통해 선언
- 숫자든 문자든 중복을 없앰
- 삽입하는 순서에 상관없이 정렬되어 입력
- 밸런스 트리구조
    
    ![](image/%EB%B0%B8%EB%9F%B0%EC%8A%A4%20%ED%8A%B8%EB%A6%AC%EA%B5%AC%EC%A1%B0.png)
    

- 중복되면 사라지기에 value값은 확인 불가하고 key값이 입력되었는지 확인하는데에 용이
<br><br>

---

## 동적 프로그래밍 vs 동적 할당
<br>

<u>**동적 프로그래밍(Dynamic Programming)**</u>

- 메모리를 적절히 사용하여 수행시간 효율성을 향상시키는 방법
- 이미 계산된 결과는 별도의 메모리 영역에 저장하여 다시 계산하지 않도록 함
- 일반적으로 Top-down(하향식)방식과, Bottom-up(상향식)방식으로 나뉨
- 동적 계획법이라고도 함

<u>**동적할당**</u>

- 자료구조의 하나로 프로그램이 실행되는 도중에 실행에 필요한 메모리를 할당하는 기법
