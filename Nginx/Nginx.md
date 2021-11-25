# Nginx
- [참고 자료](https://harrydony.tistory.com/665?category=897900)

### 사용하는 이유
- CORS 오류를 해결하기 위해서!

1. [설치하기](http://nginx.org/en/download.html)
- 위의 사이트에서 stable version nginx/windows 버번 다운하기
- 압축풀고 난후 nginx.exe 실행!
- http://localhost/ 들어가서 nginx 켜졌는지 확인하기

2. cmd 를 통한 끄고 켜기!
- 위에서 실행이 되어 있다면 끄는 방법은 cmd에서!
    - cmd 실행 -> cd nginx.exe 가 있는 폴더경로  ex) cd  C:\Users\JG\Downloads\nginx-1.20.2

    > nginx.exe -s stop
    - 좀더 직관적인 방법은 작업 관리자를 켜서 nginx.exe 작업 끝내기 하기!
- nginx 실행

- nginx가 설치된 폴더로 이동하여 nginx.exe 실행
- cmd창에서 nginx가 설치된 폴더로 이동하여 아래 커맨드 실행
> nginx

- nginx 실행 확인

- cmd창에서 호출하여 아래 커맨드 실행
> tasklist /fi "imagename eq nginx.exe"

- nginx 종료

- cmd창에서 nginx가 설치된 폴더로 이동하여 아래 커맨드 실행
>nginx -s stop ( 빠른 종료 )
nginx -s quit ( 일반 종료 )
nginx -s reload ( 재기동 )
nginx -s reopen ( 로그파일 다시쓰기 시작 )


3. conf 파일에서 nginx root 변경하기
- nginx.conf 파일 열기
```
location / {
    root  C:/
    index index.html 
}
```
- 위와 같은 화면이 뜰때 listen 80 , root 안의 경로를 pc 파일 경로로 변경을 하면 localhost로 접속하여 pc에 저장되어 있는 파일을 열수 있다.

