## 1. a = "Hello Python" 문자열을 Slicing과 연결 연산자 (+)를 사용하여 "Python Hello"로 변경하시오.
* [주의] a 변수 자체에 "Python Hello" 문자열이 저장되어야 함

a = "Hello Python"
a = a[6:] + " " + a[:5]
print(a)

Python Hello

변수 a는 문자열 "Hello Python"을 가리킨다. 문자열은 쉽게 수정하고 변경할 수 없기 때문에 슬라이싱을 사용한다. 예를 들어 a[first:end:step]으로 나뉘어 값을 입력할 수 있다. a = "123456" 일 때, a[0:6:2]라고 하면 0에서 6번째 자리 전까지 2증가로 확인할 수 있다.

## 2. b="Hello Python World" 문자열을 Slicing과 연결 연산자 (+)를 사용하여 "World Python Hello"로 변경하시오.
- [주의] b 변수 자체에 "World Python Hello" 문자열이 저장되어야 함

b = "Hello Python World"
b = b[-5:] + b[5:12] + " " + b[:5]
print(b)

World Python Hello

1번 문제와 마찬가지로 [first:end]와 같이 문자열의 인덱스를 알아야 한다. hello -> 0~4까지, python -> 6~11, world -> 13~end 로 어느 인덱스 위치에 위치하고 있는지를 알 수 있어야 해결할 수 있다.

## 3. c="Hello"를 "olleH"로 변경하시오
- [주의] c 변수 자체에 "olleH" 문자열이 저장되어야 함

c = "Hello"
c = c[::-1]
print(c)
c = ''.join(reversed("Hello"))
print(c)

olleH   
olleH

[first,end,step] 에서 step구간에 -1을 대입하게 되면 왼쪽으로 -1칸씩 이동하여 문자열을 확인하게 된다. 그러면 문자열을 거꾸러 읽어준다. join을 이용한 reversed로 문자열을 입력하면 입력 한 문자열을 거꾸로 읽어준다.
