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

```
create table in mysql cheat sheet --> 치트시트
0	5	13:39:54	CREATE TABLE `testtabl`(
 `date_timestamp `TIMESTAMP NOT NULL,
 `date_datetime`DATETIME NOT NULL
 )
 ENGINE = InnoDB	Error Code: 1166. Incorrect column name 'date_timestamp '	0.000 sec
```
- column name에 빈칸이 있으면 안된다

### Query
- [공부 영상](https://www.youtube.com/watch?v=vgIc4ctNFbc&t=3092s)

- 댓글/후기 등 등롣된 시간
  - 방금 전, 몇 분 전, 한 시간 전 ... 시간 표현하기
```
SELECT 
CASE
    WHEN TIMESTAMPDIFF(MINUTE, '2019-07-20 20:00:00', NOW()) <= 0 THEN '방금 전'
    WHEN TIMESTAMPDIFF(MINUTE, '2019-07-20 20:00:00', NOW()) < 60 THEN CONCAT(TIMESTAMPDIFF(MINUTE, '2019-07-20 20:00:00', NOW()), '분 전')
    WHEN TIMESTAMPDIFF(HOUR, '2019-07-20 20:00:00', NOW()) < 24 THEN CONCAT(TIMESTAMPDIFF(HOUR, '2019-07-20 20:00:00', NOW()), '시간 전')
    WHEN TIMESTAMPDIFF(DAY, '2019-07-20 20:00:00', NOW()) < 30 THEN CONCAT(TIMESTAMPDIFF(DAY, '2019-07-20 20:00:00', NOW()), '일 전')
    ELSE CONCAT(TIMESTAMPDIFF(MONTH, '2019-07-20 20:00:00', NOW()), '달 전')
END AS AGOTIME
    FROM DUAL
```





### Query 주의사항

```
create table in mysql cheat sheet --> 치트시트
0	5	13:39:54	CREATE TABLE `testtabl`(
 `date_timestamp`TIMESTAMP NOT NULL,
 `date_datetime`DATETIME NOT NULL
 )
 ENGINE = InnoDB	Error Code: 1166. Incorrect column name 'date_timestamp '	0.000 sec
```
- column name에 빈칸이 있으면 안된다


