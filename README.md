# Homework-1

1. a = "Hello Python" 문자열을 Slicing과 연결 연산자 (+)를 사용하여 "Python Hello"로 변경하시오.
[주의] a 변수 자체에 "Python Hello" 문자열이 저장되어야 함
a = "Hello Python"
a = a[6:] + " " + a[:5]
print(a)
Python Hello
nohtyP olleH
변수 a는 문자열 "Hello Python"을 가리킨다. 문자열은 쉽게 수정하고 변경할 수 없기 때문에 슬라이싱을 사용한다. 예를 들어 a[first:end:step]으로 나뉘어 값을 입력할 수 있다. a = "123456" 일 때, a[0:6:2]라고 하면 0에서 6번째 자리 전까지 2증가로 확인할 수 있다.

2. b="Hello Python World" 문자열을 Slicing과 연결 연산자 (+)를 사용하여 "World Python Hello"로 변경하시오.
[주의] b 변수 자체에 "World Python Hello" 문자열이 저장되어야 함
b = "Hello Python World"
b = b[-5:] + b[5:12] + " " + b[:5]
print(b)
World Python Hello
1번 문제와 마찬가지로 [first:end]와 같이 문자열의 인덱스를 알아야 한다. hello -> 04까지, python -> 611, world -> 13~end 로 어느 인덱스 위치에 위치하고 있는지를 알 수 있어야 해결할 수 있다.

3. c="Hello"를 "olleH"로 변경하시오
[주의] c 변수 자체에 "olleH" 문자열이 저장되어야 함
c = "Hello"
c = c[::-1]
print(c)
c = ''.join(reversed("Hello"))
print(c)
olleH
olleH
[first,end,step] 에서 step구간에 -1을 대입하게 되면 왼쪽으로 -1칸씩 이동하여 문자열을 확인하게 된다. 그러면 문자열을 거꾸러 읽어준다. join을 이용한 reversed로 문자열을 입력하면 입력 한 문자열을 거꾸로 읽어준다.

4. s="python"에 대해 다음 문제를 풀어보시오.
s[0], s[0][0], s[0][0][0]은 각각 어떤 값이 나오는지 확인하고 그 이유를 나름대로 설명해 보시오.
s[-100], s[100]은 값이 나오는지 에러가 나오는지 확인하고 그 결과에 대한 이유를 나름대로 설명해 보시오.
s[-100, 100]은 값이 나오는지 에러가 나오는지 확인하고 그 결과에 대한 이유를 나름대로 설명해 보시오.
s[1:-1]의 결과를 확인하고 그 결과에 대한 이유를 정확하게 설명하시오.
s[3:-3]의 결과를 확인하고 그 결과에 대한 이유를 정확하게 설명하시오.
# 4-1
s = "python"
print(s[0])
print(s[0][0]) # print(s[1][0]) => y
print(s[0][0][0]) # print(s[2][0][0]) => t
p
y
t
파이썬에서 문자열은 s[index]로 저장이된다. 하지만 s[a][b][c].. 이 있을 때 a,b,c 의 값이 모두 0이 된다면, 문자열 자릿 수 0번째 자리의 수를 반환한다. 하지만 여기서 a를 제외한 나머지 인덱스에 0이외에 숫자가 들어가게 된다면 오류가 나게 된다.

# 4-2
print(s[-100])
print(s[100])
---------------------------------------------------------------------------
IndexError                                Traceback (most recent call last)
<ipython-input-4-118dbc0ce86e> in <module>
      1 # 4-2
----> 2 print(s[-100])
      3 print(s[100])

IndexError: string index out of range

s[-100], s[100]은 에러 값이 나온다. s는 "python"이다. s[0]~s[5] (p,y,t,h,o,n)으로 이루어져있다. 그렇기 때문에 범위를 벗어나는 인덱스는 반환하지 않는다.

