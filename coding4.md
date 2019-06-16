# baemin_Wrong_answer_notes

### 코드 중 OK된 그룹수 의 확률을 구하라(반올림 해야함)
* * *
#### 아래 코드는 끝나자마자 짠거라 전달값(T, R) 선언하고 시작한 코드, 2차 수정 시 함수에 T, R 전달 받아 짜는거로 다듬기! 

    T = ['test1a', 'test2', 'test1b']     # Test 하는 그룹 리스트
    R = ['Ok', 'System Error', 'Ok']      # Test의 Result 값 리스트
    Group_numbering_ilst = []             # Group_numbering_list
    okG = []                              # OK_Group 리스트


    for i in range(1, len(T)+1):          # 길이만큼 최대그룹 수나올 수 있다는 가정하에 Group_numbering_ilst
        Group_numbering_ilst.append(str(i))
    
    
    for x in range(len(R)):               # Result 값이 Ok 인것을 리스트에 넣는다.
        if 'Ok' in R[x]:
            okG.append(T[x])
        else:
            okG.append('0')               # 함수에 값 전달해서 돌릴때 range 고정하기 위해 자리수 맞춤으로 Ok가 아닌것은 '0'으로 넣음

    def group(tr):   # 몇 Group인지 count하는 함수 생성
	      gsum = 0
	      for i in range(3):
            if Group_numbering_ilst[i] in tr[i]:  # 넘버링이 okG[i]문자열에 있으면 count 없으면 continue
                gsum += 1
            continue
        return gsum
	

    print(round(group(okG)*100/group(T)))

