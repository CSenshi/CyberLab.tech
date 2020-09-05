```python
s1 = "7410145a50001700131800015a46170b5a5409080051430a031d0e0c070e0000071c001818000519170f"
s2 = "78717a20616473647772657a2078797a2061617371206262716269696965206e6f207677766c727879"


# Convert to array of hexes
def convert1(s):
    res = []
    for i in range(len(s) // 2):
        res += [s[i * 2 : (i + 1) * 2]]
    return res


s1 = convert1(s1)
s2 = convert1(s2)
print()
print(f'{s1=}')
print(f'{s2=}')
print()

# Convert Hexes to numbers
def convert2(arr):
    return list(map(lambda x: int(x, 16), arr))


s1 = convert2(s1)
s2 = convert2(s2)
print()
print(f'{s1=}')
print(f'{s2=}')
print()

# XOR
def convert3(arr1, arr2):
    arr2 = [0] + arr2
    res = []
    for i in range(len(arr1)):
        res += [arr1[i] ^ arr2[i]]
    return res


arr = convert3(s1, s2)
print()
print(f'{arr=}')
print()

# Convert INT -> CHAR
def convert4(arr):
    return "".join(list(map(lambda x: chr(x), arr)))


arr = convert4(arr)
print()
print(f'{arr=}')
print()
```
