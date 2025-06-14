---
title: ループと反復処理
slug: Web/JavaScript/Guide/Loops_and_iteration
l10n:
  sourceCommit: 2c762771070a207d410a963166adf32213bc3a45
---

{{jsSidebar("JavaScript Guide")}}
{{PreviousNext("Web/JavaScript/Guide/Control_flow_and_error_handling", "Web/JavaScript/Guide/Functions")}}

ループは、何かを繰り返して行う手軽で簡単な方法を提供します。 [JavaScript ガイド](/ja/docs/Web/JavaScript/Guide)の本章では、 JavaScript で利用可能な反復処理を行う数々の反復文を紹介します。

ループは、ある方向に _X_ 歩進み、次に別の方向に _Y_ 歩進むように誰かに指示するゲームをコンピューター化した版と考えることができます。例えば、「西に 5 歩進む」という概念はループとして、下記のように表現できます。

```js
for (let step = 0; step < 5; step++) {
  // 値が 0 から 4 まで計 5 回実行される
  console.log("一歩西に歩く");
}
```

ループには様々な種類がありますが、本質的にはそれらはすべて同じことをしています。
何らかの行為をある回数繰り返すということです（ただしその回数がゼロということもありえます）。

様々なループ機構が存在することによって、色々な方法でループの開始点と終了点を決定することができます。あるループの方が別の種類のループより簡単に目的を果たせる、という状況はたくさんあります。

JavaScript で提供されるループ文は以下のとおりです。

