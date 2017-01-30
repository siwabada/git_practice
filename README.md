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
 

