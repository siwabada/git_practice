

##문제
* 게시판에 글 작성시 제목을 입력하지 않고 저장하면 해당 글을 다시 선택할 수 없는 문제가 발생했다.
* 글 작성 화면에서 제목을 공란으로 두고 저장하지 못하도록 하려고 한다. 

##고민
* sql table 생성시에 title 컬럼을 필수 입력으로 설정하면 되지 않을까?
	* title column에 제약조건(constrain) NOT NULL을 설정 (참고 : SQL DB의 제약조건이란?)
	* NOT NULL 로 title컬럼의 constraint를 수정했지만 아무것도 입력하지 않아도 저장이 되어버림 - 왜 그럴까?
* title의 input 요소를 필수 입력으로 설정
	* input 요소의 attribute 중에 required 가 있음

##해결
* input에 required를 추가

##코드

```html
<form action="demo_form.asp">
  Username: <input type="text" name="usrname" required>
  <input type="submit">
</form>

```

##참고링크
* http://www.w3schools.com/TAgs/att_input_required.asp
 
##여담
* 왜 제약조건 NOT NULL을 설정해도 필수입력 처리가 되지 않았을까? 

 

```php
<?php
	echo 'hello world';
?>

```

```html
<html>
	<head>
	</head>
	<body>
		<a href='daum.net'>뭐라구</a>
	</body>
</html>

```
