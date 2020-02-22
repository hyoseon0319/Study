# JavaScript

## 1-1 JavaScript란?
- 객체 기반의 스크립트 프로그래밍 언어이고 웹 브라우저내에서 주로 사용하며, 다른 응용프로그램의 내장 객체에도 접근할 수 있는 기능을 가지고 있다.
- 
## 1-2 JavaScript의 특징
1) 인터프리터 언어다.
- 코드가 위에서 아래로 순차적으로 실행되고 즉시 결과가 반환됨
2) 동적 프로토 타입 기반 객체지향 언어다.
3) 함수가 일급 객체다.
4) 함수가 클로저를 정의한다.

## 1-3 자바스크립트의 기본 구성
```
<script = "text/javascript">
    스크립트 소스코드
</script>
```



#### HTML 내용 변경
document.getElementById('id속성값').innerHTML='바꾸고자 하는 내용'

```
getElementById()

-get(가져오다) Element(요소)

ById(Id로부터)

태그안의 ID값을 이용해서 오브젝트에 접근할 수 있음

document.getElementById('id속성값') : document 객체의 내장함수이므로 앞에 document. 이 붙음

ex) 
<div id="ex1">before</div>
<button onclick= "document.getElementById('ex1').innerHTML='바꾸고자 하는 내용'">내용변경</button>
<button onclick= "document.getElementById('ex1').innerHTML='before'">되돌리기</button>
```


#### HTML 속성 변경

classList 프로퍼티 (자바스크립트의 DOM 객체의 class를 조작)

```
★ 메소드

add : Elements에 클래스를 추가  ex) element.classList.add('bold')

remove : Element에 클래스를 제거 ex) element.classList.remove('bold')

toggle : Element에 클래스가 존재하면 제거하고 없으면 추가 ex) element.classList.toggle('open')

contains : Element에 클래스가 존재하는지 확인 ex) element.classList.contain('open')

replace : Element에 클래스를 새로운 클래스로 교체 ex) element.classList.replace('bold','italic')
- bold 클래스를 italic 로 교체

item(index) :  해당 위치의 클래스를 반환
```
```
ex) <div id="ex2">TEST</div>
       <button onclick="document.getElementById('ex2').classList.add('bold')">굵게</button> 
```


#### HTML 스타일 변경

visibility= 'hidden' | 'visible'
display= 'none' | ' ' (기본값)
```
ex) <button onclick="document.getElementById('ex3').style.visibility='hidden'">안 보이게</button>
```


#### JavaScript 문법

1) 세미콜론(;)으로 구분
- 자바스크립트는 줄 단위로 실행하기 때문에 문장 별 구분을 위해 세미콜론 해줘야함
```
ex) let x = 10;
      let y = "철수";
```

2) 주석문
-  한줄 주석 : // 
-   여러줄 주석 : /**/
```
// 으로 주석을 나타냄
    /* 여러 
    줄 주석 (CSS와 유사) */ 
    // cf. HTML 주석
```
3) 따옴표
- 따옴표는 중복해서 사용할 수 없음
4) 대소문자 구분


##### 리터럴은 직접 표현되는 값 자체
 - 12 // 숫자 리터럴
 - 'JavaScript' // 문자열 리터럴

     let x = 10;  // 10 : 숫자 리터럴 
     let y = "철수";  // 철수 : 문자 리터럴
  
    => let x , let y는 식별자
    => console.log 도 식별자


##### JavaScript는 " "(큰따옴표)와 ' '(작은따옴표) 혼용해서 사용

★HTML 같은 경우에는 속성을 큰따옴표를 입력을 주로 하기 때문에 작은따옴표로 입력하는 습관을 들일 것


##### 식별자는 자바스크립트 내에서 사용되는 이름을 의미
- 영문자(대소문자), 숫자, 언더스코어(_) 또는 $(달러)만 사용 가능
- 식별자는 숫자로 시작할수 없음
    ex) let var1 = 7;
     let var_2 = 12;
     let $var3 = 19;
     let 4var4 = 20;   (x)


