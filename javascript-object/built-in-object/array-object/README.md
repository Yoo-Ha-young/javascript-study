# 자바스크립트 객체(Object)

자바스크립트는 객체기반의 언어로 자바스크립트를 이루고 있는 거의 모든 것이 객체이다. 숫자, 문자열, 배열 등도 모두 객체를 기반으로 한다.

자바스크립트의 객체는 속성(Property)과 메서드(Method)로 구성된다. 속성은 객체에 붙어있는 변수이고 메서드는 객체에 붙어있는 합수이다.

하나의 객체는 속성과 데이터를 처리하는 기능을 가진 메서드의 집합이라 할 수 있다.

변수는 데이터를 저장하고 있는 메모리 공간이며 객체도 일종의 변수이다. 그러나 각 객체의 요소들은 키와 값으로 구성되며 객체 자체의 함수인 메서드를 가질 수 있다.

~~~
<script>
	var person = {
    	name : "홍길동",
        age : 25,
        sayHello: function() {
        	document.write(this.name + "님 안녕하세요!");
        }
    };
    
    document.write("이름:" + person.name + "<br>");
    document.write("나이:" + person.name + "<br>");
    person.sayHello();
</script>
~~~


① 객체 리터럴(Object Literal)
리터럴은 데이터 형에 들어가는 데이터 값 자체를 의미한다.

변수 선언할 때와 유사한 방식으로 객체에 들어가는 속성과 메서드를 직접 정의한다.

var 객체명 = {
	// 속성 정의
	키1 : 값1,
    키2 : 값2,
    ...
    // 메서드 정의
    메서드1 : function() {
    	// 자바스크립트 코드
    },
    메서드2 : function() {
    	// 자바스크립트 코드
    },
    ...
};
각 속성은 키와 값으로 정의되고, 메서드들은 익명함수의 형태로 정의된다.



② New 연산자와 생성자 함수(Constructor) 이용
생성자 함수를 이용하여 객체의 타입을 정의한다.
생성자 함수의 첫 글자는 반드시 영문 대문자를 사용하도록 한다.
new를 이용하여 객체를 생성한다.
<script>
    function Car(company, model, year) {
    	this.company = company;
        this.model = model;
        this.year = year;
    }
    
    var car1 = new Car("현대", "아반떼", 2021);
    document.write(car1.company + "/" + car1.model + "/" + car1.year + "<br>")

    var car2 = new Car("르노 삼성", "SM6", 2021);    
    document.write(car2.company + "/" + car2.model + "/" + car2.year + "<br>")

<script>
생성자 함수 Car()가 정의 되었으며 속성으로 company, model, year 3개가 구성된다. 생성자 함수에서 사용된 this는 이 생성자 함수 Car에 의해 생성되는 객체를 가리킨다. 따라서 this.company는 new 연산자에 의해 생성되는 객체의 속성 company 현대와 르노 삼성이 된다. 화면에는 c1은 현대/아반떼/2021로 출력되고 c2는 르노 삼성/SM6/2021이 출력된다.





③ 객체의 속성 접근법
ⓐ 객체명. 키 : 객체명 다음에 점(.) 다음에 키를 사용

ⓑ 객체명["키"] : 객체명 다음에 대괄호([])에 키(문자열)를 사용



<script>
	var obj1 = {
    	name : "박혜린",
        age : 22,
    };
    
    document.write(obj.name + "<br>");
    document.write(obj.age + "<br>");
	
    document.write(obj["name"] + "<br>");
    document.write(obj["age"] + "<br>");
</script>


④ for in 문으로 객체 사용
for in 구문은 자바스크립트에서 객체의 속성에 반복해서 접근하려고 할 때 사용한다.

for(변수명 in 객체명) {
	문장1;
    문장2;
	...
}
객체명의 객체에 대해 반복 루프를 수행하며, 자바의 for-each문과 비슷하다. 각 반복 루프에서 변수명은 객체의 키 값을 가지고 문장1, 문장2, ... 를 수행한다.



for문을 이용하면 객체의 속성을 반복해서 읽어올 수 있다.

<script>
	var obj1 = {
    	name: "박정수",
        age: 22,
        address: "서울"
    };
    
    var str = "";
    for(var x in obj1)
    	str += obj1[x] + "<br>";
        
    document.write(str);
