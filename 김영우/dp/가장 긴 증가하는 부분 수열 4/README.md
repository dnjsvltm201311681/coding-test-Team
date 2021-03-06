# 가장 긴 증가하는 부분 수열 4

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
> [현재 비교하는수, 현재 비교하는 수의 이전 수 전체]  
> 를 비교한다.   
> 1. 만약 이전 수가 더 작으면 현재 dp를 올린다.
> 2. 그러나 이전 수의 dp가 1이 아닐 수가 있는데 부분 수열에 포함되는 수일 경우이다.
> 3. 따라서 **이전 수의 dp중 가장 큰 값**보다 1을 추가한 값이 현재 dp가 된다.
가장 긴 증가하는 부분 수열 1 의 dp 알고리즘을 다시 사용하여 dp를 만들었다.  
dp 사용시 n제곱 시간복잡도를 가지고 이진 탐색을 사용시 nLog(n) 의 시간 복잡도를 가진다고 하여 이진 탐색으로 풀어 dpMax(최장 dp의 길이)를 찾는데까지는 성공했음.  
그러나 그 방법을 사용하게 되면 생기는 L 배열이 가장 긴 증가하는 부분 수열을 가리키지 않으며 거의 무관계하다.  
그 방법으로 수열을 받아올 수도 있으나 몇번 시도해보고 실패하여 dp로 돌아왔다;
> (가장 긴 증가하는 부분 수열 5를 풀어서 완벽히 이해하도록 하자)

수열을 생성한 방법은 이렇다.
1. dp **뒤에서부터 높은 숫자 순서**로 검색하여 찾은 좌표를 읽는다
2. *스택*을 이용해서 각 좌표의 seq값들을 push해준다(js에서는 unshift)