##### 자바스크립트는 대소문자를 구분
    ex) let abc = 10; 
        let Abc = 20;


##### 개발자 도구 콘솔에 메시지를 출력해주는 함수(기능)
```
   console.log('Hello World");
 ex) console.log(abc); // 10
      console.log(12);
      console.log("javascript");
```

##### 자바스크립트 삽입을 어디에 할까요? 

	head 태그 vs body 태그 

	=> body 태그 하단 (  head 태그에 넣으면 작동하지만 느림 ) 
CSS가 맨 위에 있어야 모든 걸 포괄해서 일괄적으로 작동을 할 수 있기 때문에 헤드 태그 안에 있는 거예요.
그렇기 때문에 자바스크립트 중에 모든 어떠한 걸 지정을 하고 작동을 해야 되는 게 있다면 헤드 안에 들어가 있는 게 맞겠죠.




##### HTML 내부, 외부 script 태그

1. <head> 태그 안
 <script>
        // HTML 내부 script 태그 : head
        document.getElementById('head').innerHTML = "hello world";
    </script>
    <!-- 외부 script 파일 : head -->
    <script src="myJS.js"></script>


2. <body> 태그 안
<script>
    // HTML 내부 script 태그 : body
    document.getElementById('body').innerHTML = "hello world";
    document.getElementById('body').style.backgroundColor = 'red';
    </script>
    <!-- 외부 script 파일 : body -->
    <script src="myJS.js"></script>


#### 출력

##### 개발자 도구 실행 - console
- console.log() : 웹 브라우저(개발자 도구) 콘솔을 통해 데이터 출력
	>console.log("console.log() 출력");


- alert() : 대화 상자를 띄워 데이터 출력
	>alert('alert() 출력');

- document.write() :
    >웹 페이지가 로딩될 때 실행되면, 웹 페이지에 가장 먼저 데이터를 출력합니다.
= script 블록 위치에 따라


- innerHTML : 특정 요소를 찾아 그 안에 데이터 출력
```
<div id="place1">값</div>
<button onclick="alert('왜 눌러!')">누르지마시오</button>

document.getElementById('아이디') 로 특정 요소를 찾아, 그 속에 innerHTML로 태그, 스타일 값 등을 넣어준다
```

#### 변수와 상수

**var : 변수**
- 변수(變數) : 변화하는 값에 특정한 이름을 붙여준 것
- 선언 (변수의 자리 만들어주기)
undefined -> 선언만하고 초기화 안해줬을 때의 변수값
초기화 (변수에 값 지정해주기)
 = 을 통해 값을 대입한다
선언한 다음에는 맘껏 초기화를 할 수 있음
가장 마지막에 초기화=대입 된 값이 변수의 값
연산자를 통해 값을 계산해서 대입할 수 있음 (연산자는 차후 설명)

> var에는 치명적인 문제가 있는데
var를 통해 생성된 변수는 계속 선언할 수 있음

- 선언 : 의미적으로 중복되지 않는 값들을 추가로 만들어내는 것
var는 중복 선언을 허용하다보니 실수 혹은 여러 스크립트 간 혼합될 확률이 높음
=> 그래서 만들어진 것이 " let " (= 새롭게 창조한다) 

- let은 중복해서 선언하면 오류가 남

**블록 선언**
> block 안에는 변수가 없는 상태이므로
 block 안에는 새롭게 선언 가능 (이후 전역변수, 지역변수 개념에서 상세 설명)
{ } 블록 밖에서 블록의 값 못보기 때문에 블록 이전의 값이 출력됨

**const : 고정 선언**
- 한 번 선언&초기화 하면 변화하면 안 되는 수의 경우 const를 통해 상수(常數) 선언 가능
- 두 번 이상 초기화할 수 없음

