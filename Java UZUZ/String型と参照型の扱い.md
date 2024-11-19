## String型と参照型の扱い
- プリミティブ型は値が直接入っている変数だが、参照型との違いは変数を作る際の必要なメモリ領域が決まっている
```
整数
byte 1バイト
short 2バイト
int 4バイト
long 8バイト
小数点
float 4バイト
double 8バイト
文字
char 2バイト
論理値
boolean 1バイト
```
- 文字データをメモリに保存するには1文字につき2バイト必要だが、文字数によってどれだけメモリ領域を取ることになるのか読めない。このような変数はすべて参照型
### 疑似プリミティブ型
- String型は本来以下のように生成しなければならないが、プリミティブ型のようにい使用されるケースがあまりにも多いのでプリミティブ型と同じ感覚で扱えるようJavaの開発者によって特別なプログラムが組まれている。このような特性からString型は疑似プリミティブ型と呼ばれる
```
変数名： data
値： データ
String data = new String("データ");
```
- String型は文字列を内部的にchar型配列で管理しているが、参照された際に取得・結合した値を参照元に渡すよう内部的に処理され、まるでプリミティブのようなふるまいをする
```
String data{char[]{'デ', 'ー', 'タ'}}
```
### String型の比較 (変数名.equals(変数名))
- 参照型の変数に格納されているデータは具体的な値ではなく他の変数の場所情報である為、`==`を使った比較ができない
```
String name1 == String name2 // 比較できない
name1 = x丁目i番地 // 本来は意味不明の文字列が取得される
name2 = y丁目j番地
```
- `==`を使うと`x丁目i番地`と` y丁目j番地`の比較になるため当然`false`が出力される
```
name1.equals(name2)
```
- 上記では`true`出力
### 疑似プリミティブと生成されたString型で関係演算子を使う際の扱い
- 下記では`疑似 == 疑似`の場合のみ`true`を出力するが開発者の優しさのような有難迷惑
- 例外があるとややこしいので、比較には`.equals()`を使うことが好ましい
```
String  nameOfficial1 = new String("モコ") ;  //正式な作られ方をしたString型変数
String  nameOfficial2 = new String("モコ") ;  //正式な作られ方をしたString型変数
String  nameGizi1   = "モコ" ;                //疑似プリミティブな作られ方をしたString型変数
String  nameGizi2   = "モコ" ;                //疑似プリミティブな作られ方をしたString型変数
		
boolean check3 = nameOfficial1 == nameOfficial2 ;
System.out.println("▼『==』を用いた比較（正式⇔正式）");
System.out.println("check3：" + check3 );
		
boolean check4 = nameGizi1 == nameOfficial1 ;
System.out.println("▼『==』を用いた比較（疑似⇔正式）");
System.out.println("check4：" + check4 );
		
boolean check5 = nameGizi1 == nameGizi2 ;
System.out.println("▼『==』を用いた比較（疑似⇔疑似）※注目！");
System.out.println("check5：" + check5 );
```
