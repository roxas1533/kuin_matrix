# kuin_matrix
Kuin言語用の行列ライブラリ
## Matrixクラス
## \matrix@Matrix
行列のクラスです。
## Matrix@makeMatrix
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
## Matrix@makeIdentity
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
## Matrix@shape
「Matrix@shape」は、行列のサイズを返す関数です。
```
func shape(): []int
```
|戻り値|説明|
|:---|:---|
|戻り値|[行,列]で表されるint型の一次元配列|
## Matrix@trans
「Matrix@trans」は、転置行列を返す関数です。
```
func trans(): @Matrix
```
|戻り値|説明|
|:---|:---|
|戻り値|自分自身の転置行列|  
## Matrix@det
「Matrix@det」は、行列式を返す関数です。
始めに、LU分解法を用いて行列式をだしますが、LU分解できない行列の場合定義に従って計算します。
```
func det(): float
```
|戻り値|説明|
|:---|:---|
|戻り値|行列式|  

**例外**  
|発生条件|例外コード|
|:--|:--|
|行列が正方行列ではない|0x00000003|
## Matrix@addLine
「Matrix@addLine」は、現在の行列に行を追加する関数です。
この関数は直接自分自身の行列を変更します。
```
func addLine(line:[][]float)
```
|引数等|説明|
|:---|:---|
|line|追加する行|

**例外**  
|発生条件|例外コード|
|:--|:--|
|追加される行の列と現在の列の数が一致しない|0x00000002|
## Matrix@addCol
「Matrix@addLine」は、現在の行列に列を追加する関数です。
この関数は直接自分自身の行列を変更します。
```
func addCol(line:[][]float)
```
|引数等|説明|
|:---|:---|
|line|追加する列|

**例外**  
|発生条件|例外コード|
|:--|:--|
|追加される列の行と現在の行の数が一致しない|0x00000002|
## Matrix@VecToArray
「Matrix@VecToArray」は、自分自身が行または列ベクトルの場合一次元配列に変換したものを返す関数です。
```
func VecToArray():[]float
```
|戻り値|説明|
|:---|:---|
|戻り値|変換したfloat型の一次元配列|

**例外**  
|発生条件|例外コード|
|:--|:--|
|行または列ベクトルではない|0x00000004|
## Matrix@solvEq
「Matrix@solvEq」は、連立一次方程式を解く関数です。  
LU分解法を用いて解くため、LU分解できない場合解くことができません。
```
func solvEq(coefficient: &@Matrix, rvalue: &@Matrix): @Matrix
```
|引数等|説明|
|:---|:---|
|coefficient|係数行列|
|rvalue|右辺値の定数行列（本来は列ベクトルであるべきですが、<br>行ベクトルが渡されても内部で転置します。|

**例外**  
|発生条件|例外コード|
|:--|:--|
|係数行列が正方行列でない|0x00000003|
|右辺値が列または行ベクトルでない|0x00000004|