- [for 文](#for_文)
- [do...while 文](#do...while_文)
- [while 文](#while_文)
- [ラベルつき文](#ラベルつき文)
- [break 文](#break_文)
- [continue 文](#continue_文)
- [for...in 文](#for...in_文)
- [for...of 文](#for...of_文)

## for 文

{{jsxref("Statements/for", "for")}} 文によるループは指定された条件が `false` と評価されるまで繰り返されます。JavaScript の `for` ループは Java や C 言語の `for` ループと同じです。

`for` 文は以下のような形です。

```js-nolint
for (初期化式; 条件式; 加算式)
  文
```

`for` ループが実行されるとき、次の処理が行われます。

1. もしあれば、`初期化式`が実行されます。この式は通常、1 個またはそれ以上のループカウンターを初期化しますが、この構文ではいかなるレベルの複雑な式を入れることが可能です。初期化式で変数を宣言することもできます。
2. `条件式`が評価されます。`条件式`の値が真の場合、ループ文が実行されます。`条件式`の値が偽の場合、`for` ループは終了します。（`条件式`がすべて省略されている場合、条件式は真であるとみなされます。）
3. `文`が実行されます。複数の文を実行するには、それらの文をグループ化するために[ブロック文](/ja/docs/Web/JavaScript/Reference/Statements/block) (`{ }`) を使用します。
4. もしあれば、`加算式`が実行されます。
5. ステップ 2 に制御が戻ります。

### 例

例えば下記の例には `for` 文があり、スクロールリスト（複数選択が可能な [`<select>`](/ja/docs/Web/HTML/Reference/Elements/select) 要素）で選択されたオプションの数値をカウントしています。

#### HTML

```html-nolint
<form name="selectForm">
  <label for="musicTypes"
    >好きな音楽のジャンルをいくつか選び、下のボタンをクリックしてください。</label
  >
  <select id="musicTypes" name="musicTypes" multiple>
    <option selected>R&B</option>
    <option>Jazz</option>
    <option>Blues</option>
    <option>New Age</option>
    <option>Classical</option>
    <option>Opera</option>
  </select>
  <button id="btn" type="button">How many are selected?</button>
</form>
```

#### JavaScript

ここでは、 `for` 文が変数 `i` を宣言し、 `0` に初期化します。 `i` が `<select>` 要素のオプション数未満であることを確認し、後続の `if` 文を実行し、ループ内を一通り実行した後に `i` を 1 ずつ加算します。

```js
function countSelected(selectObject) {
  let numberSelected = 0;
  for (let i = 0; i < selectObject.options.length; i++) {
    if (selectObject.options[i].selected) {
      numberSelected++;
    }
  }
  return numberSelected;
}

const btn = document.getElementById("btn");

btn.addEventListener("click", () => {
  const musicTypes = document.selectForm.musicTypes;
  console.log(`You have selected ${countSelected(musicTypes)} option(s).`);
});
```

## do...while 文

{{jsxref("statements/do...while", "do...while")}} 文は指定された条件が偽になるまで繰り返します。

`do...while` 文は以下のような形です。

```js-nolint
do
  文
while (条件式);
```

`文`は、条件式がチェックされる前に一度ずつ実行されます。（複数の文を実行するには、ブロック文 (`{ }`) を使って文をグループ化します。）

`条件式`が `true` の場合、`文`が再び実行されます。`文`の実行終了時に毎回条件がチェックされます。条件が `false` の場合、実行は停止し、制御は `do...while` の次の文に渡ります。

### 例

次の例では、`do` ループは少なくとも一度繰り返されます。そして `i` が 5 未満でなくなるまで繰り返されます。

```js
let i = 0;
do {
  i += 1;
  console.log(i);
} while (i < 5);
```

## while 文

{{jsxref("Statements/while", "while")}} 文は指定された条件が `true` と評価される限り文を実行します。 `while` 文は以下のようになります。

```js-nolint
while (条件式)
  文
```

`条件式`が `false` となる場合、ループ内の`文`は実行を停止し、ループに続く文に制御が渡されます。

ループ内の`文`が実行される前に条件が検査されます。条件が `true` を返した場合、`文`が実行され、条件が再び検査されます。条件が `false` を返した場合、実行は停止し、 `while` の次の文に制御が渡されます。

複数の文を実行するには、それらの文をグループ化するブロック文 (`{ }`) を使用します。

### 例 1

次の例では、`while` ループは、`n` が `3` 未満の場合繰り返されます。

```js
let n = 0;
let x = 0;
while (n < 3) {
  n++;
  x += n;
}
```

各反復で、`n` がインクリメントされ、その値が `x` に加算されます。そのため、`x` と `n` は以下の値をとります。

- 1 回目の反復後 : `n` = `1`, `x` = `1`
- 2 回目の反復後 : `n` = `2`, `x` = `3`
- 3 回目の反復後 : `n` = `3`, `x` = `6`

3 回目の通過完了後、条件式 `n < 3` はもはや `true` ではなくなるため、ループが終了します。

### 例 2

無限ループは避けてください。ループ内の条件が最終的に `false` になることを確かめるようにしましょう。さもないと、ループは永遠に終了しません。次の `while` ループ文は、条件が決して `false` にならないので永遠に実行されます :

```js example-bad
// 無限ループは悪!
while (true) {
  console.log("Hello, world!");
}
```

## ラベルつき文

{{jsxref("Statements/label", "ラベル", "", "true")}}を使って、プログラム内の他の場所から参照できる識別子を組み込んだ文が作成できます。例えば、ループの識別にラベルを使い、そのプログラムでループを中断するか、実行を継続するかどうかを指定する場合に、ラベルを `break` 文や `continue` 文で使用することができます。

ラベル文の構文は以下のようになります。

```js-nolint
ラベル:
  文
```

`ラベル`の値には、予約語でなければあらゆる JavaScript 識別子を使用できます。ラベルによって識別される`文`はどんな文でもかまいません。ラベル付き文の例については、下記の `break` と `continue` の例を参照してください。

## break 文

{{jsxref("Statements/break", "break")}} 文を使用すると、ループ、`switch`、ラベル文を使った関連付けを終了させることができます。

- ラベルなしで `break` を使用すると、最も内側の `while`、`do-while`、`for`、`switch` をただちに終了し、次の文に制御を移します。
- ラベルつきで `break` を使用すると、指定したラベルつき文を終了します。

`break` 文の構文は下記のようになります。

```js-nolint
break;
break ラベル;
```

1. 最初の形では最も内側のループや `switch` を終了します
2. 2 つ目の形では指定した外側のラベルつき文を終了します。

### 例 1

次の例では、値が `theValue` である要素のインデックスを探すまで配列の要素を反復します。

```js
for (let i = 0; i < a.length; i++) {
  if (a[i] === theValue) {
    break;
  }
}
```

### 例 2: ラベルを中断

```js
let x = 0;
let z = 0;
labelCancelLoops: while (true) {
  console.log("外側のループ: " + x);
  x += 1;
  z = 1;
  while (true) {
    console.log("内側のループ: " + z);
    z += 1;
    if (z === 10 && x === 10) {
      break labelCancelLoops;
    } else if (z === 10) {
      break;
    }
  }
}
```

## continue 文

{{jsxref("Statements/continue","continue")}} 文は `while`、`do-while`、`for`、`label` 文を再起動する際に使用されます。

- ラベルなしで `continue` を使用すると、その文を囲んでいる最も内側の `while`、`do-while`、`for` 文による現在の反復を終了し、次の反復のループの実行を継続します。`break` 文とは対照的に、`continue` は完全にループの実行を終了しません。`while` ループの場合、条件にジャンプします。`for` ループでは、`加算式` にジャンプします。
- ラベルとともに `continue` を使用すると、この動作がそのラベルによって識別されるループ文に対して適用されます。

`continue`文の構文は下記のようになります。

```js-nolint
continue;
continue ラベル;
```

### 例 1

次の例では、`i` の値が 3 のときに実行される `continue` 文が使用された `while` ループを示しています。この場合、`n` の値は `1`、`3`、`7`、`12` となります。

```js
let i = 0;
let n = 0;
while (i < 5) {
  i++;
  if (i === 3) {
    continue;
  }
  n += i;
  console.log(n);
}
// ログ出力:
// 1 3 7 12
```

`continue;` をコメントアウトすると、ループは末尾まで実行され、 `1,3,6,10,15` という結果になります。

### 例 2

次の例では、`checkIandJ` とラベル付けされた文には `checkJ` とラベル付けされた文が含まれています。`continue` 文に出会うと、プログラムは `checkJ` の現在の反復を終了し次の反復を開始します。`continue` に出会うたびに、`checkJ` はその条件が `false` を返すまで繰り返されます。`false` が返されると、`checkIandJ` の残りの部分が完了し、その条件が `false` を返すまで `checkIandJ` が繰り返されます。`false` が返されると、プログラムは `checkIandJ` に続く文を継続します。

もし `continue` が `checkIandJ` のラベルを持っていると、プログラムは `checkIandJ` のラベル文の先頭から継続されます。

```js
let i = 0;
let j = 10;
checkIandJ: while (i < 4) {
  console.log(i);
  i += 1;
  checkJ: while (j > 4) {
    console.log(j);
    j -= 1;
    if (j % 2 === 0) {
      continue checkJ;
    }
    console.log(j, "is odd.");
  }
  console.log("i =", i);
  console.log("j =", j);
}
```

## for...in 文

{{jsxref("Statements/for...in","for...in")}} 文はオブジェクトにあるすべての列挙可能なプロパティに対し指定された変数を通して反復処理を行います。それぞれの異なるプロパティに、JavaScript は指定された文を実行します。`for...in` 文は下記のようになります。

```js-nolint
for (変数 in オブジェクト)
  文
```

### 例

次の関数は引数としてオブジェクトと、そのオブジェクトの名前を表す文字列を取ります。それからすべてのオブジェクトのプロパティに対して反復処理し、プロパティ名とその値を表示する文字列を返します。

```js
function dumpProps(obj, objName) {
  let result = "";
  for (const i in obj) {
    result += `${objName}.${i} = ${obj[i]}<br>`;
  }
  result += "<hr>";
  return result;
}
```

`make` プロパティと `model` プロパティを持つ `car` オブジェクトに対し、`result` は下記のようになります。

```plain
car.make = Ford
car.model = Mustang
```

### 配列

{{jsxref("Array")}} の要素に対して反復処理を行う方法としてこれを使用したくなるかもしれませんが、これは数値のインデックスに加えてユーザー定義プロパティの名前も返します。

したがって、配列を繰り返し処理する場合は、数値インデックスを使用する従来の {{jsxref("Statements/for","for")}} ループを使用した方が良いでしょう。なぜなら、Array オブジェクトを変更した場合（カスタムプロパティやメソッドを追加した場合など）、 `for...in` 文は配列要素に加えて、ユーザー定義プロパティに対しても反復処理するからです。

## for...of 文

{{jsxref("Statements/for...of","for...of")}} 文は、[反復可能オブジェクト](/ja/docs/Web/JavaScript/Reference/Iteration_protocols)（{{jsxref("Array")}}、{{jsxref("Map")}}、{{jsxref("Set")}}、{{jsxref("functions/arguments","arguments")}} オブジェクトなどを含む）を反復処理するループを生成し、それぞれのプロパティの値に対して実行したい文をともなって作られた反復処理フックを呼び出します。

```js-nolint
for (変数 of オブジェクト)
  文
```

次の例では、`for...of` ループと {{jsxref("Statements/for...in","for...in")}} ループとの違いを示しています。`for...in` はプロパティ名に対し反復処理する一方、 `for...of` はプロパティの値に対して反復処理します。

```js
const arr = [3, 5, 7];
arr.foo = "hello";

for (const i in arr) {
  console.log(i);
}
// "0" "1" "2" "foo"

for (const i of arr) {
  console.log(i);
}
// Logs: 3 5 7
```

`for...of` および `for...in` 文は、[構造分解](/ja/docs/Web/JavaScript/Reference/Operators/Destructuring)でも使用することができます。例えば、 {{jsxref("Object.entries()")}} を使用して、オブジェクトのキーと値を同時に反復処理することができます。

```js
const obj = { foo: 1, bar: 2 };

for (const [key, val] of Object.entries(obj)) {
  console.log(key, val);
}
// "foo" 1
// "bar" 2
```

{{PreviousNext("Web/JavaScript/Guide/Control_flow_and_error_handling", "Web/JavaScript/Guide/Functions")}}