```
-var : 중복 선언, 여러 번 초기화
-let : 한 번 선언, 여러 번 초기화 
-const : 한 번 선언, 한 번 초기화

(1) 기본적으로는 const 사용
(2) 재할당이 필요한 경우, 한정해 let을 사용
(3) var는 일단 안녕. 그리울거야 T_T
```
#### 타입

1) Number(숫자형)

```
        console.log(10); // 양수 
        console.log(-128); // 음수
        console.log(13.02);   // 소수
        // 자바스크립트는 정수와 실수를 따로 구분하지 않고, 모든 수를 실수 하나로만 표현
        console.log(1 / 3);
        // 숫자끼리의 연산 값 (이후 연산자에서 자세히)
```

2) String(문자열)
```
// 큰따옴표("")나 작은따옴표('')로 둘러싸인 문자의 집합을 의미

        console.log("큰따옴표");
        console.log('');
        console.log('작은따옴표');


        document.write('<a href="http://naver.com">네이버</a>') (o)
        // document.write("<a href="http://naver.com">네이버</a>") (x)
        console.log(`백틱`);

        console.log("큰따옴표 안에 '작은 따옴표'");
        console.log('작은따옴표 안에 "큰 따옴표"');

        console.log(`백틱 속 "큰따옴표"와 '작은 따옴표'`);

        console.log(`백틱은 괜찮습니다`);
        // console.log('
        // 엔터는 반영안됨');   

        console.log('역슬래시(\\)를 \붙여줘도 됩니다');
        
```
3) Boolean(불리언)
- 참(true)과 거짓(false)을 표현
- 어떤 조건을 만족시키는지, 아닌지 (10은 15보다 큰가? a와 b는 같은가? 지금 비가 오고 있는지?)


#### 연산자
##### 산술 연산자
- 사칙연산을 다루는 가장 기본적이고 많이 사용하는 연산자
- 연산자의 대상에 되는 값 = 피연산자
ex) + , - , * , / ,  %(모듈러스): 나머지값 , ** (제곱) , 괄호에 따른 우선순위, 변수도 연산자로 계산 가능, 문자열이 포함되었을 경우, 덧셈 연산시 결합시켜줌

##### 증감 연산자
- 피연산자를 1씩 증가 혹은 감소 시킬 때 사용하는 연산자
- 증감연산자가 왼쪽에 있으면 값을 증감시키고 연산을 수행 ( --c , ++c )

``` 
        console.log(c); // 10
        console.log(c++); //  10
        console.log(c); // 11
        
        console.log(++c); //12
        console.log(c); //12

        console.log(c--); //12
        console.log(c); //11
        
        console.log(--c); //10
        console.log(c); //10
        
```

##### 대입 연산자
- 변수에 값을 대입할 때 사용 
>ex) let x = 10;

##### 복합 대입 연산자
- 산술 연산자와 결합한 다양한 복합 대입 연산자가 존재 
>ex) x *= 4;

##### 조건 관련 연산자
> true, false
##### 비교 연산자
- 일반적으로 '부등호/등호'와 같은 방식으로 연산
- !는 not을 의미함, 즉 != 은 같지 않다 를 의미
- typeof (피연산자) : type을 알려주는 연산자
```
 ===, !== (타입도 같이) ==는 동등 연산자, ===는 일치 연산자

    * 타입이 달라도 자바스크립트가 자동변환해줌
     console.log(x == y); // true, 타입이 다르지만 자동변환돼서 x와 y는 같음!
     console.log(x === y); // false, 타입도 일치하는지 봄 ( x와 y는 타입이 다름)
     console.log(x != y); // false, 자동변환 돼서 x와 y는 같음 
     console.log(x !== y); // true, x와 y는 타입이 다름
 ```

 ##### 논리 연산자
