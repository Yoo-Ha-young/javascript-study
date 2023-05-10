# 사용자 정의 객체(User-defined Object)
사용자 즉 프로그래머가 객체의 속성을 정의하거나 메서드를 속성과 메서드를 함께 정의하여 객체를 프로그램에서 이용한다.

### ① 객체 리터럴(Object Literal)
리터럴은 데이터 형에 들어가는 데이터 값 자체를 의미한다.

변수 선언할 때와 유사한 방식으로 객체에 들어가는 속성과 메서드를 직접 정의한다.
~~~
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
~~~
각 속성은 키와 값으로 정의되고, 메서드들은 익명함수의 형태로 정의된다.



### ② New 연산자와 생성자 함수(Constructor) 이용
생성자 함수를 이용하여 객체의 타입을 정의한다.
생성자 함수의 첫 글자는 반드시 영문 대문자를 사용하도록 한다.
new를 이용하여 객체를 생성한다.
~~~
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

</script>
~~~
생성자 함수 Car()가 정의 되었으며 속성으로 company, model, year 3개가 구성된다. 생성자 함수에서 사용된 this는 이 생성자 함수 Car에 의해 생성되는 객체를 가리킨다. 따라서 this.company는 new 연산자에 의해 생성되는 객체의 속성 company 현대와 르노 삼성이 된다. 화면에는 c1은 현대/아반떼/2021로 출력되고 c2는 르노 삼성/SM6/2021이 출력된다.