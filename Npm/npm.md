# Npm
### LIST

* [express](https://www.npmjs.com/package/express)

    * http 웹사이트 제작 도움

* morgan : 터미널 창에 로그가 보이게 할수있음-req 요청 로깅 미들웨어 (설정은 dev)
    * 윈스턴과 함께 설치 아래에 코드 확인 

* [winston](https://www.npmjs.com/package/winston)
    * 로그 파일 및 로그 레벨 관리 모듈
    * npm install --save winston winston-daily-rotate-file morgan
    * winston-daily-rotate-file : 매일 날짜 별로 로그 파일 생성 및 관리 모듈,자동삭제 및 관리
    * [참고사이트1](https://for-development.tistory.com/51)
    * [참고사이트2](https://logtail.com/tutorials/how-to-install-setup-and-use-winston-and-morgan-to-log-node-js-applications/)
    * 추가로 시간을 Asia/Seoul로 맞추기 위해서는 **npm i moment moment-timezone**
    * lever 단계는 error, warn , info , verbose , debug ,combine
        * 대개 **info** 형식까지 사용 (info 사용시 debug, combine 찍히지 않음) 
    * format 로그형식은 json, label, timestamp, printf, simple, combine, etc...
        * 대개 **json** 형식을 사용 (단, 시간을 표현하려면 timestamp)
    * transports 로그 저장방식

* [swagger]()

* [jest]()

* [passport]()

* [passport-jwt]()

* [passport-kakao]()

