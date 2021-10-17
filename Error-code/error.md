# error-code

## VS code
* Error: Cannot find module 'C:\Users\JG\Desktop\js-study\functiong.js'
  *  터미널에서 명령어 오타

## git bash
* bash: cd: too many arguments: No such file or directory
  * 공백으로 인한 문제
  * cd "new folder" 또는 공백을 탈출 cd new\ folder

* warning: LF will be replaced by CRLF in src/views/layout.ejs.
The file will have its original line endings in your working directory 
  * [해결](https://blog.jaeyoon.io/2018/01/git-crlf.html)
  * git config --global core.autocrlf true
  * 현재 파일만 변경을 하려면 --global 제거해주기