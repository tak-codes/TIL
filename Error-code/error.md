# error-code

## VS code
* Error: Cannot find module 'C:\Users\JG\Desktop\js-study\functiong.js'
  *  터미널에서 명령어 오타

## GIT
* bash: cd: too many arguments: No such file or directory

  * 공백으로 인한 문제
  * cd "new folder" 또는 공백을 탈출 cd new\ folder

* warning: LF will be replaced by CRLF in src/views/layout.ejs.

  * The file will have its original line endings in your working directory 
  * [해결](https://blog.jaeyoon.io/2018/01/git-crlf.html)
  * git config --global core.autocrlf true
  * 현재 파일만 변경을 하려면 --global 제거해주기
* The file will have its original line endings in your working directory

  * 깃 띄워쓰기 문제
  * git config --global core.autocrlf true
* Updates were rejected because the tip of your current branch is behind its remote

  * 깃 push에서 발생한 문제- 로컬과 버전이 맞지 않아서 생기는 오류
  * 푸시하고 싶은 브렌치에서 pull을 하여 버전을 맞춰준 다음 다시 push
  * 로컬 파일 상관 없으면  git push -u origin +branch 
