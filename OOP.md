## 객체지향프로그래밍

- 객체의 상태(state)와 행동(behavior)은 각각 프로퍼티(property)와 메서드(method)로 구현 할 수 있다.
- 객체의 설계도는 class 이다.
- PHP에서 클래스를 가지고 객체를 생성 사용한다.

### 객체의 5가지 특징
- 

가 무슨 말이나면

- class를 붕어빵 틀이라고 가정해보자.
- class를 정의한다.
```php 
    class fishTool{
        $name = "붕어빵"
        // 밀가루
        $flour   
        // 팥 
        $redBean
        function jump(){
            echo "up!up!";
        }
    }
```
- 생성한 객체를 
- 
  

- 프로퍼티(property)
```php
    $man->name = "홍길동";
    $man->age = 24;
    $man->footSize = 260;
```
- 메서드(method)

```php
    $man->jump();
    $man->run();
```
인스턴스(instance)
```php
    class man{
        $name = "홍길동";
    }
    // 인스턴스화 시키다
    $me = new man(); 

```