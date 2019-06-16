# baemin_Wrong_answer_notes
#### 긴장해버렸지만 이미 지나간 일이고 AWS t2.micro 우분투에 postgresql 설치해서 풀었는데 발전하고 있는 내 자신이 정말 너무 뿌듯하다!
###### postgresql 설치 및 테이블 생성은 private에 올림.
### 코딩테스트_오답노트

    SELECT D.pond_id, count(D.pond_id) happy_ducks
	    FROM ducks D, (SELECT P.id as pond_id, S.id as species_id
	                    FROM ponds P, specieds S
	                    WHERE CASE WHEN temp_preferences='+' THEN P.temperature >= temp_limit
	                              ELSE P.temperature <= temp_limit
	                              END= 't') SP 
	      WHERE D.pond_id = SP.pond_id AND D.species_id = SP.species_id
	      GROUP BY D.pond_id;

### 출력값
    pond_id | happy_ducks 
    ---------+-------------
          1 |           1
          2 |           2
