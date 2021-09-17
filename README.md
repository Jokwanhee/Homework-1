## 1. a = "Hello Python" 문자열을 Slicing과 연결 연산자 (+)를 사용하여 "Python Hello"로 변경하시오.
* [주의] a 변수 자체에 "Python Hello" 문자열이 저장되어야 함

a = "Hello Python"
a = a[6:] + " " + a[:5]
print(a)

Python Hello   
nohtyP olleH

변수 a는 문자열 "Hello Python"을 가리킨다. 문자열은 쉽게 수정하고 변경할 수 없기 때문에 슬라이싱을 사용한다. 예를 들어 a[first:end:step]으로 나뉘어 값을 입력할 수 있다. a = "123456" 일 때, a[0:6:2]라고 하면 0에서 6번째 자리 전까지 2증가로 확인할 수 있다.
