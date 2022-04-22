```python
n, m = map(int, input().split())
package = []
individual = []

for _ in range(m):
    a, b = map(int, input().split())
    package.append(a)
    individual.append(b)

minPackage = min(package)
minIndividual = min(individual)

result1 = (n//6 if n % 6 == 0 else n//6 + 1)*minPackage
result2 = n//6*minPackage+n % 6*minIndividual
result3 = n*minIndividual
print(min(result1, result2, result3))

```
