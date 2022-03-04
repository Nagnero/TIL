# CSS

### 특징
- Cascading Style Sheets
- HTML이 구조라면, CSS는 비주얼 표현
- HTML에 CSS를 작성할수 있지만(\<style>태그) 관리를 용이하게 하기 위해 CSS파일로 디자인을 구분
---

### 문법
- 선택자(selector)와 선언부(declaratives)로 구성
```CSS
a {
  background-color: yellow;
  font-size: 10px;
}
```
- a가 선택자, 이후 중괄호로 묶인 부분이 선언부
- 선택자에는 HTML요소(태그), id(#a), class(.a) 등을 사용
- 주석 표현법:  
/*주석내용\*/  
---

### 적용방법
1. 인라인 스타일 (Inline style)
- HTML요소 내부에 style 속성 사용
- 해당 태그에만 스타일 적용
```HTML
<body>
  <h1 style="color:green; font-size:10px">
    인라인 스타일의 적용
  </h1>
</body>
```
2. 내부 스타일 시트 (Internal style sheet)
- HTML \<head>태그 내에 \<style>태그 사용
- 해당 HTML문서에만 스타일 적용
```HTML
<head>
  <style>
    body {
      background-color: green;
      font-size: 10px;
    }
    a {
      color: red;
    }
  </style>
</head>
```
3. 외부 스타일 시트(External style sheet)
- CSS파일을 따로 작성하여 저장
- 웹사이트 전체의 스타일에 적용
- 스타일을 적용할 웹페이지의 \<head>태그에 \<link>태그를 사용하여 포함시켜야함
```HTML
<head>
  <link rel="stylesheet" href="/link/adress/style.css">
</head>
```
+. 스타일 적용 우선순위  
1. 인라인 스타일
2. 내부/외부 스타일 시트
3. 웹 브라우저 기본 스타일
---

## Reference
[http://www.tcpschool.com/css/intro](http://www.tcpschool.com/css/intro)