# 객체(Object)

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
person이 하나의 객체이고, 이 객체는 속성 name, age, sayHello() 메서드로 구성된다.



### ③ 객체의 속성 접근법
ⓐ 객체명. 키 : 객체명 다음에 점(.) 다음에 키를 사용

ⓑ 객체명["키"] : 객체명 다음에 대괄호([])에 키(문자열)를 사용

~~~
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
~~~

### ④ for in 문으로 객체 사용
for in 구문은 자바스크립트에서 객체의 속성에 반복해서 접근하려고 할 때 사용한다.

for(변수명 in 객체명) {
	문장1;
    문장2;
	...
}
객체명의 객체에 대해 반복 루프를 수행하며, 자바의 for-each문과 비슷하다. 각 반복 루프에서 변수명은 객체의 키 값을 가지고 문장1, 문장2, ... 를 수행한다.



for문을 이용하면 객체의 속성을 반복해서 읽어올 수 있다.

~~~
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
~~~