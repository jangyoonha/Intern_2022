


list_N = []   #입력값 넣을 리스트
while True:
    input_N = input()
    if (input_N == '0 0'):
        break
    input_N_D = tuple(map(int, input_N.split())) #두 수를 공백 기준으로 나누어 튜플로 저장
    list_N.append(input_N_D)


def Primary_A(Number_1, Number_2):
    Carry_N = 0
    a = 0
    quotient_1 = Number_1
    quotient_2 = Number_2
    while(quotient_1 != 0 and quotient_2 != 0): #0이 될 때 빠져나옴
        if(((quotient_1 % 10) + (quotient_2 % 10) + a ) >= 10 ): #10으로 나눈 나머지로 일의자리를 구해서 더함, 10 이상이면 올림 발생
            a = 1                   #올림 발생한 경우, 1이 다음 반복문에서 더해져야 함
            Carry_N = Carry_N + 1  #올림 발생 수 카운트
        else:
            a = 0
        quotient_1 = int(quotient_1 // 10)    #10으로 나누었을 때의 몫을 넣은 뒤 while문 반복
        quotient_2 = int(quotient_2 // 10)    
       
    return Carry_N


for x in list_N:       #리스트의 요소(=튜플) 하나씩 꺼내 반복
    Number_1 = x[0]    #튜플의 첫번째 요소 대입
    Number_2 = x[1]    #튜플의 두번째 요소 대입
    Carry_N = Primary_A(Number_1, Number_2)
    if (Carry_N == 0):
        print("No carry operation")
    else:
        print (str(Carry_N) + " carry operation")
        
      

No carry operation
2 carry operation
2 carry operation