</script>



// 출력 결과
박정수
22
서울
루프를 돌면서 빈 문자열 str에 obj의 인덱스를 순차적으로 넣어주며 document.write로 str에 쌓인 데이터를 출력한다.

내장 객체(Built-in Object)
기본적으로 내장되어 있는 객체로 별도의 정의가 필요없다. 내장 객체를 이용할 때는 필요 시 해당 내장 객체로부터 객체를 생성하여 내장 객체에서 제공하는 속성과 메서드를 사용하면 된다.



내장 객체에는 배열(Array), 숫자(Number), 문자열(String), 수학(Math), 날짜(Date)객체가 있다.


① Number 객체의 메서드
toString() : 숫자를 문자열로 변환하는 데는 Number 객체의 toString() 메서드가 사용된다. 
<script>

    var a = 10;
    var b = 20;
    var c;
    
    c = a + b;
    document.write(c + "<br>");
    
    c = a + b.toString();
    document.write(c);

</script>
변수 c에 a+b의 연산된 값을 담아 write로 출력을하는 코드이다. 그냥 a+b로 c에 할당할 경우 숫자로 연산되어 30이란 값이 출력되는데, .toString()이 b에 붙으면 숫자 더하기 문자열이 되어 1020이라는 값이 출력된다.





toFixed() : 실수에서 소숫점 이하 자리수를 구하는 데 사용된다.
<script>
    var x = 12.4763;
    
    document.write(x.toFixed(0) + "<br>");
    document.write(x.toFixed(1) + "<br>");
    document.write(x.toFixed(3));

</script>


// 출력결과
12
12.5
12.476

② 문자열의 숫자 반환
문자열을 숫자로 변환하는 데에는 Number(), parseInt(), parseFloat()가 사용된다. 이 함수들은 Number객체의 메서드가 아니라 전역 함수(Global function)이다. 전역함수이기 때문에 다른 메서드와는 달리 함수 호출에 함수명이 그대로 사용된다.



Number() : 어떤 객체의 값을 숫자로 변환
parseInt() : 문자열을 정수로 변환
parseFloat() : 문자열을 실수로 변환
String() : 어떤 객체의 값을 문자열로 변환
<script>
    var x = "10.33";
    
    document.write(Number(x) + "<br>");
    document.write(parseInt(x) + "<br>");
    document.write(parseFloat(x) + "<br>");
	
    var x = "apple";
    document.write(Number(x));
</script>


// 출력결과 
10.33
20
10.33
NaN
만약 Number()함수에 영문자나 한글 같이 숫자로 변환하기에 어려운 값이 적용될 때는 NaN값이 반환된다.





③ Array객체 
배열은 하나의 변수로 여러 개의 데이터를 저장할 수 있게 해준다. 자바스크립트의 배열은 Array 객체를 기반으로 하고 있다. Array 객체에서는 배열의 문자열 변환, 배열 요소의 추가와 삭제, 배열 요소의 이동, 배열의 연결, 등 을 가능하게 해주는 다양한 메서드들을 제공한다.



toString() : 배열 요소 값들을 콤마로 분리된 문자열로 반환
<script>
	var animals = ["사자", "호랑이", "사슴", "펭귄"];
    var str = animals.toString();
    document.write(str + "<br>");
    document.write(typeof(str));
</script>


// 출력 결과
사자,호랑이,사슴,펭귄
string
typeof()메서드로 str의 타입을 확인해보면 string타입으로 변환되었음을 확인할 수 있다.



push() : 배열에 새로운 요소 추가
<script>
	var animals = ["사자", "호랑이", "사슴", "펭귄"];
    
    animals.push("기린");
    document.write(animals + "<br>");
    
    var x = animals.push("이구아나");
    document.write(x + "<br>");
    document.write(animals);
</script>


// 출력 결과
사자,호랑이,사슴,펭귄,기린
6
사자,호랑이,사슴,펭귄,기린,이구아나
변수 x의 값을 출력하면 배열 요소 개수가 반환된다. 배열의 요소 값들을 출력하려면 배열 변수명을 써서 출력해야한다.



