# 3주차: 조건문과 반복문(if, for, while)

---

## 1. 조건문(if, elif, else)

- 프로그램이 특정 조건을 만족할 때만 어떤 코드를 실행하도록 함.

```python
# if 문 예제
age = int(input("나이를 입력하세요: "))

if age < 13:
    print("어린이")
elif age < 20:
    print("청소년")
else:
    print("성인")
```

> **input의 정체**: `input()`은 method가 아니고 내장 함수(function, 파이썬에 내장되어 있음)

---

## 2. 반복문(for, while)

### for문과 range()

```python
# for 문과 range()
for i in range(1, 6):
    print(i, end=" ")   # 1 2 3 4 5

# 리스트 반복
fruits = ["사과", "배", "포도"]
for fruit in fruits:
    print(fruit)

# while 문
num = 0
while num < 5:
    print(num)
    num += 1

# break & continue
for i in range(10):
    if i == 5:
        break        # 5에서 반복 중단
    if i % 2 == 0:
        continue     # 짝수는 건너뛰기
    print(i)
```

### 축약형 대입 연산자 (반복문에서 자주 사용)

| 축약형 | 의미 | 예시 |
|--------|------|------|
| `+=` | 더해서 저장 | `num += 1` |
| `-=` | 빼서 저장 | `num -= 1` |
| `*=` | 곱해서 저장 | `num *= 2` |
| `/=` | 나눠서 저장 | `num /= 2` |

---

## 3. 함수(function) vs 메서드(method)

| 구분 | 함수 (function) | 메서드 (method) |
|------|----------------|----------------|
| 정의 | 독립적으로 사용 | 객체에 종속되어 있음 |
| 예시 | `input()`, `print()` | `"hello".upper()`, `list.append()` |
| 차이 | 클래스 밖에 정의됨 | 클래스 안에 정의된 함수 |

```python
# 함수 (독립적)
age = input("나이 입력: ")

# 메서드 (문자열 객체에 붙음)
text = "hello"
print(text.upper())   # 'HELLO' ← 문자열 객체의 메서드
```

---

## 4. 파이썬 내장 함수(built-in functions)

| 함수 | 설명 | 예시 |
|------|------|------|
| `print()` | 콘솔에 출력 | `print("Hello")` |
| `input()` | 사용자 입력 받기 | `name = input("이름: ")` |
| `len()` | 길이 반환 | `len("hello")` → `5` |
| `type()` | 자료형 확인 | `type(3.14)` → `<class 'float'>` |
| `int()` | 정수형 변환 | `int("10")` → `10` |
| `float()` | 실수형 변환 | `float("3.14")` → `3.14` |
| `str()` | 문자열 변환 | `str(10)` → `"10"` |
| `bool()` | 불리언 변환 | `bool(0)` → `False` |
| `list()` | 리스트 변환 | `list("abc")` → `['a', 'b', 'c']` |
| `range()` | 숫자 범위 생성 | `range(5)` → `0,1,2,3,4` |
| `sum()` | 합계 구하기 | `sum([1, 2, 3])` → `6` |
| `min()` / `max()` | 최소 / 최대값 | `min([2,5,1])` → `1` |
| `abs()` | 절댓값 | `abs(-7)` → `7` |
| `round()` | 반올림 | `round(3.1415, 2)` → `3.14` |
| `sorted()` | 정렬된 리스트 반환 | `sorted([3,1,2])` → `[1,2,3]` |
| `enumerate()` | 인덱스 + 값 반복 | `for i, v in enumerate(...)` |
| `zip()` | 여러 리스트 묶기 | `zip([1,2], ['a','b'])` |
| `map()` | 함수 적용 | `map(str, [1, 2])` → `'1', '2'` |
| `filter()` | 조건 필터링 | `filter(lambda x: x>0, nums)` |
| `eval()` | 문자열 계산 | `eval("3 + 5")` → `8` |
| `help()` | 도움말 보기 | `help(print)` |

```python
print(type(10))        # <class 'int'>
print(type("hi"))      # <class 'str'>
print(type([1, 2, 3])) # <class 'list'>
```

---

## 5. while문 응용 예제

```python
# 사용자 입력이 "exit"일 때까지 계속 입력 받기
text = ""
while text != "exit":
    text = input("문장을 입력하세요 (종료하려면 exit): ")
    print("입력한 문장:", text)
```

---

## 6. 리스트 컴프리헨션(List Comprehension)

```python
# 일반 for문
squares = []
for i in range(5):
    squares.append(i * i)
print(squares)

# 리스트 컴프리헨션 (한 줄로 압축)
squares = [i * i for i in range(5)]
print(squares)
```

---

## 7. 클래스(Class) 기초

### 쿠키 비유로 이해하는 클래스

| 개념 | 쿠키 비유 | 의미 |
|------|-----------|------|
| **클래스** | 쿠키틀 (cookie cutter) | 쿠키 모양과 특징을 정의하는 설계도 |
| **객체** | 쿠키틀로 찍어낸 실제 쿠키 | 실제로 만들어진 것 |
| **인스턴스** | 특정 쿠키틀로 만든 쿠키 | 어떤 클래스에서 만들어진 객체 (정체 강조) |

```python
class Cookie:
    def __init__(self, shape):
        self.shape = shape

cookie1 = Cookie("별")
cookie2 = Cookie("하트")
```
