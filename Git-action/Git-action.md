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
- [참고URL](https://github.com/JangJaeWon22)

### 1. 작동 원리

Workflow ⇒ Job ⇒ Step ⇒ Action

점점 작은 단위로 이동함.

---

### 2. git action 코드 작성.

작업하고 있는 **Repositories**에 들어가서 action 탭으로 Workflows를 생성.

절대 폴더 이름을 바꾸면 안된다.

폴더 구조 : .github/workflows/node.js.yml

```jsx
name: SERVER distribute

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-18.04

    steps:
      - name: Deploy
        uses: appleboy/ssh-action@master
        with:
          host: ${{ secrets.STUDY_IP }}
          username: ${{ secrets.STUDY_SSH_ID }}
          key: ${{ secrets.STUDY_SSH_KEY }}
          port: ${{ secrets.STUDY_SSH_PORT }}
          script: |
            sudo -s
            cd /home/ubuntu/폴더명
            sudo git pull
            cd /home/ubuntu/폴더명
            npm i
            sudo pm2 reload all
```

`appleboy/ssh-action@master`는 ssh로 접속을 하고 스크립트를 실행하게 한다.

setting 값으로 github에서 STUDY_IP, STUDY_SSH_ID, STUDY_SSH_KEY, STUDY_SSH_PORT 가 있다.

---

### 3. Secrets 설정

**Repositories**의 Settings로 이동하여 Secrets탭을 선택 후 New repository secret 탭을 누르면 생성 가능함.

- STUDY_IP : ubuntu 주소
- STUDY_SSH_ID : ubuntu
- STUDY_SSH_PORT: 22
- STUDY_SSH_KEY : SSH KEY

  > - STUDY_IP 는 ec2 서버의 주소.
  > - STUDY_SSH_ID : ubuntu 다. FileZilla에서 연결할 때 계정 ID는 ubuntu로 연결 하던걸 생각하자.
  > - STUDY_SSH_PORT : 22 포트가 기본이다. 또 한번 FileZilla를 생각해 보자 포트가 22로 맞췄을 꺼다.
  > - STUDY_SSH_KEY:
  >   가장 중요하다. 5일 동안 삽질을.. 하고 알아 냈다.
  >   - ubuntu 서버에서 public 키를 발급 한다.
  >   - 그리고 기존 연결은 ubuntu keypair.pem으로 하던걸 기억하자.

```jsx
// ec2 서버에서 실행
// email은 github email을 사용했다.
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

// 생성 확인
cd ~/.ssh
ls
// 결과: authorized_keys  id_rsa  id_rsa.pub
// authorized_keys => .pem 키페어가 저장되어있다.
// 여기에서 중요!!!! id_rsa.pub가 public 키인데 직접 확인 해보자

cat id_rsa.pub

// 권한 설정
chmod 700 .ssh
chmod 600 authorized_keys

// 이제 public 키를 키페어에 추가 해주면 끝.
cat id_rsa.pub >> ~/.ssh/authorized_keys

// Secrets에 등록하기 위해 cat으로 조회하고 복 붙.
cat authorized_keys
```

- .git add commit push
  해보면 action이 자동적으로 서버 배포 후 pm2 reload 를 함.

---
