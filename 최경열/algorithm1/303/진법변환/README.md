## 2745번 진법 변환

### 난이도

> 브론즈2

### 문제

B진법 수 N이 주어진다. 이 수를 10진법으로 바꿔 출력하는 프로그램을 작성하시오.

10진법을 넘어가는 진법은 숫자로 표시할 수 없는 자리가 있다. 이런 경우에는 다음과 같이 알파벳 대문자를 사용한다.

A: 10, B: 11, ..., F: 15, ..., Y: 34, Z: 35

### 입력

첫째 줄에 N과 B가 주어진다. (2 ≤ B ≤ 36)

B진법 수 N을 10진법으로 바꾸면, 항상 10억보다 작거나 같다.

### 출력

첫째 줄에 B진법 수 N을 10진법으로 출력한다.

### 예제 입력 1 복사

```
ZZZZZ 36
```

### 예제 출력 1 복사

```
60466175
```

### 풀이

문자와 숫자, 특정 진법이 주어질때 10진법으로 변환시 값을
구하는 문제이다. 때문에 진수계산법에 따른 계산을 수행하면 되는데
여기서 문제는 크게 두개이다. 첫번째는 문자와 숫자가 섞여있기 때문에 0~9까지는 숫자로 그 이상은 알파벳으로 바꿔 숫자를 추출해야 한다. 때문에 isdigit로 숫자로 구별했고, 문자는
ord로 숫자로 바꾼후 -55를 해서 A가 10나오게 처리했다.
두번째는 a에 담긴 문자숫자들이 반대로 출력되어야지
제곱근이 성립이 되는데 이는 [::-1] 로 해서 처리해줬다.
