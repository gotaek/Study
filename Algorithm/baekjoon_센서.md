```python
n = int(input())
k = int(input())

unsortedSensors = list(map(int, input().split()))

sortedSensors = sorted(unsortedSensors)

gapOfSensors = [sortedSensors[i+1]-sortedSensors[i]
                for i in range(0, len(sortedSensors)-1)]

sortedGapOfSensors = sorted(gapOfSensors)
print(sum(sortedGapOfSensors[:(n-k)]))
```
