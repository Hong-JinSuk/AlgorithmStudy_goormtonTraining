## 과자 나눠주기
일반적인 이분 탐색 문제다. 이분 탐색을 할 땐 정렬을 해야 한다.

## 배열 돌리기 4
배열을 회전하는 것이 관건이다. 가장 바깥쪽 테두리부터 네 변을 회전시키고 네 꼭짓점을 따로 처리해준다.   
순서는 임의로 정할 수 있으므로 모든 순서의 경우를 백트래킹으로 탐색해봐야 한다. C++에서는 algorithm 헤더의 next_permutation 함수로 순서의 경우의 수를 쉽게 탐색할 수 있다.

## 이분 그래프
문제를 이해하는 것이 어려웠다. 노드를 번갈아가며 다른 색을 칠할 수 있으면 이분 그래프라는 것이다.   
첫 노드를 임의의 색으로 칠하고 그 옆의 노드를 다른 색으로 번갈아 칠하면서 탐색한다. bfs로 탐색하면 되고, bfs를 이용하면 연결된 모든 노드를 탐색하므로 첫 노드를 임의의 색으로 정해도 된다.
그래프가 끊겨 있을 수 있으므로 for문을 이용해 방문하지 않은 노드를 시작점으로 해서 bfs를 진행해야 한다. color를 처음에 0으로 초기화하고 1과 -1를 번갈아 칠하므로 visited 배열을 따로 정하지 않아도 된다.

## 전구와 스위치
스위치를 누르는 순서는 중요하지 않다. 1번을 누른 후 2번을 누르는 것과 2번을 누른 후 1번을 누른 것이 동일하다.   
스위치를 누르는 순서는 중요하지 않으므로 번호가 작은 스위치부터 누를 수 있다.   
번호를 순서대로 누른다면 i번 전구의 상태가 확정되는 것은 i + 1번 스위치를 누를 때이다.
i - 1번 전구가 비교하는 것과 다르다면 스위치를 누르고, 같다면 누르지 않는다.   
문제는 가장 처음에 있는 전구인데, 첫 스위치를 누르는 경우와 안 누르는 경우로 나누어서 비교하면 된다.   
첫 스위치를 누르는 것과 안 누르는 것 둘 다 성공하는 경우가 있다. 0 0과 0 0같은 경우 첫 스위치를 누른다면 스위치를 두 번 눌러야 하지만 첫 스위치를 누르지 않는다면 한 번도 누르면 안 된다.   
따라서 첫 스위치를 눌러서 성공한다고 해도 첫 스위치를 안 누르는 경우를 따져 보고 최솟값을 구해야 한다.