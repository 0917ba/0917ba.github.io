---
date: 2025-09-16T23:43
updated: 2025-09-17T00:05
title: "BOJ Random Defense - 4일차"
categories: [Algorithm, 랜디]
image: null
math: true
---

![image](/assets/img/2025-09-17-BOJ-Random-Defense---4일차/Pasted-image-20250916234344.png)

5892를 제외하면 무난하게 방어한 것 같다.

## 문제 풀이

### [5892](https://www.acmicpc.net/problem/5892): Landscaping (<b><span style="color:rgb(256, 0, 0)">PASSED</span></b>)

어렵게 느낀 DP 문제이다. SCPC 2025 2차 예선 1번 문제와도 비슷해서 PTSD가 살짝 왔다.

[진한님의 풀이](https://blog.naver.com/jinhan814/222683184227)가 깔끔하고 좋은 풀이인 것 같다. 임의의 3번 연산 한 번은 인접한 두 위치에서 흙을 비용 $Z$에 옮기는 연산 여러 번으로 분해할 수 있다. 또한, 음수 높이를 허용한다면 일련의 1, 2, 3번 연산을 3번 연산을 모두 사용한 후 1, 2번 연산을 적용하는 것으로 생각할 수 있다.

뒤에서부터 배열 $A$를 $B$와 동일하게 만들어 줄 것이다. $dp(i, x)$: $i$번부터 $n$번까지의 흙더미의 높이를 올바르게 맞춰 줄건데, 초기에 $i$번 위치에 흙더미가 추가로 $x$만큼 쌓여있었을 때, 연산에 필요한 최소 비용이라 두자. $x$는 음의 정수가 될 수 있다. 구하고자 하는 답은 $dp(1, 0)$이다. 전이는 $i$번째 위치에서 $i+1$번째 위치로 흙을 얼마나 옮길 지를 고려하여 해줄 수 있다.

배열을 풀어헤쳐 편집 거리 비슷한 DP로 푸는 풀이도 존재한다. ([USACO 공식 풀이](https://usaco.org/current/data/sol_landscape.html)) MCMF로 모델링하여 푸는 풀이도 있다.

### [20652](https://www.acmicpc.net/problem/20652): Stuck in a Rut (<b><span style="color:rgb(0, 152, 116)">AC</span></b>, 35:54)

정렬 및 시뮬레이션으로 풀 수 있는 문제이다. $n$이 작으므로 모든 소 쌍 간의 충돌 위치와 충돌 시간을 모두 계산해두고, 시간이 이른 순으로 순회하여 실제로 그 점에서 두 소가 충돌하는지를 판별해주면 된다.

### [15362](https://www.acmicpc.net/problem/15362): Automobil (<b><span style="color:rgb(0, 152, 116)">AC</span></b>, 15:56)

재미있는 문제. 식을 잘 정리하면 convolution 느낌의 누적 합 형태로 표현할 수 있다. 이를 이용하여 $O(n+m+k)$에 문제를 해결할 수 있다.

### [3136](https://www.acmicpc.net/problem/3136): 평면도 (<b><span style="color:rgb(0, 152, 116)">AC</span></b>, 13:00)

모르는 태그 경고가 떠 있길래 문제를 읽고 생각해 보았더니 오일러 지표 기본 문제였다. 평면도를 따라 그리면서 vertex, edge의 개수를 set으로 세어 주면 된다. 이 때 X자 모양으로 교차하는 두 edge가 생길 수 있으므로, 그래프의 각 edge 길이에 2를 곱하여 평면 그래프로 만들어 주어야 한다.

### [4297](https://www.acmicpc.net/problem/4297): Ultra-QuickSort (<b><span style="color:rgb(0, 152, 116)">AC</span></b>, 04:19)

Inversion counting 기본 문제길래 쓱싹 풀었다.
