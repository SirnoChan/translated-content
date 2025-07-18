---
title: asm.js
slug: Games/Tools/asm.js
---

{{Deprecated_header}}

[asm.js](http://asmjs.org/) は 高度に最適化可能な JavaScript のサブセットを規定する仕様です。この文書では、asm.js で可能なこと、利点、利用方法、そして関連する情報と使用例を解説します。

## asm.js とは

極めて小さく、厳密な JavaScript のサブセットです。while や if、数値型、トップレベルの名前付き関数といくつかの単純な生成物のみ利用可能です。オブジェクト、文字列、クロージャや、ヒープを必要とするものは利用できません。asm.js のコードは多くの点で C のそれと類似していますが、全ての JavaScript エンジンで動作します。JavaScript エンジンの最適化を助ける一方、[Emscripten](https://github.com/emscripten-core/emscripten) のようなコンパイラーが出力するべきコードを明確に規定しています。asm.js のコードと、それがどのように動作するのか、そしてどのように利用できるかを解説します。

JavaScript のサブセットは Just-In-Time (JIT) コンパイラーを持つ多くのエンジンで高度に最適化されています。しかし、明確な標準を定めることによって、この種のコードの最適化により取り組むことができ、また驚くほどの高速化が可能となります。議論と測定が容易になるため、複数の JS エンジンの間での協力がより簡単になります。この種のコードは全てのエンジンで高速に動作するべきで、そうでないのはバグであるべきです。そのためのエンジンが最適化するべき仕様となっています。

標準はウェブ向けにハイパフォーマンスなコードを出力したいと考えるコンパイラー製作者たちも助けます。asm.js の仕様を参考にでき、asm.js に忠実であれば高速に動作するということがわかるからです。C/C++ を JavaScript へコンパイルする [Emscripten](https://github.com/emscripten-core/emscripten) は asm.js を出力し、そのコードはいくつかのブラウザーでネイティブと同等の速度で動作します。

またエンジンが asm.js のコードを識別べきする場合、さらなる最適化を行えます。現在のところ、それが可能なブラウザーは Firefox のみとなっています。

## asm.js 言語のまとめ

asm.js は中間言語です。厳密に型づけされた整数および浮動小数点演算、関数呼び出しとヒープ領域へのアクセスのみが許されるため、パフォーマンスレートの予測が極めて容易です。通常の JavaScript と比べ、そのパフォーマンス特性はネイティブコードに近くなっています。主要なブラウザーは既に asm.js をサポートしています。asm.js はブラウザー内で動作するため、ブラウザーとハードウェアに大きく依存します。
