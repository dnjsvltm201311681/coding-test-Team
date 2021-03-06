# 숫자 카드

## 문제

- 숫자 카드는 정수 하나가 적혀져 있는 카드이다. 상근이는 숫자 카드 N개를 가지고 있다. 정수 M개가 주어졌을 때, 이 수가 적혀있는 숫자 카드를 상근이가 가지고 있는지 아닌지를 구하는 프로그램을 작성하시오.

## 입력

- 첫째 줄에 상근이가 가지고 있는 숫자 카드의 개수 N(1 ≤ N ≤ 500,000)이 주어진다. 둘째 줄에는 숫자 카드에 적혀있는 정수가 주어진다. 숫자 카드에 적혀있는 수는 -10,000,000보다 크거나 같고, 10,000,000보다 작거나 같다. 두 숫자 카드에 같은 수가 적혀있는 경우는 없다.

- 셋째 줄에는 M(1 ≤ M ≤ 500,000)이 주어진다. 넷째 줄에는 상근이가 가지고 있는 숫자 카드인지 아닌지를 구해야 할 M개의 정수가 주어지며, 이 수는 공백으로 구분되어져 있다. 이 수도 -10,000,000보다 크거나 같고, 10,000,000보다 작거나 같다


## 출력

- 첫째 줄에 입력으로 주어진 M개의 수에 대해서, 각 수가 적힌 숫자 카드를 상근이가 가지고 있으면 1을, 아니면 0을 공백으로 구분해 출력한다.

## 제한 

- 

## 예제

input
``` 
5
6 3 2 10 -10
8
10 9 -5 2 3 4 5 -10
```
output
``` 
1 0 0 1 1 0 0 1
```

## 알고리즘 풀이

> 이진탐색을 구현만 하면 되는 문제
> 이진탐색의 구조를 설명하자

1. 이진탐색은 **정렬된 배열**을 대상으로 한다 
2. 배열의 가장 앞쪽 인덱스(start)와 뒤쪽 인덱스(end), 중간 인덱스(middle), 찾는 숫자(find)를 명시한다.
3. middle에 있는 숫자와 find를 비교하는데 만약 find가 arr[middle]보다 크다면 middle인덱스 이전의 값들은 전부 비교할 필요가 없게 된다. 작을 때도 마찬가지로 middle인덱스 이후의 값들은 당연히 틀리므로 비교할 필요가 없게 된다. **정렬된 배열**만을 대상으로 하는 이유가 여기에 있다.
   - arr[middle]을 pivot이라고 한다.
   - 가독성을 위해 middle을 새로 만들었지만 메모리가 아깝다면 start나 end를 pivot으로 잡아서 비교해도 문제 없다. 다만 세부적인 코드는 수정이 필요하다.
   - 비교할 필요가 없는 인덱스를 비교조차 하지 않기 때문에 대부분의 O(n*n) 탐색보다 월등히 빠르다.
4. 1회 비교해서 find가 pivot보다 크다면 배열은 [비교할 필요가 없는 숫자..., middle, middle보다 큰 값...] 이 되는데 middle도 더이상 비교할 필요가 없기 때문에 start를 middle + 1로 바꾼 후 다시 3 비교를 진행한다. 
5. 이것을 start가 end보다 커질 때까지 반복한다.
6. 마지막까지 찾지 못했다면 -1을 리턴한다.
7. 최종적으로 O(n * log(n))의 시간복잡도를 가진다.