```python
import math

s = ",..,....,...,,,,,..,,.,.,..,...,,...,,,,,...,.,.,..,,..,,..,,."
s += ',,'

# 1. Get pattern of 0's and 1's
s = s.replace(",", "0").replace(".", "1")
print(f"{s=}")

# 2. Create chunks of 8 bits
arr = []
for i in range(math.ceil(len(s) / 8)):
    arr += [s[i * 8 : (i + 1) * 8]]
print(f"{arr=}")

# 3. Decode bytes -> Integers
arr = list(map(lambda x: int(x, 2), arr))
print(f"{arr=}")

# 4. Decode Integers -> Characters
arr = list(map(lambda x: chr(x), arr))
print(f"{arr=}")

# 4. Print result as String
result = "".join(arr)
print(f"\n{result=}")
```