# 4-3
print(s[-100,100])
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-5-f8798f227a18> in <module>
      1 # 4-3
----> 2 print(s[-100,100])

TypeError: string indices must be integers

s[-100,100]의 값은 오류이다. 슬라이싱으로 s[-100:100]으로 했으면 모든 s의 python을 호출하겠지만, 2차원 배열처럼 s[first,second]와 같은 형식은 파이썬에서 반환해주지 않는다.

# 4-4 
print(s[1:-1])
ytho
s = python, s[1:-1]의 결과로는 s[1] = y, s[-1] = n이기 때문에 s[-1] 전 값인 s[-2] = o의 값까지 출력하여 "ytho"가 나옴을 알 수 있다.

# 4-5
print(s[3:-3])

s = python, s[3] = h, s[-3] = h이다. 3에서 -3전까지면, 3에서 -4까지여야 한다. 그러면 순서상 올바르지 않기 때문에 아무것도 출력하지 않는다. p, y, h, o, n 의 방향으로 진행되어야 하는데, s[3] = h, s[-4] = t 이다. 그렇기 때문에 올바르지 않다.

5. for문을 활용하여 1부터 100사이의 홀수를 출력하시오.
for i in range(1,101):
    if i % 2 == 1:
        print(i, end =" ")
1 3 5 7 9 11 13 15 17 19 21 23 25 27 29 31 33 35 37 39 41 43 45 47 49 51 53 55 57 59 61 63 65 67 69 71 73 75 77 79 81 83 85 87 89 91 93 95 97 99 
for 반복문을 사용했다. 여기서 range를 이용하여 1~100 까지 홀수를 출력하기 위한 반복문이고, i가 2를 나누었을 때, 1의 나머지를 가지게 되면 홀수이기 때문에 출력한다.

6. while문을 활용하여 1부터 100사이의 짝수의 합을 계산하여 출력하시오.
sum = 0
i=1
​
while i <=100 :
    if i % 2 == 0:
        sum += i
    i+=1
​
print(sum)
2550
while 반복문을 사용하여 1~100까지 짝수의 합을 계산하였다. i가 2로 나누었을 때, 나머지가 0이면 sum이라는 합의 i를 계속 더한다. 그리고 100번까지 모두 돌기 위해서 i의 값에 1을 계속더해준다. 그리고 모든 짝수의 합이 완료되면 sum을 출력한다.

7. 사용자로 부터 임의의 정수를 입력받고, 해당 숫자를 역순으로 출력하는 프로그램을 작성하시오.
[실행 예]
정수를 입력하세요: 3125
숫자 역순은 5213 입니다.

a = int(input("정수를 입력하세요 : "))
​
a1 = a%1000
b1 = a/1000
a2 = a1%100
b2 = a1/100
a3 = a2%10
b3 = a2/10
a4 = a3/1
​
print("숫자 역순은 %d%d%d%d 입니다." %(a4,b3,b2,b1))
정수를 입력하세요 : 3125
숫자 역순은 5213 입니다.
a를 내장함수 input을 사용하여 변수를 받을 때, 반환형을 int로 바꾸어준다. 왜냐하면 그냥 하게되면, string으로 반환되기 때문이다. 입력한 a의 값에 1000을 나눈 나머지를 100으로 나누고, 그 나머지를 10으로 나누고, 또 그 나머지를 1로 나누면 각 몫들이 값이된다. 그렇기 때문에 각 몫들을 출력해주면된다.

8. 사용자로 부터 정수를 입력받아서 1부터 그 사이에 존재하는 소수 (Prime number)를 출력하는 파이썬 프로그램을 작성하시오.
user = int(input("정수를 입력하시오 : "))
count = 0

for i in range(1,user):
    for j in range(1,user):
        if i%j == 0:
            count += 1
    if(count == 2):
        print(i, end=" ")
    count = 0
