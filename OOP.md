## 객체지향프로그래밍

- 객체의 상태(state)와 행동(behavior)은 각각 프로퍼티(property)와 메서드(method)로 구현 할 수 있다.
- 객체의 설계도는 class 이다.
- PHP에서 클래스를 가지고 객체를 생성 사용한다.

### 객체의 5가지 특징
- 추상화(abstraction)

- 캡슐화(encapsulation)

- 정보 은닉(data hiding)

- 상속성(inheritance)

- 다형성(polymorphism)

이게 무슨 말이나면

- class를 붕어빵 틀이라고 가정해보자.(이해를 돕기위한 예시일 뿐...)
- 붕어빵 틀을 설계한다.(class를 정의한다.)
```php 
    class fishTool{
        // 붕어빵이름
        $name 
        // 밀가루
        $flour   
        // 팥 
        $redBean
        function fire($name, $flour, $redBean){
            echo ($name."의 붕어빵이 완성 되었습니다."."밀가루 :".$flour."팥 :".$redBean)
        }
    }
```

- 생성된 틀을 이용해 객체를 만든다.
- 인스턴스 생성

```php
    // $객체명 =  new 클래스이름(인수1,인수1)
    $tool1 = new fishTool
```

- 이후 해당 프로퍼티 혹은 메서드에 접근할 수 있다.

- 설계한 틀에 $name, $flour, $redBean은 프로퍼티 
  
- 프로퍼티(property)
```php
    $tool1->name = "홍길동";
    $tool1->flour = 24;
    $tool1->redBean = 260;
```

- 설계한 틀에 fire()은 메서드
  
- 메서드(method)
```php
    $tool1->fire();
```

- 객체 내부에서 해당 인스턴스의 프로퍼티에 접근하려고 할 때 
- $this 변수를 사용
  
```php
    $this->fire();
```


