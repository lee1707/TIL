![image](https://user-images.githubusercontent.com/35374344/41164646-a4c7e9ec-6b76-11e8-8d34-77ba0d6c3da0.png)

```
■ 정리하기
1. 합병 정렬과 퀵 정렬
- 분할정복 방법을 적용한 정렬 알고리즘(※교재2장 참조) - 합병 정렬 → O(nlogn), 안정적, 제자리 정렬이 아님
- 퀵 정렬 → 최악 O(n2
), 최선/평균 O(nlogn), 불안정적, 제자리 → 피벗 선택의 임
의성만 보장되면 평균적인 성능을 보일 가능성이 매우 높음


2. 힙 정렬
- (최대)힙 : 각 노드의 값이 자신의 자식 노드의 값보다 크거나 같은 완전 이진트리
→ 임의의 값 삽입과 최댓값 삭제가 용이 → 일차원 배열로 구현
- 힙 자료구조를 이용한 정렬 → ① 일차원 배열을 초기 힙으로 구축하는 단계, ②
최댓값 삭제 및 힙으로 재구성하는 단계를 반복
- 초기 힙 구축 방법 : ① 입력 배열의 각 원소에 대해 힙에서의 삽입 과정을 반복하
는 방법, ② 입력 배열을 우선 완전 이진트리를 만든 다음 아래에서 위로 그리고
오른쪽에서 왼쪽으로 진행하면서 각 노드에 대해서 힙의 조건을 만족시키는 방법
- 최댓값 삭제 및 힙으로 재구성 과정 : 힙의 루트 노드의 값과 힙에서의 맨 마지막
노드의 값을 교환한 후, 루트 노드로부터 리프 노드로 진행하면서 힙의 조건을 만
족하도록 조정
- O(nlogn), 불안정적, 제자리


3. 비교 기반 정렬 알고리즘의 하한
- 비교 기반 정렬 알고리즘으로서 O(nlogn)보다 더 좋은 성능을 갖는 알고리즘은 존
재하지 않음


4. 계수 정렬
- 데이터 분포 기반의 정렬 알고리즘
- 주어진 원소 중에서 자신보다 작거나 같은 값을 갖는 원소의 개수를 계산하여 정렬
할 위치를 찾아 정렬하는 방식 → 입력값이 어떤 작은 정수 범위 내에 있다는 것을
알고 있는 경우에만 적용 가능
- 입력값의 범위가 입력 원소의 개수보다 작거나 비례하는 경우 → O(n) - 안정적, 제자리 정렬이 아님


5. 기수 정렬
- 데이터 분포 기반의 정렬 알고리즘
- 주어진 원소의 킷값을 자릿수별로 나누고, 각 자릿수별로 계수 정렬과 같은 안정적
인 정렬 알고리즘을 반복적으로 적용하여 정렬하는 방식
- 입력 원소의 값의 자릿수가 상수인 경우 → O(n) - 안정적, 제자리 정렬이 아님
```