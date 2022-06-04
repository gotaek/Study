```python
n, k = map(int, input().split())
stuff = list(map(int, input().split()))

plugs = []
cnt = 0
for i in range(k):
    if stuff[i] in plugs:
        continue
    if len(plugs) < n:
        plugs.append(stuff[i])
        continue

    idxs = []
    for j in range(n):
        try:
            idx = stuff[i:].index(plugs[j])
        except:
            idx = 101
        idxs.append(idx)

    plug_out = idxs.index(max(idxs))
    del plugs[plug_out]
    plugs.append(stuff[i])
    cnt += 1
print(cnt)

```
출처:https://alpyrithm.tistory.com/71
