## 1. a = "Hello Python" 문자열을 Slicing과 연결 연산자 (+)를 사용하여 "Python Hello"로 변경하시오.
* [주의] a 변수 자체에 "Python Hello" 문자열이 저장되어야 함

a = "Hello Python"
a = a[6:] + " " + a[:5]
print(a)
