# 상위 n개 레코드
## mysql
```mysql
SELECT NAME
FROM ANIMAL_INS
ORDER BY DATETIME
LIMIT 1
```
___
SELECT를 이용하여 조회하고자 하는 컬럼명 입력

FROM을 이용하여 조회하는데 이용하는 테이블 이름 입력

ORDER BY를 이용하여 정렬 오름차순은 ASC를 입력하지만 생략 가능

상위 1개를 만들고 싶을 때 LIMIT 1을 씀 (MYSQL 일때만!)

만일 상위 N개라면 LIMIT N을 씀

ORACLE에서 상위 N개를 입력하고자 할 때는 ROWNUM을 사용한다는 점