
# 문서 객체 모델(DOM, Document Object Model)
HTML 문서 구조를 말하며, 문서 객체 모델에서는 Document 객체 아래 HTML 요소들이 트리 구조를 형성하고 있다.

트리 구조에 있는 HTML 요소, 즉 객체에 접근하여 요소의 내용을 바꾸거나 설정된 CSS를 변경할 수 있다.

자바스크립트 DOM의 메서드와 속성을 이용하여 HTML 요소를 다룰 수 있지만, 제이쿼리에서는 자바스크립트보다 더 쉽고 편리하게 DOM을 처리할 수 있는 라이브러리를 제공한다. 실제 프로그램에서는 자바스크립트보다 제이쿼리에서 DOM을 처리하기도 한다.



## 문서 객체 모델의 트리구조

Document
<html>
<head>	<body>
<title>	<meta>	<h3>	<p>	<div>


### ① DOM 기본구조
~~~
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>페이지 제목</title>
</head>
<body>
<h2>큰 제목</h2>
<p id="result"></p>
</body>
</html>
~~~
html 요소 아래에는 head와 body 요소가 위치하며 그 아래에는 title, meta, h3, p 요소들이 위치하고 있다.

charset과 id는 각각 meta와 p요소의 속성이다. charset은 UTF-8 속성 값을 갖고, id는 result 속성 값을 가진다.


### 요소 내용 삽입과 CSS 조작
~~~
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>페이지 제목</title>
</head>
<body>
<h2>큰 제목</h2>
<p id="result"></p>
	<script>
        document.getElementById("result").innerHTML = "안녕하세요.";
        document.getElementById("result").style.color = "red";    
    </script>
</body>
</html>
~~~
위와 같이 자바스크립트 코드를 추가하면 innerHTML로 <p>태그로 안녕하세요가 추가된다. 그리고 p태그의 id 속성 값 result에 점(.)으로 접근하여 색상을 red로 지정해 주었다.



## DOM의 이벤트

웹 브라우저에서 DOM의 요소에 마우스를 클릭하는 것과 같은 이벤트가 발생하면 원하는 자바스크립트 코드를 실행하도록 할 수 있다.

- onclick 속성 : 요소에 마우스 클릭 이벤트가 발생하였을 때 이벤트를 처리하는 자바스크립트 함수를 설정하는 데 사용 된다.

- onmouseover 속성 : 마우스가 올려졌을 때 발생되는 이벤트 처리 자바스크립트 함수를 설정하는 데 사용 된다.

- onmouseout 속성 : 마우스가 벗어났을 때 발생되는 이벤트 처리 자바스크립트 함수를 설정하는 데 사용 된다.