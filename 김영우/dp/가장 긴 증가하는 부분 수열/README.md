# 가장 긴 증가하는 부분 수열

## 문제

- 수열 A가 주어졌을 때, 가장 긴 증가하는 부분 수열을 구하는 프로그램을 작성하시오.
- 예를 들어, 수열 A = {10, 20, 10, 30, 20, 50} 인 경우에 가장 긴 증가하는 부분 수열은 A = {10, 20, 10, 30, 20, 50} 이고, 길이는 4이다.


## 입력

- 첫째 줄에 수열 A의 크기 N (1 ≤ N ≤ 1,000)이 주어진다.
- 둘째 줄에는 수열 A를 이루고 있는 Ai가 주어진다. (1 ≤ Ai ≤ 1,000)

## 출력

- 첫째 줄에 수열 A의 가장 긴 증가하는 부분 수열의 길이를 출력한다.

## 제한 

- 

## 예제

input
``` 
6
10 20 10 30 20 50
```
output
``` 
4
```

## 알고리즘 풀이
```
[ 10, 20, 10, 30, 20, 50 ]
1 1 1 1 1 1
1 2 1 1 1 1
1 2 1 1 1 1
1 2 1 3 1 1
1 2 1 3 2 1
1 2 1 3 2 4
1 2 1 3 2 4
4
```
[현재 비교하는수, 현재 비교하는 수의 이전 수 전체]  
를 비교한다.   
1. 만약 이전 수가 더 작으면 현재 dp를 올린다.
2. 그러나 이전 수의 dp가 1이 아닐 수가 있는데 부분 수열에 포함되는 수일 경우이다.
3. 따라서 **이전 수의 dp중 가장 큰 값**보다 1을 추가한 값이 현재 dp가 된다.
