```python
class Solution:
    def findDuplicateSubtrees(self, root):
    # 종전과 다른 것은 고유한 tree를 저장하기 위한 데이터 구조가 새로 필요합니다.
        trees = {}

        count = {}
        ans = []

        def lookup(node):
            if node:
                # 왼쪽 자식의 고유 id를 가져옵니다.
                left_id = lookup(node.left)
                # 오른쪽 자식의 고유 id를 가져옵니다.
                right_id = lookup(node.right)

                # (자신의 값, 왼쪽 자식 고유 id, 오른쪽 자식 고유 id)로 key를 만들어서
                # 그것이 고유한 tree에 있으면 해당 id를 받아오고,
                # 기존에 없던 tree이면 unique한 번호를 부여합니다.
                if (node.val, left_id, right_id) not in trees:
                    trees[(node.val, left_id, right_id)] = len(trees)
                uid = trees[(node.val, left_id, right_id)]

                # 나머지 로직은 똑같습니다. uid가 두번 이상 출현하면 최종 결과에 추가해줍니다.
                count[uid] = count.get(uid, 0) + 1
                if count[uid] == 2:
                    ans.append(node)
                
                return uid

        lookup(root)
        return ans
  ```
  
  출처: https://smlee729.wordpress.com/2018/03/30/algorithm-%EB%AC%B8%EC%A0%9C-find-duplicate-subtrees/
