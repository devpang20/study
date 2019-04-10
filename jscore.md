# 자바스크립트 핵심 개념

##scope(유효범위)
- 변수와 매개변수의 접근성과 생존기간
 
###global scope, local scope

```js
// 글로벌스코프
    var globla_scope = "global";
    // 로컬스코프
    function A(a_scope_param){
        var local_scope_a = "a";

        function B(){
            val local_scope_b = "b";
                function (){
                    var local_scope_c = "c"; 
            }
        }
    // 로컬스코프
    }
// 글로벌스코프
```

- 함수 단위 유효범위

```js
    var scope = 10;
    function scopeA(){
        var scope = 20;
        console.log("scope = " + scope);
    }
    scopeA();
// scope = 20   
```

##호이스팅
```js
    function hositingExam(){
        console.log("value="+value);
        var value = 10;
        console.log("value="+value);
    }
    hositingExam();
```

##스코프체인

```js
    function a(){
        var a =1;
        function b(){
            console.log(a);
        }
        b();
    }
    a();

    // 1
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