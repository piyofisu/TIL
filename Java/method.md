## Public static void main(String[] args)
- Javaの実行に必須のメソッド
## System.out.println()
- 引数の出力
## ;
- 命令の区切り
## /*  */
- Javaにおけるコメント
- 複数行の場合の書き方
## //
- 1行の場合は//から行末までがコメント
- ショートカットキーはctrl + /
## 変数の宣言
### データ型と変数名の指定```データ型 変数名;```
- プリミティブ型(基本データ型)
```
byte  -128	127	小さな整数
short  -32,768	32,767	小規模な整数
int  -2^31	2^31-1	標準的な整数
long  -2^63	2^63-1	大きな整数
float  -	-	単精度小数点数
double  -	-	倍精度小数点数
char  0	65,535 (Unicode)	文字
boolean  false	true	真偽値
```
- 参照型
```
String  String name = "Alice";
配列  int[] numbers = {1, 2, 3};
クラス  Person person = new Person();
```
- 同じデータ型の場合まとめて宣言可```int height, old;```
### var 型推論
- データ型が異なる場合再代入は不可
```
var number = 10;   // int型として推測される
var name = "Alice";  // String型として推測される
number = 20  //int型なので再代入可
name = 20  //int型の値をString型に代入できない
```
## final double ○○ = 1.1
- 変数○○の再代入を禁止
- 値を再代入できない変数は「定数」。○○を大文字で記述
## フォーマット指定子
- 文字列の中に変数の値を埋め込むために使用
- String.format() や System.out.printf()で使用
- ```%s```:文字列(String) ```%d```:整数(int) ```%f```: 浮動小数点数 (float, double) ```%c```: 単一の文字 (char) ```%n```: 改行 ```%%```: パーセント記号
```
String name = "Alice";
int age = 30;
double height = 1.75;
System.out.printf("Name: %s, Age: %d, Height: %.2f meters%n", name, age, height);
Name: Alice, Age: 30, Height: 1.75 meters
```