user = int(input("정수를 입력하시오 : "))
count = 0
​
for i in range(1,user):
    for j in range(1,user):
        if i%j == 0:
            count += 1
    if(count == 2):
        print(i, end=" ")
    count = 0
정수를 입력하시오 : 30
2 3 5 7 11 13 17 19 23 29 
user라는 변수에 input내장함수를 통하여 입력받고 int형으로 반환한다. for 반복문을 사용하는데, 여기서 for 반복문을 for반복문 안에 넣으며 중첩 반복문을 사용하였다. i가 1 ~ user(입력한 수)만큼 반복하고, 중첩 for 문은 j가 1~user(입력한 수)만큼 반복하게 된다. 그리고 중첩 반복문에 if 조건문으로 i%j 의 값이 0이면 count라는 변수에 1을 계속 더한다. 그리고 for문을 나와 if 조건문으로 count == 2이면 i를 출력하게 된다. 그리고 count를 0으로 초기화한다. 그렇게 되면 출력되는 i는 자기자신과 하나의 숫자만을 갖는 소수가 출력되게 된다.

9. Kevin과 Stuart는 게임을 한다. 규칙은 아래와 같다.
두 플레이어에게 같은 string, S, 가 주어진다.
두 플레이어는 string S의 문자를 사용하여 substring을 만들어야 한다(중복 가능).
Stuart는 자음으로 시작하는 단어를 만들어야 한다.
Kevin은 모음으로 시작하는 단어를 만들어야 한다.
게임은 두 플레이어가 만들 수 있는 모든 단어를 만들었을 때 끝난다.
점수 계산 : substring 1개당 +1 점을 획득한다. (아래 그림 참고)
사용자로 부터 대문자로 이루어진 string S를 입력받고, 승자와 그의 점수를 출력하는 프로그램을 작성하시오.
[실행 예]
string S를 입력하세요: BANANA
승자: Stuart 점수: 12
score = 0
s = string(input("string S를 입력하세요 : "))
​
if s[0] == ['A','E','I','O','U']:
    if(s == "A"): score = 3
    if(s == s[0]+"N"): score += 2
    if(s == s[0:]+"A"): score += 
    if(s == s[0:]+)
    if(s == "ANANA")
    print("승자 : Kevin")
    print("점수 : %d" %)
else :
    print("승자 : Stuart")
    print("점수 : %d" %)
​
​
10. 알파벳 소문자만으로 이루어진 string, S, 가 주어지고 아래 2가지 연산을 수행할 수 있다.
추가 : string S의 끝에 알파벳 소문자 하나를 추가한다.

삭제 : string S의 마지막 문자 하나를 삭제한다. empty string에서 삭제 연산을 수행한 결과는 empty string이다.
두 개의 string, s와 t, 그리고 정수 k가 주어질 때, 정확히 k번의 연산을 통해 s를 t로 바꿀 수 있는지 판단하는 함수를 작성하시오
[예시]

s = 'hackerhappy' t = 'hackerrank' k = 9 => 'Yes'

s = 'aba' t = 'aba' k = 7 => 'Yes'

s = 'ashley' t = 'ash' k = 2 => 'No'

def appendDelete(s, t, k):
    count = 0
    for i in k:
        if s != k:
            s.remove(len(s)-1)
            t.remove(len(t)-1)
            if s == k:
                
        s.remove(len(s-1))
        count += 1
    
    print("s = %s\t t = %s\t k = %d\t => " %(s,t,k))
    
    return 'Yes'    # or 'No'

appendDelete("aba","aba",7)
def appendDelete(s, t, k):
    count = 0
    for i in k:
        if s != k:
            s.remove(len(s)-1)
            t.remove(len(t)-1)
            if s == k:
                
        s.remove(len(s-1))
        count += 1
    
    print("s = %s\t t = %s\t k = %d\t => " %(s,t,k))
    
    return 'Yes'    # or 'No'
​
appendDelete("aba","aba",7)
