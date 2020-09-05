* სატესტო სკრიპტი (ვიპოვოთ დეკრიპტის სწორი ფუნცქია):
```python
# Python2
from itertools import cycle

a = 'abcdefghijklmnopqrstuvwxyz'
b = 26 # int(0x1A, 16)


TEST_STR="nsbzrlvrtvbucacaj".lower()
KEY="robinson"

# Encrypt
def encrypt(key, p):
    print "I'm gonna do some crypting!"
    items = zip(p, cycle(key))
    result = ''
    for item in items:
        total = reduce(lambda u, v: a.index(u) + a.index(v), item)
        result += a[total % b]
    return result.lower()

# Decrypt
def decrypt(key, p):
    print "I'm gonna do some decrypting!"
    items = zip(p, cycle(key))
    result = ''
    for item in items:
        total = reduce(lambda u, v: a.index(u) - a.index(v), item)
        result += a[total % b]
    return result.lower()

# Decrypt(Encrypt(s))
e = encrypt(KEY, TEST_STR.lower())
d = decrypt(KEY, e)

print(e)
print(d)
assert TEST_STR == d
```

* გავშიფროთ მოცემული ტექსტი ნაპოვნი decrypt ფუნქციით
```python
from itertools import cycle

a = 'abcdefghijklmnopqrstuvwxyz'
b = 26 # int(0x1A, 16)

KEY="robinson"
CIPHER="nsbzrlvrtvbucacaj"

# Decrypt
def decrypt(key, p):
    print "I'm gonna do some decrypting!"
    items = zip(p, cycle(key))
    result = ''
    for item in items:
        total = reduce(lambda u, v: a.index(u) - a.index(v), item)
        result += a[total % b]
    return result.lower()

d = decrypt(KEY, CIPHER)
print(d)
```
