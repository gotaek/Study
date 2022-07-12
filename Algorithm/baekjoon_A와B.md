```python
s = input()
t = input()

len_s = len(s)
len_t = len(t)

while len_t > len_s:
    last_character = t[-1]

    if last_character == 'B':
        t = t[:-1][::-1]
    else:
        t = t[:-1]

    len_t -= 1

if t == s:
    print(1)
else:
    print(0)
```
