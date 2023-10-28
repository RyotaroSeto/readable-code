## 2章 名前に情報を詰め込む
- 「名前に情報を詰め込む」には、明確な単語を選ばなければいけない。「空虚な」単語は避けるべき
  - 明確な単語を選ぶ
  - 汎用的な名前を避ける
  - 抽象的な名前よりも具体的な名前を使う
  - 接尾辞や接頭辞を使って情報を追加する
  - 名前の長さを決める
  - 名前のフォーマットで情報を伝える
### 明確な単語を選ぶ
例えば、「get」はあまり明確な単語ではない。
```python
def GetPage(url):
...
```
- 「get」という単語からは何も伝わってこない。
  - このメソッドはページをどこから取ってくるのだろうか？
    - ローカルキャッシュから？データベースから？インターネットから？
    - インターネットから取ってくるのであれば、FetchPage()やDownloadPage()の方が明確

|  単語  |  代替案  |
| ---- | ---- |
|  send  |  deliver, dispatch, announce  |
|  find  |  search, extract, recover  |
|  start  |  	launch, create, open  |
|  make  |  	create, set up, build  |

### tmpやretvalなどの汎用的な名前を避ける
- tmpは一般的に「一時的な保管」という文脈で使われることが多い
- 以下のコードは生存期間は短いけど、「一時的な保管ではない」
  - わかりやすく伝えるには`user_info`などが適切
```javascript
let tmp = user.name 
tmp += user.phone_number
tmp += user.email
tmp += user.address
// 以下同様の処理
template.set("user_info", tmp)
```

### 抽象的な名前よりも具体的な名前を使う
- `ServerCanStart()`という名前のメソッドがあったとする
  - TCP/IPポートをサーバがリッスンできるか確認するメソッド
  - 抽象的なので具体的なメソッド名は`CanListenOnPort()`

### 名前の長さを決める
- スコープが小さい場合は「短い名前」も許容される。
```javascript
if(user){
  let u = user.info.telephoneNumber 
  alert(`ユーザーの電話番号:${u}`)
}
```
- スコープが小さいので「多くの情報を詰め込む必要はない」。
- uという変数名だと情報が全くないがコードを理解するための情報がすぐそばにあるので許容される。
- 頭文字と省略形
  - クラス名を`BackEndManager`ではなく、`BEManager`にしたりする。
  　　- このプロジェクト固有の省略形はNG
  - プログラマは`evaluation`を`eval`
  - `document`を`doc`
  - `string`を`str`を使う。よく使う省略形ならOK
