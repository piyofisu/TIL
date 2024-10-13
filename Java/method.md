## public class Main{ public static void main(String[] args){}}
- Javaの実行に必須のメソッド
## ;
- 命令の区切り
## /*  */
- Javaにおけるコメント
- 複数行の場合の書き方
## //
- 1行の場合は//から行末までがコメント
- ショートカットキーはctrl + /
## 変数の宣言
### 命名規則
- 先頭小文字
- 複数単語の場合、2番目以降の単語の先頭を大文字にする
### データ型と変数名の指定```データ型 変数名;```
- プリミティブ型(基本データ型)
```java
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
```java
String  String name = "Alice";
配列  int[] numbers = {1, 2, 3};
クラス  Person person = new Person();
```
- 同じデータ型の変数が複数の場合まとめて宣言可```int height, old;```
- 一度変数のデータ型を宣言するとその変数にはデータ型が異なる値は代入できない
```java
int age = 15;
 ○  age = 30;
 ×  age = 30.5;
 ×  age = "30years";
```
### var 型推論
- データ型が異なる場合再代入は不可
```java
var number = 10;   // int型として推測される
var name = "Alice";  // String型として推測される
number = 20  //int型なので再代入可
name = 20  //int型の値をString型に代入できない
```
### 基本データ型と参照型の違い
- 変数に格納される値が異なる
```java
- 基本データ型
int a = 10;
PC上にaという領域が確保されそこに値10が格納される
- 参照型
int[] x = {70, 80};
PC上にxという領域が確保されるが、参照型のデータは大きくなりがちなので別に新たに領域が確保され値はそちらに格納
xにはその値がどこにあるか、の情報のみが格納される
```
## 配列の宣言
```java
int[] scores; // 配列のデータ型と変数名
scores = new int[3]; // 何個の値を管理したいのか指定、3個
```
もしくは
```java
int[] scores = new int[3];
scores[0] = 70;
scores[1] = 90;
scores[2] = 80;
```
更に簡単に
```java
int[] scores = {70, 90, 80};
```
## 多重配列
- 複数の配列を1つの配列にまとめる
```java
int[] firstYearScores = {70, 90, 80};
int[] secondYearScores = {60, 50, 70};
int[][] scores = {{70, 90, 80}, {60, 50, 70}};
```
- 1つの要素を取り出す
```java
System.out.println(scores[1][0]);
結果
60
```
## 変数の定数化```final double TAX = 1.1```
- 変数taxの再代入を禁止
- taxを大文字で記述
- 先に宣言だけしておいて後からの代入もできる
## フォーマット指定子
- 文字列の中に変数の値を埋め込むために使用
- String.format() や System.out.printf()で使用
- ```%s```:文字列(String) ```%d```:整数(int) ```%f```: 浮動小数点数 (float, double) ```%c```: 単一の文字 (char) ```%n```: 改行 ```%%```: パーセント記号
```java
String name = "Alice";
int age = 30;
double height = 1.75;
System.out.printf("Name: %s, Age: %d, Height: %.2f meters%n", name, age, height);
Name: Alice, Age: 30, Height: 1.75 meters
```
## 条件分岐
```java
if (条件式) {
    処理;
}els if(条件式) {
    処理;
}else{
    処理;
}
```
## 文字列の一致```変数.equals("〇〇")```
- ```equals```は変数が括弧内文字列○○と一致するか判定する
- ifと組み合わせてみる
```java
if (name.equals("Java")) {
 System.out.println("Hello " + name);
}
```
## 繰り返し処理```for (カウンタ変数; 繰り返し条件; カウンタ変数の増減)```
- 以下は処理を3回繰り返し
- ```i```はカウンタ変数、慣習により```i```や```j```を使う
- ```i++```により処理が1回終わるごとに増えていく
```java
for (int i = 0; i < 3; i++) {
 処理;
}
```
## 乱数の生成```Math.random```
- 0.0以上1.0未満のランダムな数値が返される
```java
double rand = Math.random();
```
- 小数点以下を切り捨て1～100の整数値を得る
```java
double rand = Math.random() * 100 + 1;
int number = (int)rand;
```
上記(int)は自身に続く変数の値を整数型に変換するという意味
型変換やキャストと呼ぶ
