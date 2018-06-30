# Today I learned
approximation algorithm

```
1. 기본 개념
- 튜링 기계 → 테이프, 기호, 헤드, 상태, 규칙으로 구성 → 주어진 테이프와 규칙에
따라 동작하는 모델 → “주어진 입력과 알고리즘으로 동작하는 컴퓨터” → 결정론
적 튜링 기계 vs 비결정론적 튜링 기계

- 다항 시간 알고리즘 → 알고리즘의 수행 시간이 입력 크기 n에 대한 다항식으로
표현 → O(1), O(logn), O(n), O(nlogn), O(n2), …, O(nk), …

- 문제의 난이도 :
→ 쉬운 문제 → 결정론적 튜링 기계에서 다항 시간 알고리즘이 존재하는 문제
→ 어려운 문제 → 다항 시간 알고리즘보다 더 많은 수행 시간을 요구하는 문제
- 문제의 형태에 따른 분류 :
→ 판정 문제 → ‘예’ 혹은 ‘아니오’ 중 하나를 답으로 요구하는 형태의 문제
→ 최적화 문제 → 최솟값이나 최댓값을 구하는 형태의 문제
- 클래스 P와 클래스 NP
→ 클래스 P → 결정론적 튜링 기계에서 다항 시간에 해결할 수 있는 모든 판정
문제의 집합
→ 클래스 NP → 비결정론적 튜링 기계에서 다항 시간에 해결할 수 있는 모든 판
정 문제의 집합

- 변환 → 문제 A의 입력과 출력을 문제 B의 입력과 출력 형태로 바꿀 수 있고, 여
기에 문제 B를 해결하는 알고리즘을 적용함으로써 궁극적으로 문제 A를 풀 수 있
을 때, 문제 A를 문제 B로 변환할 수 있다고 하며, 이러한 변환에 다항 시간이 소
요되면 다항식 시간 변환이라고 한다. 2. NP-완전 문제

- 완전 문제 → 어떤 부류에 속하는 모든 문제가 그 부류에 속하는 어떤 문제 R로
다항식 시간 변환 가능하다면 문제 R은 그 부류의 완전(complete) 문제라고 함 →
완전인 문제는 해당 부류의 모든 문제를 대표하는 문제이며, 그 부류의 가장 어려
운 문제로 여겨짐

- 하드 문제 → 어떤 부류의 모든 문제가 어떤 문제 R로 다항식 시간 변환될 수 있
지만 문제 R이 그 부류에 속한다는 조건이 없다면 R은 그 부류에 대한 하드(hard)
과목명인 문제라고 함 → 해당 부류에 속하는 어떤 문제보다 풀기 어렵거나 또는 비슷한
정도로 풀기 힘든 문제

- NP-완전 문제와 NP-하드 문제 → 클래스 NP에 속하는 모든 문제가 어떤 문제 A
로 다항식 시간 변환된다면 문제 A는 NP-하드 문제이며, 여기에 문제 A가 클래스
NP에 속한다는 조건이 함께 만족되면 그 문제는 NP-완전 문제이다. - NP-완전 문제의 종류 → 외판원 문제, 0/1 배낭 문제, CNF 만족성 문제, 해밀토
니언 사이클 문제, 궤 채우기 문제, 파티션 문제, 클리크 판정 문제, 버텍스 커버
문제

- NP-완전성의 증명 → 어떤 문제가 NP-완전 문제인지를 보이기 위해서는, ① 알려
진 하나의 NP-완전 문제가 해당 문제로 다항식 변환됨을 보이고, ② 해당 문제를
푸는 비결정론적 튜링 기계가 존재함을 보인다. 3. 근사 알고리즘

- 근사 알고리즘 → 최적화 문제에 대해서 최적해에 가까운 해(“근사해, 가능해”)를
구하는 다항 시간 알고리즘

- 외판원 문제의 근사 알고리즘 → 주어진 그래프의 최소 신장 트리를 구하고, 트리
에서 임의의 정점 하나를 루트 노드로 지정해서 깊이 우선 탐색 순서대로 정점을
나열하고 마지막에 첫 정점을 한 번 더 추가한다. → O(|V|2) → 근사해는 최적해의
두 배를 넘지 않음

- 궤 채우기 문제의 근사 알고리즘 → 최초법, 최선법, 감소순 최초법, 감소순 최선법
→ O(n2) (n: 물체의 개수) → 근사해는 최적해의 두 배 혹은 1.5배를 넘지 않음

- 버텍스 커버 문제의 근사 알고리즘 → 임의의 간선을 선택하여 이와 맞닿은 두 정
점을 모두 버텍스 커버에 포함시키고, 두 정점에 부수된 모든 간선을 제거하는 과
정을 반복 → O(|E|) → 근사해는 최적해의 두 배를 넘지 않음
```