# 자바스크립트 핵심 개념

##scope(유효범위) 와 호이스팅
- 변수와 매개변수의 접근성과 생존기간
 
###global scope, local scope

- 협업시 충돌날 가능성을 대비해 글로벌 스코프 보다는 로컬 스코프를 권장한다.

```js
    var globla_scope = "global"; //전역스코프
        var local_function = function() {
            var local_scope = 'local'; //지역스코프
            console.log(global_scope); //전역스코프 참조 가능. global
            console.log(local_scope); //한수 내이기 때문에 지역 스코프 참조 가능 local
        }
    console.log(local_scope); // local_scope은 지역 시코프이기 때문에 에러 발생

```
- 위와 같이 다른 함수끼리 참조할 수 가 없다.
- 하지만 함수 안의 함수는 참조 할 수 있을까?

##스코프체인

- inner->outer->global 꼬리에 꼬리를 무는 스코프 체인
- 반대로는 안된다.

```js
    var a = 1
    function outer(){
        var b =2;
        console.log(a)
        function inner(){
            var c =3;
            console.log(b);
            console.log(a);
        }
        inner();// 2 , 1;
    }
    outer();

    console.log(c);
```
## Lexical scope(정적 범위)
- 렉시컬 스코프란 어디서 호출하는지가 아니라 어떤 스코프에서 선언하였는지에 따라 결정된다.
- 
##호이스팅
```js
    function human(name){
        console.log("My name is" + name);
    }
    human("kim");

    // My name is kim

    human("kim");

    function human(name){
        console.log("My name is" + name);
    }

    // My name is kim
    
```



##클로저

```js
    var base = "name is :";
    function sayHello(name){
        var text = base + name;
        return function(){
            console.log(text);
        }
    }
    var test1 = sayHello('김일');
    var test2 = sayHello('김이');
    var test2 = sayHello('김삼');

    test1();
    //  name is : 김일
    test2();
    // name is : 김이
    test3();
    // name is : 김삼
    
```

- 반복문의 클로저

```js
    var i
    for (i = 0; i < 10; i++ ) {
        setTimeout(function() {
            console.log(i);
        }, 100);
    }
    // 결과
    // 10
    // 10
    // 10
    // 10
    // 10
    // 10
    // 10
    // 10
    // 10
    // 10

```
- 순차적으로 출력하기 

```js
   var i
    for (i = 0; i < 10; i++ ) {
        (function(j){
        setTimeout(function() {
            console.log(j);
        }, 100);
    })(i);
    }
```