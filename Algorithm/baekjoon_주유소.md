```python
n = int(input())
distances = list(map(int, input().split()))
costsOfCities = list(map(int, input().split()))

totalCost = 0
startIndex = 0
costMinimum = costsOfCities[0]
for i in range(1, len(costsOfCities)):
    if i == len(costsOfCities)-1:
        totalCost += costMinimum*sum(distances[startIndex:i])
    elif costsOfCities[i] >= costMinimum:
        continue
    else:

        totalCost += costMinimum*sum(distances[startIndex:i])
        startIndex = i
        costMinimum = costsOfCities[i]

print(totalCost)
```
