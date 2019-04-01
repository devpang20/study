## 기본 출력 문제

### PHP 
```php
<?php
//PHP 출력할 때
echo 'hi';
?>
```
### JS
```js
// SCRIPT 출력할 때 
<script>
  document.write('hi');
</script>
```
---
## 문자열 합치기
### PHP
```php
<?php
//php 문자열 합칠때는 .
echo 'hi'.'PHP';
?>
```

### JS
```js
<!-- script 문자열 합칠때는 + -->
<script>
  document.write('hi'+'script');
</script>
```
---
## 변수와 문자열 합치기
### PHP
```php
<?php
//php 변수는     $변수명
$a = 'hi';
$num = 1;
echo $a . '<br>';
echo $num;
?>
```
### JS
```js
<!-- script 변수는  var 변수명 -->
<script>
  var a = "hi";
  var num = 1;
  document.write(a + '<br>');
  document.write(num + '<br>');
</script>
````