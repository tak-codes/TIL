# error-code

## VS code
* Error: Cannot find module 'C:\Users\JG\Desktop\js-study\functiong.js'
  *  터미널에서 명령어 오타

* undefined 관련 에러
```
(node:3132) UnhandledPromiseRejectionWarning: TypeError: Cannot read property 'userEmail' of undefined
    at C:\dev\workspace\walkingdog\routes\user.js:23:33
    at processTicksAndRejections (internal/process/task_queues.js:95:5)
(Use `node --trace-warnings ...` to show where the warning was created)
(node:3132) UnhandledPromiseRejectionWarning: Unhandled promise rejection. This error originated either by throwing inside of an async function without a catch block, or by rejecting a promise which was not handled with .catch(). To terminate the node process on unhandled promise rejection, use the CLI flag `--unhandled-rejections=strict` (see https://nodejs.org/api/cli.html#cli_unhandled_rejections_mode). (rejection id: 1)
(node:3132) [DEP0018] DeprecationWarning: Unhandled promise rejections are deprecated. In the future, promise rejections that are not handled will terminate the Node.js process with a non-zero exit code.
```
- 변수 지정 및 위치에 따라 해쉬된 변수 확인이 불가능해짐. (팬딩에 걸림)

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
