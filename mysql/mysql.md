# Mysql

### 준비물 : mysql, workbench , VS code

[참고 자료]()

- 작성하기
  - [Sequelize 사용법](https://sskey.tistory.com/69) / [Query문 사용법](https://365kim.tistory.com/102) 둘다 활용하기
- 문자열 인코딩하기!

  - [escape , sql injection](https://devkingdom.tistory.com/90)

### mysql 시작 및 주의사항
[mysql 정리사이트-생활코딩](https://nittaku.tistory.com/375?category=764930)
[외부접속 허용](https://abc1211.tistory.com/537)

- create table in mysql cheat sheet --> 치트시트
0	5	13:39:54	CREATE TABLE `testtabl`(
 `date_timestamp `TIMESTAMP NOT NULL,
 `date_datetime`DATETIME NOT NULL
 )
 ENGINE = InnoDB	Error Code: 1166. Incorrect column name 'date_timestamp '	0.000 sec

- column name에 빈칸이 있으면 안된다
