## turpleとlistの違い
tuple > appendできない。constのようなもの

## setとは
- {1,2,3}
- 値が重複しない
### 追加
- myset.add()
### 削除
- myset.remove()
### 積集合
- A & B
- A.intersection(B)
### 和集合
- A | B
- A.union(B)
### 差集合
- A - B
- A.difference(B)

### 排他的論理和？
- A ^ B
- A.symmetric_difference(B)

## list
重複を許す

## 内包表記
- 1行で記述できる
```python
# リストの各値を二乗
numbers = [1,2,3]
squares = [num**2 for num in numbers]
# リストから1文字ずつ取り出す
words = ['python','django']
one_wods = [char for word in words for char in word]
# 九九
table = [[ a * b for b in range(1,10) ] for a in range(1,10)]
# 辞書型
dicts = {x:'default' for x in range(10)}
# generator
gen = (x for x in numbers)
```




