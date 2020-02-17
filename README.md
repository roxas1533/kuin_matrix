# kuin_matrix
Kuin言語用の行列ライブラリ
## Matrixクラス
### \matrix@Matrix
行列のクラスです。
### Matrix@new
「Matrix@new」は、行列クラスのインスタンスを生成する関数です。  
```
func makeMatrix(data : [][]float): @Matrix
```
|引数等|説明|
|:---|:---|
|data|計算に使う行列です。|
|戻り値|行列クラスのインスタンス|  

**例外**  
|発生条件|例外コード|
|:--|:--|
|2次元配列の行同士のサイズが一致しない|0x00000001|
### Matrix@makeIdentity
「Matrix@makeIdentity」は、単位行列のインスタンスを生成する関数です。
```
func makeIdentity(num : int): @Matrix
```
|引数等|説明|
|:---|:---|
|num|行列のサイズ|
|戻り値|行列クラスのインスタンス|  

**例外**  
|発生条件|例外コード|
|:--|:--|
|numに0以下が渡される|0x00000006|
