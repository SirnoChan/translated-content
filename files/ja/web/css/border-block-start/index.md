---
title: border-block-start
slug: Web/CSS/border-block-start
l10n:
  sourceCommit: 429d45679a29f386af0ddfcf2a64498843c3e1e5
---

**`border-block-start`** は [CSS](/ja/docs/Web/CSS) のプロパティで、個々の論理的なブロック方向の先頭側境界のプロパティ値を、スタイルシート内の単一の場所で設定するための[一括指定プロパティ](/ja/docs/Web/CSS/CSS_cascade/Shorthand_properties)です。

{{InteractiveExample("CSS デモ: border-block-start")}}

```css interactive-example-choice
border-block-start: solid;
writing-mode: horizontal-tb;
```

```css interactive-example-choice
border-block-start: dashed red;
writing-mode: vertical-rl;
```

```css interactive-example-choice
border-block-start: 1rem solid;
writing-mode: horizontal-tb;
```

```css interactive-example-choice
border-block-start: thick double #32a1ce;
writing-mode: vertical-lr;
```

```html interactive-example
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">
    これは周囲に境界線があるボックスです。
  </div>
</section>
```

```css interactive-example
#example-element {
  background-color: #eee;
  color: #8b008b;
  padding: 0.75em;
  width: 80%;
  height: 100px;
  unicode-bidi: bidi-override;
}
```

## 構成要素のプロパティ

このプロパティは以下の CSS プロパティの一括指定です。

- [`border-block-start-color`](/ja/docs/Web/CSS/border-block-start-color)
- [`border-block-start-style`](/ja/docs/Web/CSS/border-block-start-style)
- [`border-block-start-width`](/ja/docs/Web/CSS/border-block-start-width)

## 構文

```css
border-block-start: 1px;
border-block-start: 2px dotted;
border-block-start: medium dashed blue;

/* グローバル値 */
border-block-start: inherit;
border-block-start: initial;
border-block-start: revert;
border-block-start: revert-layer;
border-block-start: unset;
```

`border-block-start` は 1 つ以上の {{cssxref("border-block-start-width")}}, {{cssxref("border-block-start-style")}}, {{cssxref("border-block-start-color")}} の値の組み合わせを使用することができます。対応づけられる物理的な境界は、書字方向やテキストの向きによって決まります。これは {{cssxref("border-top")}}, {{cssxref("border-right")}}, {{cssxref("border-bottom")}}, {{cssxref("border-left")}} の何れかに対応し、どれに対応するかは {{cssxref("writing-mode")}}, {{cssxref("direction")}}, {{cssxref("text-orientation")}} で定義された値によって決まります。

関連するプロパティとしては、 {{cssxref("border-block-end")}}, {{cssxref("border-inline-start")}}, {{cssxref("border-inline-end")}} が要素の他の境界を定義します。

### 値

`border-block-start` は以下の値のうちの 1 つ以上を任意の順序で指定します。

- `<'border-width'>`
  - : 境界の幅です。 {{cssxref("border-width")}} を参照してください。
- `<'border-style'>`
  - : 境界線のスタイルです。 {{cssxref("border-style")}} を参照してください。
- {{CSSXref("&lt;color&gt;")}}
  - : 境界線の色です。

## 公式定義

{{CSSInfo}}

## 形式文法

{{csssyntax}}

## 例

### 縦書きテキストの境界線

#### HTML

```html
<div>
  <p class="exampleText">テキストの例</p>
</div>
```

#### CSS

```css
div {
  background-color: yellow;
  width: 120px;
  height: 120px;
}

.exampleText {
  writing-mode: vertical-rl;
  border-block-start: 5px dashed blue;
}
```

{{EmbedLiveSample("縦書きテキストの境界線", 140, 140)}}

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- [CSS 論理的プロパティと値](/ja/docs/Web/CSS/CSS_logical_properties_and_values)
- このプロパティは {{cssxref("border-top")}}, {{cssxref("border-right")}}, {{cssxref("border-bottom")}}, {{cssxref("border-left")}} のうちの一つに対応づけられます。
- {{cssxref("writing-mode")}}, {{cssxref("direction")}}, {{cssxref("text-orientation")}}
