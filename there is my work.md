# адекватное решение:
```python
'''
user_in = str(input("Введите номер: "))
user_in = user_in if len(user_in) > 8 else "8495" + user_in
    
bd = "8(495)430-23-97", "+7-4-9-5-43-023-97", "4-3-0-2-3-9-7", "8-495-430"
bd1 = [''.join(c for c in phone if c not in '!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~') for phone in bd]
bd2 = [''.join("8495" + c) if len(c) < 8 else c for c in bd1]

print(*map(lambda s: "\n{}".format("YES" if user_in == s else "NO"), bd2))
'''

# неудачные попытки вывода:
'''

print("{}".format(*(map(lambda x: "YES" if user_in == x else "NO", bd2))))
print(map(lambda s: print(s),bd2))
for s in bd2: print("{}".format("YES" if user_in == s else "NO"))

'''

# неадекватное решение
user_in = str(input("Введите номер: "))
print(*map(lambda s: "\n{}".format("YES" if (user_in if len(user_in) > 8 else "8495" + user_in) == s else "NO"), [''.join("8495" + c) if len(c) < 8 else c for c in [''.join(c for c in phone if c not in '!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~') for phone in ("8(495)430-23-97", "+7-4-9-5-43-023-97", "4-3-0-2-3-9-7", "8-495-430")]]))
```