pop() : 배열의 마지막 요소 삭제
<script>
	var animals = ["사자", "호랑이", "사슴", "펭귄"];
    animals.pop();
    document.write(animals + "<br>");
    
    var x = animals.pop();
    document.write(x + "<br>");
    document.write(animals);
</script>

// 출력결과
사자, 호랑이, 사슴
사슴
사자, 호랑이
두번째의 출력결과는 x에 animals에서 처음 pop하고 남은 사자, 호랑이, 사슴 중에서 사슴을 pop으로 꺼내서 담았다.

그리고 x를 출력하면 사슴이 나오고, 이후 animals를 출력하면 사자, 호랑이가 나온다.  

splice() : 배열에 요소 삽입
배열변수명.splice(삭제를 시작할 위치 인덱스, 삭제할 갯수, '삭제하고 대체할 값');
<script>
	var animals = ["사자", "호랑이", "사슴", "펭귄"];
    animals.splice(2, 2, "곰");
    document.write(animals + "<br>");
    
    animals.splice(2, 0, "원숭이");
    document.write(animals);
</script>


// 출력결과
사자,호랑이,곰       
사자,호랑이,원숭이,곰
    animals.splice(2, 2, "곰") 은 배열의 인덱스 2인 사슴부터 펭귄까지 2개를 삭제한 후 그 자리에 곰을 삽입해서 사자, 호랑이, 곰이 출력된다. animals.splice(2, 0, "원숭이")는 [사자, 호랑이, 곰] 배열에서 2번째 위치인 곰에서 매개변수가 0으로 삭제는 이루어지지 않고 원숭이만 삽입하여  사자, 호랑이, 원숭이, 곰이 출력된다.



slice() : 배열에서 특정요소 추출
기타 메서드


sort() : 배열의 요소를 오름차순으로 정렬
reverse() : 배열의 요소를 내림차순으로 정렬


요소 값 변경과 length 속성
배열의 인덱스가 가리키는 요소에 값을 저장함으로써 배열의 요소 값을 변경할 수 있다.

그리고 length 속성은 배열의 길이, 즉 배열 요소의 개수를 구하는 데 사용된다.



문서 객체 모델(DOM, Document Object Model)
HTML 문서 구조를 말하며, 문서 객체 모델에서는 Document 객체 아래 HTML 요소들이 트리 구조를 형성하고 있다.

트리 구조에 있는 HTML 요소, 즉 객체에 접근하여 요소의 내용을 바꾸거나 설정된 CSS를 변경할 수 있다.

자바스크립트 DOM의 메서드와 속성을 이용하여 HTML 요소를 다룰 수 있지만, 제이쿼리에서는 자바스크립트보다 더 쉽고 편리하게 DOM을 처리할 수 있는 라이브러리를 제공한다. 실제 프로그램에서는 자바스크립트보다 제이쿼리에서 DOM을 처리하기도 한다.



* 문서 객체 모델의 트리구조

Document
<html>
<head>	<body>
<title>	<meta>	<h3>	<p>	<div>


① DOM 기본구조
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
html 요소 아래에는 head와 body 요소가 위치하며 그 아래에는 title, meta, h3, p 요소들이 위치하고 있다.

charset과 id는 각각 meta와 p요소의 속성이다. charset은 UTF-8 속성 값을 갖고, id는 result 속성 값을 가진다.



요소 내용 삽입과 CSS 조작
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
위와 같이 자바스크립트 코드를 추가하면 innerHTML로 <p>태그로 안녕하세요가 추가된다. 그리고 p태그의 id 속성 값 result에 점(.)으로 접근하여 색상을 red로 지정해 주었다.



DOM의 이벤트

웹 브라우저에서 DOM의 요소에 마우스를 클릭하는 것과 같은 이벤트가 발생하면 원하는 자바스크립트 코드를 실행하도록 할 수 있다.



브라우저 객체 모델(BOM, Browser Object Model)
자바스크립트에서 브라우저를 다루는 데 필요한 객체의 모델을 제공한다. BOM에는 Window, Screen, Location, History, Navigator 등의 객체가 있다. 이러한 객체의 속성과 메서드를 이용하여 브라우저에 관련된 처리를 할 수 있다.
