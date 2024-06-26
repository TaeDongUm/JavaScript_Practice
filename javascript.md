- 자바스크립트는 브라우저를 설치해야 실행할 수 있다.
    
    → 브라우저가 자바스크립트나 html을 읽고 화면을 그려준다.
    
- Node.js를 설치하면 브라우저없이 자바스크립트를 실행할 수 있다.

- 브라우저 상에서 코드를 실행할 수 있다.
- 자바스크립트 코드를 콘솔에 입력 후 [Enter]를 누르면 결과가 바로 나오는데, 이처럼 코드를 한 덩어리씩 실행해 결과를 출력하는 방식을 인터프리터(Interpreter) 방식이라고 한다.
- 한 덩어리라고 표현한 이유는 [Shift + Enter] 키를 누르면 줄바꿈을 해 여러 줄의 코드를 동시에 입력할 수 있기 때문

### 세미콜론

```jsx
console.log('Hello, world!');
// ; 붙이면 에러가 안남. 안붙이면 에러가 발생할 수도 있음. 차라리 붙이고 말겠다.
```

### 주석

```jsx
// 붙이기

주석 길이기 길다면
/*

*/

코드와 코드 사이에도 넣을 수 있음
const hello = ('코드사이에 주석 넣기'/*
이렇게 넣을수 있음
*/);
```

### 작은따옴표, 큰따옴표, 백틱(’ ” `)

```jsx
문자열을 만들기위해서 붙이는 것

'abcd'
"abcd"
`abcd`
```

### 줄바꿈

```jsx
'안녕하세요/n반갑습니다.'

--> 출력은
안녕하세요
반갑습니다.
```

### typeof

```jsx
typeof '문자열'

결과
--> "string"

typeof ''
--> "string"
```

### ==

```jsx
'' == '  '
false

''==''
true

' ' == ' '
true
```

### 따옴표 문자열에 넣기

```jsx
작은따옴표를 감싸주고 싶다면 큰따옴표로, 백틱으로
"'"
`'`

큰따옴표를 감싸주고 싶다면 작은따옴표로, 또는 백틱으로
'"'
`"`

문장안에서 따옴표를 짚어넣고 싶다면? 다른 따옴표로 감싸주기
'"정말" 그랬니?'

역슬래쉬로 감싸주기(같은 따옴표로 감싸고 싶다면)
'\'정말\' 그랬니?'
```

### 문자열 합치기

```jsx

'바나나'+'사과'
-> '바나나사과'

'바나나' - '사과'
-> NaN
'바나나' * '사과'
-> NaN
'바나나' / '사과'
-> NaN

```

### 숫자 기본(parseInt, NaN)

- 숫자는 따옴표로 감싸지 않고 그대로 적으면 된다.
- 음수는 앞에 -를 붙인다.
- 지수표기법도 사용가능

```jsx
1+1
-> 2

-5

5000

5e4
->50000

5e-4
0.0005

8진법
0o 또는 0(숫자)

16진법
0x
```

### NaN(Not a Number)

```jsx
typeof NaN
"number"

'바나나' - '사과'
NaN

? 숫자가 아닌데 숫자다. (직관적으로 이해하기 어려움.)

```

### parseInt, Number

```jsx
'1234' + 5
-> '12345'

parseInt('1234') + 5 // parseInt 정수로 바꾸다. 소수점 자른다.
-> 1239

Number('1234') + 5
-> 1239

parseInt('3.14')
-> 3

Number('3.14')
-> 3.14

parseFloat('3.14')
-> 3.14

// 그럼 숫자를 알아서 정수, 실수로 바꿔주는 Nubmer가 더 좋은 함수 아니냐?
// No
// 사용법이 다름

console.log(parseInt('123abc')); // 123 (숫자로 시작하기 때문에 숫자 부분만 파싱)
console.log(parseInt('abc123')); // NaN (문자가 숫자로 시작하지 않음)
console.log(parseInt('  456 ')); // 456 (공백을 무시하고 숫자를 파싱)
console.log(parseInt('78.9'));   // 78 (소수점 이후는 무시)

Number('3월')
-> NaN

const result1 = Number('123abc');
console.log(result1); // NaN

const result2 = Number('123');
console.log(result2); // 123

const result3 = Number('   123   '); // 공백은 무시하고 숫자로 변환
console.log(result3); // 123

const result4 = Number('123.45'); // 소수점 포함 숫자로 변환
console.log(result4); // 123.45

const result5 = Number('abc'); // 숫자로 변환 불가
console.log(result5); // NaN
```

- 함수는 차이점이 무조건 존재한다.

### substr, substring

```jsx
'1234'.substr(0,2)
-> 12
'1234'.substring(0,2)
-> 12
```

### 주요 차이점

1. **두 번째 인자의 의미**:
    - `substr(start, length)`: 두 번째 인자는 길이를 나타냅니다.
    - `substring(start, end)`: 두 번째 인자는 종료 인덱스입니다(이 인덱스 직전까지 추출).
2. **음수 인덱스 처리**:
    - `substr(start, length)`: `start`가 음수이면 문자열의 끝에서부터의 위치를 나타냅니다. 예를 들어, `1`은 문자열의 마지막 문자를 나타냅니다.
    - `substring(start, end)`: `start`와 `end`가 음수이면 `0`으로 간주됩니다.
    

### 거듭제곱

```jsx
3**2
-> 9

2**3
-> 8
```

### Infinity

```jsx
Infinity
-> Infinity

2/0
-> Infinity

-2/0
-> -Infinity
```

### +와 -

```jsx
'문자열' + 0
-> '문자열0'

'문자열' - 0
-> NaN
```

- + 연산자는 문자열과 다른 자료형을 더하게 되면 다른 자료형이 문자열로 바뀐 후 문자열과 더해집니다.
- - 문자열은 다른 자료형이 먼저 숫자형으로 바뀐 후 빼기를 진행.
    - ‘문자열’을 숫자로 바꾸면 NaN이 되고, 여기서 0을 빼봤자 그대로 NaN
    - Number() 함수를 수행하는 것과 같다.
