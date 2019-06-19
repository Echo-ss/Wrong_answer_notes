# Alec, Bob의 카드놀이
#### 문제
   우리는 방금 해결 한 과제 중 하나에 대한 귀하의 의견을 듣고 싶습니다. " 똑같은 긴 순서 (A, B)의 카드 기호 (2-9, T = 10, J, Q, K, A) 난 A [I]가 B [I]보다 더 높은 카드를 나타낸다되도록 위치의 수를 카운트. "
   카드 기호 (2-9, T = 10, J, Q, K, A)의 동등하게 긴 두 시퀀스 (A, B)가 주어지면 A [i]가 B보다 높은 카드를 나타내는 위치 i의 수를 세십시오. 나는].



    def card(A, B):
	    alec = list(A)					# 인자값을 비교가능하게 A,B 매개변수를 리스트로 받기 선언
	    bob = list(B)
	    all_list = ['A','K','Q','J','T','9','8','7','6','5','4','3','2'] # 모든 카드의 서열 정하기 익덱스값이 0일수록 높다
	    acnt = 0						# 알렉스 이긴 cnt값 변수 선언
	    bcnt = 0						# 밥의 이긴 cnt값 변수 선언
	    ans = 0							# 결과값 변수 선언

	    for i in range(6):				# 각자의 덱은 6개이므로 
		    if alec[i] == bob[i]:		# 알렉스와 밥의 값이 같으면 continue
			    continue
		    if all_list.index(alec[i]) < all_list.index(bob[i]): # all_list의 인덱스 값으로 비교하여 작은 값 쪽으로 +1
			    acnt += 1
		    else:
			    bcnt += 1
	

	    if acnt > bcnt:					# 알렉스와 밥의 이긴 값을 비교해 큰 값을 결과로 return
		    ans += acnt
	    else:
		    ans += bcnt
		
	    return ans
	
    print(card('A384QJ','JT87K2'))
