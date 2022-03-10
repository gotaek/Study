#방의 개수
문제를 풀기 위해서는 방이 생성되었는 지 판별할 수 있어야 한다. 방의 조건은 다음과 같다.
+ 현재 방문하는 노드가 이미 방문한 노드여야 한다.
+ 현재 방문하는 노드로 들어오는 경로는 처음이어야 한다.
이 조건을 만족해야 하며 하나의 명령에 대해서는 같은 방향으로 좌표를 두번씩 이동 시켜 모래시계형태의 예외 상황도 해결해주어야 한다. 
```python
# 프로그래머스 코딩테스트 연습 > 그래프 > 방의 개수

import collections


def solution(arrows):
    answer = 0
    move = [(-1, 0), (-1, 1), (0, 1), (1, 1),
            (1, 0), (1, -1), (0, -1), (-1, -1)]
    now = (0, 0)

    # visited : 노드 방문 체크
    # visited_dir : 노드 방문 경로 체크 ((A, B)는 A -> B 경로를 의미)
    visited = collections.defaultdict(int)
    visited_dir = collections.defaultdict(int)

    # arrows 따라 노드 좌표를 큐에 추가
    queue = collections.deque([now])
    for i in arrows:
        # 모래 시계 형태 예외를 처리하기 위해 해당 방향으로 2칸씩 추가한다.
        for _ in range(2):
            next = (now[0] + move[i][0], now[1] + move[i][1])
            queue.append(next)

            now = next

    now = queue.popleft()
    visited[now] = 1

    while queue:
        next = queue.popleft()

        # 이미 방문한 노드(visited[x]==1)인 경우
        if visited[next] == 1:
            # 해당 경로로 처음 들어온 경우인 경우 answer++
            # 처음 들어온 경우에 방이 처음 생성되므로!
            if visited_dir[(now, next)] == 0:
                answer += 1
        # 처음 방문한 노드인 경우 방문 체크를 한다.
        else:
            visited[next] = 1

        # 해당 노드로 들어온 경로를 방문 체크해준다.
        visited_dir[(now, next)] = 1
        visited_dir[(next, now)] = 1
        now = next

    return answer
  ```
  
  출처
  https://bellog.tistory.com/147
