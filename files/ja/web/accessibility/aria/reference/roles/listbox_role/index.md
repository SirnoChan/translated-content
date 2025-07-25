---
title: "ARIA: listbox ロール"
slug: Web/Accessibility/ARIA/Reference/Roles/listbox_role
original_slug: Web/Accessibility/ARIA/Roles/listbox_role
---

リストボックス (`listbox`) ロールは、HTML の `<select>` 要素とは異なり、画像を含むことができる、1 つまたは複数の静的な項目をユーザーが選択できるリストに使用します。

## 説明

リストボックス (`listbox`) ロールは、HTML の選択 ({{htmlelement("select")}}) 要素と同様に、ユーザーが 1 つまたは複数の静的な項目を選択できるリストを作成する要素を識別するために使用します。 `<select>` とは異なり、リストボックスは画像を含むことができます。 リストボックスのそれぞれの子は、オプション ([`option`](https://www.w3.org/TR/2010/WD-wai-aria-20100916/roles#option)) ロールを持つべきです。

HTML の選択要素や、1 項目しか選択できない場合はラジオボタンのグループ、複数項目を選択できる場合はチェックボックスのグループを使用することを強くお勧めします。 なぜなら、全ての子孫に対するフォーカスを管理するためには、キーボードでのインタラクティビティがたくさん必要であり、ネイティブの HTML 要素はこの機能を無料で提供してくれるからです。

リストボックス (`listbox`) ロールを持つ要素は、暗黙的な `aria-orientation` の値として垂直 (`vertical`) を持ちます。

リストに <kbd>Tab</kbd> で移動すると、他に何も選択されていない場合はリストの最初の項目が選択されます。 <kbd>上/下矢印</kbd>でリストをナビゲートし、<kbd>Shift + 上/下矢印</kbd>を押すと選択範囲が移動して拡張されます。 1 文字以上をタイプ入力すると、リスト項目をナビゲートします (同じ文字はその文字から始まる各項目に移動し、異なる文字はその文字列全体で始まる最初の項目に移動します) 。 現在の項目に関連付けられたコンテキストメニューがある場合、<kbd>Shift + F10</kbd> でそのメニューが起動します。 リスト項目がチェック可能である場合、<kbd>スペース</kbd>を使用してチェックボックス ([checkbox](https://www.w3.org/TR/wai-aria-practices/#checkbox)) をトグルできます。 選択可能なリスト項目の場合、<kbd>スペース</kbd>を使用して選択をトグルし、<kbd>Shift + スペース</kbd>を使用して連続する項目を選択し、<kbd>Ctrl + 矢印</kbd>を使用して選択せずに移動し、<kbd>Ctrl + スペース</kbd>を使用して連続しない項目を選択できます。 全ての項目を選択するには、チェックボックス、リンクまたは他の方法を使用することをお勧めします。 <kbd>Ctrl + A</kbd> は、このためのショートカットキーとして使用できます。 (訳注: 推奨モデルと説明の無い代替モデルの操作方法が混じっているし、それ以外にもキーボードインタラクションに無い説明や異なった説明もあります。)

リストボックスロールが要素に追加されるか、そのような要素が可視になると、スクリーンリーダーは、リストボックスがフォーカスを得たときにリストボックスのラベルとロールをアナウンスします。 オプションや項目がリスト内でフォーカスされると、次にそれがアナウンスされ、スクリーンリーダーがサポートしていれば、続いてリストでの項目の位置が示されます。 リスト内でフォーカスが移動すると、スクリーンリーダーは関連する項目をアナウンスします。

### 関連する ARIA のロール、ステート、プロパティ

#### 関連するロール

- [option](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/option_role)
  - : 1 つ以上のネストされたオプションが必要です。 選択された全てのオプションでは、`aria-selected` が `true` に設定されています。 選択されていない全てのオプションでは、`aria-selected` が (訳注: 省略されるか) `false` に設定されています。 オプションが選択可能でない場合は、`aria-selected` を省略します (訳注: オプションでは、aria-selected のデフォルトは、false であり、変更できないことを示すなら、aria-disabled や aria-readonly があります) 。
- [list](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/list_role)
  - : リスト項目 (`listitem`) 要素を含むセクション。

#### ステートとプロパティ

- aria-activedescendant
  - : リストボックス内で現在アクティブな要素の `id` 文字列を保持します。 それがオプション要素である場合、そのオプションの `aria-selected` の値が `true` であるかどうかに関係なく、それは最後にインタラクトされたオプションの `id` になります。 複数選択可能なリストボックス内であっても、1 つの `id` の値のみを取ります。 `id` がリストボックスの DOM 子孫を参照していない場合、その `id` は `aria-owns` 属性の IDs の中に含まれている必要があります。
- aria-owns
  - : これは、リストボックスの DOM 子要素ではない要素 IDs のスペース区切りのリストです。 ここにリストされている IDs は、他の要素の `aria-owns` 属性にもリストできません。
- aria-multiselectable
  - : ユーザーが複数のオプションを選択できる場合は、これを含めて `true` に設定します。 `true` に設定されている場合、選択可能な*全ての*オプションには、`aria-selected` 属性が含まれ、`true` または `false` に設定されているべきです。 選択可能*でない*オプションは、`aria-selected` 属性を持つ*べきではありません*。
    `false` または省略されている場合、いずれかのオプションが選択されているならば、現在選択されているオプションのみが `aria-selected` 属性を必要とし、`true` に設定されている必要があります (訳注: 仕様では、単一選択コンテナーに関する説明が複数選択コンテナーに比べて具体的ではなく曖昧なので、aria-selected を使わない「選択がフォーカスに従う」単一選択コンテナーと aria-selected を使う「選択がフォーカスに従わない」単一選択コンテナーが混ざっているようです) 。
- aria-required
  - : 空でない文字列値を持つオプションを選択する必要があることを示す論理属性。
- aria-readonly
  - : ユーザーは、オプションが選択されているかいないかを変更することはできませんが、リストボックスはそれ以外の操作が可能です。
- aria-label
  - : リストボックスを識別する、人間が読むことができる文字列値。 可視のラベルがある場合は、代わりに `aria-labelledby` を使用してそのラベルを参照するべきです。
- aria-labelledby
  - : リストボックスを識別する、要素 IDs のスペースで区切られたリストで、1 つ以上の可視の要素を識別します。 可視のラベルがない場合は、代わりに `aria-label` を使用してラベルを含めるべきです。 (注: 2 つの L が付いた「labelled」は、アクセシビリティ API の規約に基づく正しいスペルです。)
- aria-roledescription
  - : リストボックスのロールをより明確に識別する、人間が読むことができる文字列値。 スクリーンリーダーは、ラベル (ある場合) を読んだ後に、「リストボックス」と言う代わりに、この値をユーザーに読み上げることがよくあります。

(詳細および ARIA のステートとプロパティの完全なリストについては、[ARIA の `listbox` (role)](https://www.w3.org/TR/wai-aria-1.1/#listbox) の文書を参照してください。)

### キーボードインタラクション

- 単一選択リストボックスがフォーカスを受け取ったとき、
  - リストボックスがフォーカスを受け取る前にどのオプションも選択されていなかった場合、最初のオプションがフォーカスを受け取ります。 任意で、最初のオプションを自動選択することもできます。
  - リストボックスがフォーカスを受け取る前にオプションが選択されていた場合、フォーカスは選択されているオプションに設定されます。

- 複数選択リストボックスがフォーカスを受け取ったとき、
  - リストボックスがフォーカスを受け取る前にどのオプションも選択されていなかった場合、フォーカスは最初のオプションに設定され、選択状態の自動変更は行われません。
  - リストボックスがフォーカスを受け取る前に 1 つ以上のオプションが選択されていた場合、フォーカスはリストの中で最初に選択されているオプションに設定されます。

- <kbd>↓ (下矢印)</kbd>

  : 次のオプションにフォーカスを移動します。 任意で、単一選択リストボックスでは、選択もフォーカスと共に移動することがあります。

- <kbd>↑ (上矢印)</kbd>

  : 前のオプションにフォーカスを移動します。 任意で、単一選択リストボックスでは、選択もフォーカスと共に移動することがあります。

- <kbd>Home</kbd>

  &#x20;(任意): 最初のオプションにフォーカスを移動します。 任意で、単一選択リストボックスでは、選択もフォーカスと共に移動することがあります。 5 つ以上のオプションがあるリストでは、このキーをサポートすることを強くお勧めします。

- <kbd>End</kbd>

  &#x20;(任意): 最後のオプションにフォーカスを移動します。 任意で、単一選択リストボックスでは、選択もフォーカスと共に移動することがあります。 5 つ以上のオプションがあるリストでは、このキーをサポートすることを強くお勧めします。

- 先行入力は、全てのリストボックス、特に 7 つ以上のオプションがあるリストボックスに対してお勧めします。
  - 文字を入力: フォーカスは、入力された文字で始まる名前を持つ次の項目に移動します。
  - 複数の文字をすばやく続けて入力: フォーカスは、入力された文字列で始まる名前を持つ次の項目に移動します。

- **複数選択**: 作成者は、複数選択をサポートするために 2 つのインタラクションモデルのいずれかを実装することができます。 ユーザーがリストをナビゲートしながら&#x20;

  <kbd>Shift</kbd>

  &#x20;や&#x20;

  <kbd>Ctrl</kbd>

  &#x20;などの修飾キーを押し続けなくてもよい推奨モデルや、選択状態が失われるのを避けるためにナビゲート中に修飾キーを押し続ける必要のある代替モデルがあります。
  - 推奨選択モデル — 修飾キーを押し続ける必要はありません。
    - <kbd>スペース</kbd>

      : フォーカスされたオプションの選択状態を変更します。

    - <kbd>Shift + ↓ (下矢印)</kbd>

      &#x20;(任意): 次のオプションにフォーカスを移動し、選択状態をトグルします。

    - <kbd>Shift + ↑ (上矢印)</kbd>

      &#x20;(任意): 前のオプションにフォーカスを移動し、選択状態をトグルします。

    - <kbd>Shift + スペース</kbd>

      &#x20;(任意): 直前に選択した項目からフォーカスされた項目までの連続した項目を選択します。

    - <kbd>Ctrl + Shift + Home</kbd>

      &#x20;(任意): フォーカスされたオプションから最初のオプションまでの全てのオプションを選択します。 任意で、フォーカスを最初のオプションに移動します。

    - <kbd>Ctrl + Shift + End</kbd>

      &#x20;(任意): フォーカスされたオプションから最後のオプションまでの全てのオプションを選択します。 任意で、フォーカスを最後のオプションに移動します。

    - <kbd>Ctrl + A</kbd>

      &#x20;(任意): リスト内の全てのオプションを選択します。 任意で、全てのオプションが選択されている場合は、全てのオプションの選択を解除することもできます。

### 必要な JavaScript 機能

#### 単一選択リストボックスでオプションを選択する

ユーザーがオプションを選択すると、以下が起こる必要があります。

1. 前に選択したオプションの選択を解除し、`aria-selected` を `false` に設定するか、属性を完全に削除して、新しく選択を解除したオプションの外観を選択されていないように変更します。
2. 新しく選択したオプションを選択し、オプションに `aria-selected="true"` を設定し、新しく選択したオプションの外観を選択されているように変更します。
3. リストボックスの `aria-activedescendant` の値を、新しく選択したオプションの `id` に更新します。
4. オプションのブラー (blur) 、フォーカス、選択状態を視覚的に処理します。

#### 複数選択リストボックスでオプションの状態をトグルする

ユーザーがオプションをクリックしたり、オプションにフォーカスしているときに<kbd>スペース</kbd>を押すなどして、オプションの状態をトグルすると、以下が起こる必要があります。

1. 現在フォーカスされているオプションの `aria-selected` ステート (状態) をトグルし、`aria-selected` の状態を `false` なら `true` に、`true` なら `false` に変更します。
2. 選択状態を反映するようにオプションの外観を変更します。
3. オプションを選択の解除へトグルしている場合でも、リストボックスの `aria-activedescendant` の値を、ユーザーが直前にインタラクトしたオプションの `id` に更新します。

> [!NOTE]
> ARIA の使用の第一のルールは、要素を転用して ARIA のロール、ステート、プロパティを追加することでアクセス可能にするのではなく、必要としている意味論と振る舞いがすでに組み込まれているネイティブな機能を使用できることです。 `<option>` 要素を子孫に持つ `<select>` 要素は、必要な全てのインタラクションをネイティブに処理します。

## 例

#### 例 1: aria-activedescendant を使用する単一選択リストボックス

以下のスニペットは、リストボックスロールが HTML ソースコードに直接どのように追加されるかを示しています。

```html
<p id="listbox1label" role="label">色を選択:</p>
<div
  role="listbox"
  tabindex="0"
  id="listbox1"
  aria-labelledby="listbox1label"
  onclick="return listItemClick(event);"
  onkeydown="return listItemKeyEvent(event);"
  onkeypress="return listItemKeyEvent(event);"
  aria-activedescendant="listbox1-1">
  <div role="option" id="listbox1-1" class="selected" aria-selected="true">
    緑
  </div>
  <div role="option" id="listbox1-2">オレンジ</div>
  <div role="option" id="listbox1-3">赤</div>
  <div role="option" id="listbox1-4">青</div>
  <div role="option" id="listbox1-5">紫</div>
  <div role="option" id="listbox1-6">ペリウィンクル</div>
</div>
```

これは、ネイティブの HTML の {{htmlelement("select")}} 要素と {{htmlelement("label")}} 要素でより簡単に処理できます。

```html
<label for="listbox1">色を選択:</label>
<select id="listbox1">
  <option selected>緑</option>
  <option>オレンジ</option>
  <option>赤</option>
  <option>青</option>
  <option>紫</option>
  <option>ペリウィンクル</option>
</select>
```

#### より多くの例

- [スクロール可能なリストボックスの例](https://w3c.github.io/aria-practices/examples/listbox/listbox-scrollable.html): 1 より大きい `size` 属性を持つ HTML の `<select>` と同様な、スクロールしてより多くのオプションを表示する単一選択リストボックス。 (英語)
- [折りたたみ可能なドロップダウンリストボックスの例](https://w3c.github.io/aria-practices/examples/listbox/listbox-collapsible.html): 属性 `size="1"` を持つ HTML の `<select>` と同様な、アクティブにすると展開される単一選択の折りたたみ可能なリストボックス。 (英語)
- [並べ替え可能なオプションを持つリストボックスの例](https://w3c.github.io/aria-practices/examples/listbox/listbox-rearrangeable.html): オプションの追加、移動、および削除が可能なツールバーが付属する、単一選択リストボックスと複数選択リストボックスの両方の例。 (英語)

## ベストプラクティス

- キーボードからアクセス可能にするために、作成者はこのロールの全ての子孫のフォーカスを管理 ([Managing Focus](https://www.w3.org/TR/wai-aria-1.1/#managingfocus)) するべきです。
- リストがフォーカスされていない場合、作成者は選択に異なるスタイリングを使用することをお勧めします。 例えば、アクティブでない選択は、より明るい背景色で表示されることが多いです。
- リストボックスが別のウィジェットの一部でない場合は、`aria-labelledby` プロパティが設定されているべきです。
- 1 つ以上のエントリーがリストボックスの DOM の子でない場合、追加の `aria-*` プロパティを設定する必要があります ([ARIA のベストプラクティス](https://www.w3.org/TR/wai-aria-practices/#listbox_div) (英語) を参照) 。
- リストボックスを展開 ([expand](https://www.w3.org/TR/wai-aria-1.1/#aria-expanded)) する正当な理由がある場合は、コンボボックス ([`combobox`](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/combobox_role)) ロールの方がより適切かもしれません。

## 仕様書

{{Specifications}}

## スクリーンリーダーのサポート

TBD

## 関連情報

- [HTML `<select>` 要素](/ja/docs/Web/HTML/Reference/Elements/select)
- [HTML `<label>` 要素](/ja/docs/Web/HTML/Reference/Elements/label)
- [HTML `<option>` 要素](/ja/docs/Web/HTML/Reference/Elements/option)
- [ARIA: `combobox` ロール](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/combobox_role)
- [ARIA: `option` ロール](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/option_role)
- [ARIA: `list` ロール](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/list_role)
- [ARIA: `listitem` ロール](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/listitem_role)
- [ARIA のベストプラクティス — リストボックス](https://www.w3.org/TR/wai-aria-practices/#Listbox) (英語)
- [ARIA のロールモデル — リストボックス](https://www.w3.org/TR/wai-aria-1.1/#listbox) (英語)

1. [**WAI-ARIA ロール**](/ja/docs/Web/Accessibility/ARIA/Reference/Roles){{ListSubpagesForSidebar("/ja/docs/Web/Accessibility/ARIA/Roles")}}
