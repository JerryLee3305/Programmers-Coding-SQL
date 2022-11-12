# 이름에 el이 들어가는 동물 찾기
## mysql
### 문제
>문제 설명

ANIMAL_INS 테이블은 동물 보호소에 들어온 동물의 정보를 담은 테이블입니다. ANIMAL_INS 테이블 구조는 다음과 같으며, ANIMAL_ID, ANIMAL_TYPE, DATETIME, INTAKE_CONDITION, NAME, SEX_UPON_INTAKE는 각각 동물의 아이디, 생물 종, 보호 시작일, 보호 시작 시 상태, 이름, 성별 및 중성화 여부를 나타냅니다.

![image](https://user-images.githubusercontent.com/108413432/201459133-7157ca1b-10a5-407f-8a2a-bc05ca1d5dd6.png)

보호소에 돌아가신 할머니가 기르던 개를 찾는 사람이 찾아왔습니다. 이 사람이 말하길 할머니가 기르던 개는 이름에 'el'이 들어간다고 합니다. 동물 보호소에 들어온 동물 이름 중, 이름에 "EL"이 들어가는 개의 아이디와 이름을 조회하는 SQL문을 작성해주세요. 이때 결과는 이름 순으로 조회해주세요. 단, 이름의 대소문자는 구분하지 않습니다.

>예시

예를 들어 ANIMAL_INS 테이블이 다음과 같다면

![image](https://user-images.githubusercontent.com/108413432/201459138-bbf2dd3f-e23b-493b-b8dd-1a10b4c5088d.png)

이름에 'el'이 들어가는 동물은 Elijah, Ella, Maxwell 2입니다.

이 중, 개는 Elijah, Maxwell 2입니다.

따라서 SQL문을 실행하면 다음과 같이 나와야 합니다.

|ANIMAL_ID	|NAME
|----------|-------
|A355753	|Elijah
|A382192	|Maxwell 2

### 좀 틀렸지만 해결!
SELECT animal_id, name 
from animal_ins
where (name like '%el%') and (animal_type = 'Dog')
order by name

1. 결과 테이블에서 보여줘야할 컬럼은 animal_id와 name 이다. (select)
2. 가져올 테이블 명은 animal_ins (from)
3. el 이라는 글자가 포함되어 있어야한다. 이것은 like를 써서 해결한다.
4. like 뒤에 %el% 사용하면 앞 뒤 어디에 있든 존재하는 el이 나오게 된다
5. 또다른 조건문이 있으므로 and로 묶어준다.
6. 'Dog' 타입만 나타나게 해준다. (=)
7. 문제 마지막 줄에 이름 순으로 조회해 달라고 써있으니 order by name을 사용해서 정렬 (이것 때문에 계속 틀렸음)

- 문제를 끝까지 잘 읽기!!!
