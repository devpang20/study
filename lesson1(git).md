# Git

[개요는 위키에서](https://namu.wiki/w/Git) 

 - Git은 버전 관리 시스템
   - 협업을 위한 필수 도구
   - 주로 원격 저장소(github, gitlab, 비트버킷과 같은 거대 저장소 서비스 페이지)에서 로컬 저장소(내 pc)로 push(보내기) 하거나 pull(내려받기) 한다.

- 장점
    - 협업시 잘못 되었을 때 입력한 코드를 유지보수 하기 용이하다.
    -  개발 로직을 추적하기가 쉽다. 
    -  협업 시에는 필수 !!!
    -  
- 저장소 생성
  - 원격 저장소를 만든다. [github](https://github.com/)로 접속 후 가입을 한다.
  - 참고사이트
    - [생활코딩](https://opentutorials.org/course/2708/15395)
    - [블로그](https://coderkoo.tistory.com/2)


## 원격저장소 -> 로컬저장소 git clone 버전
- git clone 
    - 원격 저장소에서 로컬 저장소로 받아온다. 주로 로컬에 아무것도 없고 원격에서 작성 중이던 코드를 받아오는 초기에 쓴다.
    - init 또한 자동으로된다.
```git
실습은 CLI 환경인 Git Bash에서 진행
$ git clone [url] "디렉토리명"
``` 
- git add
  - 수정한 내용이 있을 경우 커밋한 파일을 선택한다. 
```git
$ git add "파일명"

모든 수정 파일을 담는다.(*은 전체를 의미 )
$ git add *

특정 파일만 담는다.
$ git readme.md 
``` 

- git commit 
```git
$ git commit -m "메세지 작성"
$ git commit -m "my first commit!"
```

-git status
```git
$git status를 입력시 커밋 상태 볼 수 있음
```

- git push

```git
git push를 통해 원격 저장소로 보내기 
$ git push
```

- git log
```git
git log를 통해 기록을 확인할 수 있음
$ git log 
$ git log --reverse
```

---