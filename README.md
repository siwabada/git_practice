#git 참고글 

* [완전 초보를 위한 깃허브 by nolboo](https://nolboo.kim/blog/2013/10/06/github-for-beginner/)
* [깃(?)똥차게 좋은 GIT 기초 by slowalk](http://slowalk.tistory.com/2470)
* [GIT 강의 by 생활코딩](https://opentutorials.org/course/1492)

##주요 명령어

```
git config --global user.name "이름"
git config --global user.email "깃허브 메일주소" // 매번 물어보는 귀찮음을 피하기 위해 설정.

mkdir ~/MyProject   // 로컬 디렉토리 만들고
cd ~/myproject      // 디렉토리로 들어가서
git init            // 깃 명령어를 사용할 수 있는 디렉토리로 만든다.
git status          // 현재 상태를 훑어보고
git add 일명.확장자  // 깃 주목 리스트에 파일을 추가하고 
git rm 파일명.확장자   //깃 주목 리스트에 파일을 삭제한다 
git add .           // 이 명령은 현재 디렉토리의 모든 화일을 추가할 수 있다.
git commit -m “현재형으로 설명” // 커밋해서 스냅샷을 찍는다.

git remote add origin https://github.com/username/myproject.git // 로컬과 원격 저장소를 연결한다.
git remote -v // 연결상태를 확인한다.
git push origin master // 깃허브로 푸시한다.
git pull origin master // 깃허브에서 풀한다. 
git stash // origin 파일과 master 파일 충돌시 명령 (error: Your local changes to the following files would be overwritten by merge)
```
 
##마크다운 테스트 
```php
<?php
  require('config/config.php');
  require('lib/db.php');
  $conn = db_init($config['host'],$config['duser'],$config['dpw'],$config['dname']);
  // DB 서버($conn)에서 조회할 테이블 (topic)의 모든 정보를 가져온다. 결과값을 $result 변수에 저장
  $result = mysqli_query($conn, 'SELECT * FROM topic order by id desc');
 ?>

<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>몽키와선샤인</title>
  <link rel="icon" href="favicon.png">
  <link href="/bootstrap-3.3.4-dist/css/bootstrap.min.css" rel="stylesheet">
  <link rel="stylesheet" type="text/css" href="/style.css">
  <script type="text/javascript">
    function del_confirm(){
      var result = confirm('정말로 삭제 하시겠습니까?');
      if(result === true){
        alert('삭제완료')
        location.replace("/process.php?mode=delete&id=<?=$_GET['id']?>");
      }else{
        location.replace("/index.php?id=<?=$_GET['id']?>");
      }
    }
  </script>
</head>
<body>
  <div class="container col-md-8 col-lg-offset-2">
    <div class="header clearfix">
      <nav>
        <ul class="nav nav-pills pull-right">
          <li role="presentation" class="active"><a href="/write.php">글쓰기</a></li>
        </ul>
      </nav>
      <h3 class="text-muted"><a href="/index.php"><img src="/favicon.png" alt="로고" class="logo"><span class="title">몽키와 썬샤인의 영어공부</span></a></h3>
    </div>
    <hr class="header_line">
    <?php
      if(empty($_GET['id']) === true){
    ?>
      <div class="table-responsive">
        <table class="table table-striped text-center table-bordered">
          <tr class="active">
            <td width="5%">#</td>
            <td width="50%">제목</td>
            <td width="10%">작성자</td>
            <td width="15%">날짜</td>
          </tr>
          <?php
            $i = 1;
            while($row = mysqli_fetch_assoc($result)){
          ?>
            <tr>
              <td width="5%"><?= $i?></td>
              <td width="50%"><a href="/index.php?id=<?=$row['id']?>"><?=$row['title']?></a></td>
              <td width="10%"><?= $row['author']?></td>
              <td width="15%"><?= $row['created']?></td>
            </tr>
          <?php $i = $i + 1; }?>
        </table>
      </div>
    <?}?>
    <?php
      if(empty($_GET['id']) === false){
        $sql = 'SELECT id, title, description, author FROM topic WHERE id = "'.$_GET['id'].'"';
        $result = mysqli_query($conn, $sql);
        $row = mysqli_fetch_assoc($result);
      ?>
      <div class="panel panel-default">
        <div class="panel-heading"><strong><?=$row['title']?></strong><br>by <?=$row['author']?></div>
        <div class="panel-body">
          <?=nl2br($row['description'])?>
        </div>
      </div>
        <a href="/modify.php?id=<?=$row['id']?>" class="btn btn-warning">수정</a>
        <!-- <a href="/delete.php?id=<?=$row['id']?>" class="btn btn-danger">삭제</a> -->
        <a onclick="del_confirm()" class="btn btn-danger">삭제</a>

    <?}?>
    </div>
  </div>
<!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
<!-- Include all compiled plugins (below), or include individual files as needed -->
<script src="/bootstrap-3.3.4-dist/js/bootstrap.min.js"></script>
</body>
</html>


```
