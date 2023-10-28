## 3章 誤解されない名前
### 「選択する」のであれば`select()`
### 「除外する」のであれば「exclude()」
### 限界値はlimtではなく、max・minを使う
### 範囲指定はfirst・lastを使う
- 【範囲指定をstartとstopで命名】
```javascript
const array = ["a", "b", "c", "d", "e"]
const start = 0
const stop = 4

// 範囲内の値を返す処
integerRange(start, stop)
```
- 【範囲指定をfitstとlastで命名】
```javascript
const array = ["a", "b", "c", "d", "e"]
const first = 0
const last = 4

// 範囲内の値を返す処
integerRange(first, last)
```
### 排他的範囲にはbeginとend
### ブーリアン型の命名ではis・has・can・should
