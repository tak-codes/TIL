# Git-action

### 기본개념
[참고자료](https://jsqna.com/ci-1-github-actions-nodejs/)
1. CI
- Continuous Integration. 각자의 코드를 병합하기 전에 검토하는 절차를 말한다.

2. GitHub Actions
- GitHub에서 특정 작업을 할 때 마다, 이벤트를 발생시키는데, 이를 구독해 특정 작업을 실행하는 것을 Github Actions라고 한다.

3. Worflow File
- GitHub Actions의 이벤트에 대해 무엇을 실행할 지에 대해 기록해 놓은 명령서를 workflow 파일이라고 한다.

4. Github Actions 사용 시의 CI 흐름
- PR Created(EVENT!) > Build > Test > PR Merged(EVENT!) > Deploy (배포 자동화는 다음에)
 CI 과정에서 빌드가 성공했을 때만 Merge가 가능하게 설정하자.

- **PR을 생성할 때 CI 수행**
- **Merge할 때 CD 수행**

### Node.js 자동 배포 
- [CI/CD 공부영상](https://www.youtube.com/watch?v=6-RtA6FlbgQ)
- 
