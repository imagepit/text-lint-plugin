# コードブロック記述ルール

## 基本ルール

- コマンドはできる限り1コマンド毎にわけてコードブロックで表現すること
- 言語指定を明記すること（例：bash, java, typescript, etc）
- 実行結果や出力も併せて示すこと
- コードブロックの前にファイルパスを `_` で囲って入れる
- コードブロックの内容についての説明をコードブロックの前やコメントで行うこと

## 追加・削除マーカー

### 追加マーカー

コードで追加する箇所は `//addstart` と `//addend` で囲む。

**重要**: プログラム言語の文法として `#` がコメントの場合でも `//addstart` と `//addend` で囲む。

```java
public class Sample{
  public static void main(String[] args){
    //addstart
    System.out.println("Hello World!!");
    //addend
  }
}
```

### 削除マーカー

コードで削除する箇所は `//delstart` と `//delend` で囲む。

**重要**: プログラム言語の文法として `#` がコメントの場合でも `//delstart` と `//delend` で囲む。

```java
public class Sample{
  public static void main(String[] args){
    //delstart
    System.out.println("Hello World!!");
    //delend
  }
}
```

## ファイルパスの記述

プログラムファイルを追加・更新する箇所はコードブロックの前にファイルパスを `_` で囲って入れる。

### ターミナルでコマンド実行の例

```markdown
_ターミナルでコマンド実行_
```bash
curl http://localhost:8080/api/hello
```
```

### プログラムコードの例

```markdown
`src/utils/math.ts`に以下の内容を追加します。

[コードブロックの内容についての説明]

_src/utils/math.ts_
```typescript
// 数学ユーティリティ関数
export function add(a: number, b: number): number {
  return a + b;
}
```
```
