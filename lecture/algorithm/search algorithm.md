# Today I learned
search algorithm

```
되추적 기법의 원리
- 상태 공간 트리에서 해를 찾아다니다가 앞쪽에 더 이상 해가 없으면 왔던 길로 되돌아가서 다른 길을 찾아보는 방법
- 상태 공간 트리 → 주어진 입력으로 만들어낼 수 있는 모든 후보해를 리프 노드로 갖는 트리 → 루트 노드로부터 리프 노드까지의 경로는 하나의 후보해를 만들어 가는 과정
- 출발점에서부터 깊이 우선 탐색으로 트리를 순회하면서, 자식 노드로 갈 때에는 항상 해가 존재할 가능성을 확인해서 해가 있을 수 없다면 더 이상 나가지 않고 다른 자식 노드로 방향을 바꿈

되추적 기법을 적용한 저울 문제
무게 M인 물체를 n개의 추를 이용하여 양팔저울로 달 수 있는 지 확인하는 문제
- 상태 공간 트리
→ 레벨 i → i번째 추를 선택하는 노드와 선택하지 않는 노드로 구분
→ 자식 노드 방향으로 해의 존재 가능성 확인을 위한 정보 → Ssum(현재까지 선택한 추들의 무게의 합), Rsum(앞으로 고려할 추의 무게의 합)
- 되추적 알고리즘의 주요 기준 → 자식 노드의 Ssum > M 또는 (자식 노드의 Ssum + 자식 노드의 Rsum) < M이면 되추적
- 성능 분석 → O(2^n)
- 추와 물체의 무게에 아무런 제한이 없다.

되추적 기법을 적용한 0/1 배낭 문제
- 상태 공간 트리
→ 레벨 i → i번 물체를 선택하는 노드와 선택하지 않는 노드로 구분
→ 자식 노드 방향으로 해의 존재 가능성 확인을 위한 정보 → Ssum(현재까지 선택한 물체의 무게의 합), Psum(현재까지 선택한 물체의 이익의 합), Rsum(앞으로 고려할 물체의 이익의 합)
- 되추적 알고리즘의 주요 기준(Max: 현재까지 찾은 Psum의 최댓값) → 자식 노드의 Ssum > M 또는 Psum+Rsum < Max이면 되추적
- 성능 분석 → O(2^n)
- 오른쪽 자식 노드가 해인지 확인하는 과정은 생략 가능

분기한정 기법의 원리
- 최적화 문제에 대한 상태 공간 트리를 탐색할 때 각 노드의 한정값을 이용하는 방법 → 한정값: 현재 노드로 만들 수 있는 해의 상한이나 하한, 또는 둘 다
- 분기한정 기법의 동작 과정 → 한정값이 그 순간의 최적해보다 좋은 경우에만 탐색 후보로 집합에 보관 → 다음 탐색 대상은 집합에서 가장 좋은 한정값을 갖는 노드로 선택 → 좋은 해가 등장하면 최적해를 업데이트

분기한정 기법을 적용한 0/1 배낭 문제
- 상태 공간 트리 → 되추적 알고리즘과 동일
→ 각 노드는 Ssum, Psum 및 Fsum을 유지
→ Fsum → 각 노드의 한정값 → 현재 남은 용량에 앞으로 고려할 물체를 쪼개어 넣을 수 있을 때 배낭의 최대 이익 → 남은 물체를 쪼개지 않고 넣었을 때 배낭의 최대 이익의 상한
- 분기한정 알고리즘의 주요 기준(Max: 현재까지 찾은 Psum의 최댓값) → Ssum > M 또는 Fsum ≤ Max이면 탐색 후보에서 제외시킴
- 성능 분석 → O(2^n)
- 되추적 알고리즘보다 탐색하는 노드의 수를 줄여줄 수 있음

분기한정 기법을 적용한 외판원 문제
- 외판원 문제 → 여러 도시가 주어지고 도시 사이를 이동할 때 필요한 비용이 주어진 경우, 최소의 비용으로 모든 도시를 한 번씩만 방문하고 처음 도시로 돌아오는 방법을 찾는 문제 → 모든 도시 사이에 직접 이동이 가능하다고 가정
- 상태 공간 트리
→ 레벨 0 → 임의의 정점 A
→ 레벨 i → 정점 A로부터 i개의 간선으로 서로 다른 정점 (i+1)개를 연결한 경로
→ 각 노드는 한정값 Msum을 유지 → Msum: 현재까지 결정된 경로 상의 간선의 가중치의 합, 그리고 남은 각 정점에 대해 각 정점에 연결된 (제한된) 간선들의 가중치의 최솟값의 합을 더한 값 → 가능한 해의 하한
- 분기한정 알고리즘의 주요 기준(Min: 현재까지 찾은 해의 최솟값) 
→ 레벨 n-2인 노드(실제적인 리프 노드)의 Msum < Min이면 Min을 Msum으로 변경
→ Msum ≥ Min → 탐색 후보에서 제외
- 성능 분석 → O(2^n)
```
