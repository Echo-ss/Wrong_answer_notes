# baemin_Wrong_answer_notes
#### 이미 지나간 일이고 AWS t2.micro 우분투에 postgresql 설치해서 풀었는데 발전하고 있는 내 자신이 정말 너무 뿌듯하다!
###### postgresql 설치 및 테이블 생성은 private에 올림.

### 종, 연못, 오리 테이블이 있다. 종에는 id 와 높거나 낮음을 체크하는 '+', '-'가 있고 종이 생존할 수 있는 한계값 컬럼이 존재. 연못은 연못 id와 온도, 연못 이름이 있다. 오리는 오리 id와 이름, 종 id와 연못 id가 존재한다. 연못 id당 생존한 해피덕을 구하라.
* * *
    SELECT D.pond_id, count(D.pond_id) happy_ducks
	    FROM ducks D, (SELECT P.id as pond_id, S.id as species_id
	                    FROM ponds P, specieds S
	                    WHERE CASE WHEN temp_preferences='+' THEN P.temperature >= temp_limit
	                              ELSE P.temperature <= temp_limit
	                              END) SP 
	      WHERE D.pond_id = SP.pond_id AND D.species_id = SP.species_id
	      GROUP BY D.pond_id;

### 출력값
    pond_id | happy_ducks 
    ---------+-------------
          1 |           1
          2 |           2