- 논리 AND 연산 : 두 피연산자 모두가 참이어야 참
> console.log('and', t && f); //false
- 논리 OR 연산 : 두 피연산자 중 하나 이상이 참이어야 참
> console.log('or', t || f); //true
- 논리 NOT 연산 : 참/거짓 값을 바꿈 (true->false, false->true) 
> console.log('not', !t);

##### 조건문
**if**
- 조건을 만족할 때의 실행을 정해줌
> if (조건식) {실행문}

- 조건을 만족하지 않을 때에 어떤 내용을 실행할지도 작성

**else if**
- 다양한 조건을 지정하는 방법
- 위에 있는 부분이 먼저 검사되므로 if-else if 조건문 간의 순서를 잘 생각해야함


let random = Math.random();
< 0 이상 1 미만의 값을 임의로 만들어주는 함수(기능) >

prompt
- 값을 입력 받을 수 있는 창을 띄우는 함수 (기능)
- prompt는 입력 받은 값을 모두 문자열로 인식하기 때문에 숫자로 바꿔줘야 함
- parseInt라는 함수를 사용하면 숫자로 된 문자열을 숫자로 바꿔줄 수 있음
>  if (!parseInt(num)){ }

##### 반복문
1) while
- 특정 조건이 참인 경우에만 계속 반복하는 while
> while (표현식) {표현식이 참인 동안 반복적으로 실행하고자 하는 실행문}

- 증감연산이 중요한 이유 - 없으면 무한루프에 빠짐 ex) w++;

```
* 탈출할 길이 없어서 무한 루프에 빠짐

                let w2 = 0;
                while (w2 > -1){
                    break;
                
                    w++;
                    document.write("w2는 " + w2 + "<br>");
                }

=> 끝이 없는 반복을 만들고 싶으면 조건문 안에 불리언값을 true 로 넣으면 됨
```

2) for
- 특정 횟수만큼 반복하는 for
> for (초기식; 표현식; 증감식) {표현식의 결과가 참인 동안 반복적으로 실행하고자 하는 실행문}


**간단한 과제**
```
  //과제
        문제1. 월 이율 10%인 상품에 100만원을 투자했을 때 200만원이 되려면 몇 달이 필요한가?
        let money = 100, month = 0;
        while (money < 200) {
            money *= 1.1;
            money++;
        }
        console.log("while",month);

        for (month = 0; money < 200; money++) {
            money *= 1.1
        }
        console.log("for"month);

        문제2. 월 이율 5%인 상품에 150만원을 투자했을 때 2년 후 얼마인가?
        let money = 150, month = 0;
        while (month < 24) {
            money *= 1.05;
            month++;
        }
        console.log("while",money);
 
        for (money = 150, month = 0; month < 24; month++) {
            money *= 1.05;
        }
        console.log("for",money);
```
-----------------------------------
##### 자바스크립트 코딩 테스트에서 가장 많이하는 실수들

**1) var, let 그리고 const**
 var 만 사용하든지, let 과 const 만 사용한다(추천)
 var 와 let, const 모두를 섞어 쓰지 말자

**2) 세미콜론 ;**
세미콜론을 항상 사용하자. 

**3) 일치 연산자**
항상 === 을 사용하자

**4) 불변성**
- 인자로 들어온 값을 수정하지 않기. (함수가 데이터 받을 때 객체 원본 바뀌는 것 조심)

- 새 객체에 깊은 복사로 값을 복사해서 사용하자.
   =>특히 자바스크립트 내장 메소드인 sort 사용할 때 주의
```
function sortByAges(array) {
  const _array = array.slice();
  _array.sort((a, b) => a.age - b.age);
  return _array;
}
```
**5) 삼항 연산자**
> return a ? b : c의 깔끔한 형태가 아니라면 그냥 if 쓰기


#### 

​
모던 자바스크립트 깃허브 예제
https://github.com/gilbutITbook/006960

TCP.school.com
http://tcpschool.com/javascript/js_intro_output