<!-- 라이브러리만 -->
```php
<?php
// config.php 파일에 있는 $config 배열을 사용해서 데이터베이스에
// connect 한다.
function db_init($host, $duser, $dpw, $dname, $dport){
  $link = mysqli_connect($host, $duser, $dpw, $dname, $dport);
  return $link;
}
function getRows($sql) {
  // getRows() 함수를 이용해 $sql 매개변수를 입력 받는다.
	global $link;
  // global 전역 함수로서 $link 변수를 사용
	$rows = array();
  // $rows 배열 선언
	$result = mysqli_query($link, $sql);
  //mysqli_query() 함수를 이용해
  //$link  ->  DB 연결     $sql  ->  쿼리 입력
  //데이터베이스에 쿼리문자열을 전송
	if ( $result === true ) {
    // 결과가 true 면
		return null;
    // null 을 돌려준다.
	}

	while ( $row = mysqli_fetch_assoc($result) ) {
    // mysqli_fetch_assoc 함수는
    // mysqli_query 를 통해 얻은 리절트 셋(result set)에서 레코드를 1개씩 리턴해주는 함수
		$rows[] = $row;
    //$row 변수로 받은 값들을 $rows[]  배열에 넣어준다.
	}

	return $rows;
  // $rows 를 리턴해주므로 배열이 들어가있음
  // $row  ->   한줄     $rows  ->  여러줄
}

function getRow($sql) {
  // getRow() 함수로 $sql 변수를 입력 받으면
	list($row) = getRows($sql);
  // list() 함수 설명

  // $test = array('1', '2', '3');
  // $test 변수는 3개의 배열 1,2,3을 가짐
  // $test[0] = 1

  // list($a, $b, $c) = $test;
  // 마치 변수를 선언하듯이 사용(단, 앞에 list() 키워드가 필요)
  // list($a, $b, $c) = $test[0] $test[1] $test[2]

  // echo $a;  --> test[0] 인 1이 출력
  // echo $b;
  // echo $c;

  // getRows로 받아서 한줄인 $row 를 가져온다.
	return $row;
  // 한줄인 $row 를 리턴해준다.
}

function execute($sql) {
  // 조회하는 것과 실행하는 것을 구분하기 위해
	getRows($sql);
}

function getRowValue($sql) {
  // getRowsValue 특정 값을 가지고 올때
  // 게시글에서 제목만 가져올때 등등
   $row = getRow($sql);

   $value = null;

   foreach ( $row as $key => $val ) {
    //  foreach 배열의 반복문

    // $row as $key
    // $row를 $key로 쓰겠다.

    // $key => $val
    // $key[' '] 배열에서 (연관배열)
    // $val 이  $value  일때까지
    // null  빈값이면
    // break 로 루프 빠져나옴
      $value = $val;
      break;
   }
   return $value;
  //  $value 를 리턴시켜준다.
}
```