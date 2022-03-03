# HTML
### 특징 
- Hypertext Markup Language
- 프로그래밍언어는 아님
- 크게 요소(Element)와 속성(Attributes)으로 구성

### 구조
- \<!DOCTYPE html> : 유효한 문서 형식을 나타내는 짧은 문장
- \<html> : 기본 요소로서 전체 페이지의 콘텐츠를 포함
- \<head> : 검색결과에 노출 될 키워드, 홈페이지 설명(title 태그), CSS 스타일 등을 포함  
사용자에게는 보이지 않음
- \<meta charset="uft-8"> : 문자 인코딩 설정을 uft-8로 지정  
uft-8은 전세계 대부분의 문자를 포함함
- \<title> : 브라우저 탭에 표시되는 제목
- \<body> : 텍스트, 이미지 등 페이지에 표시되는 모든 콘텐츠

### 요소(Element)
- 'opening tag'와 'closing tag'사이에 내용을 입력하여 나타냄  
ex) \<p> HTML practice \</p>  
- opening tag, closing tag, contents를 합쳐서 Element라 부름
- 'Block-level elements' : 한 덩어리로 나타남
- 'Inline elements' : Block-level 내에 포함되어 있고, 새로운 줄을 만들지 않음

### 속성(Attributes)
- Element에 추가적인 내용을 담을 때 사용  
 ex) \<p <u>class="base"</u>> HTML practice \<p> 
- 링크를 달 땐 'href' attribute를 사용
- 작은 따옴표나 큰 따옴표로 = 이후를 묶어줘야 함 (혼용은 불가)

### 특수문자
<img src="../image/entity reference.png" width="550">

### 이미지 참조
- \<img>태그를 이용, 닫는태그(\</img>)가 없음  
ex)\<img src="http://example_url.com">
- 문서를 통해서 참조도 가능  
. 은 한 폴더 위로, / 는 폴더 내부를 의미  
ex) \<img src="example/folder/image/jpg>

<br>

## Reference
[https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML/Getting_started#html_%EC%9A%94%EC%86%8Celement%EC%9D%98_%EA%B5%AC%EC%A1%B0](https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML/Getting_started#html_%EC%9A%94%EC%86%8Celement%EC%9D%98_%EA%B5%AC%EC%A1%B0)