---
title: Firefox 3 for developers
slug: Mozilla/Firefox/Releases/3
l10n:
  sourceCommit: a35e5b74ecbe13a768edf765a4666fb81a5153a1
---

もしあなたが開発者で、Firefox 3 における新機能全体について情報を得ようとしているなら、ここは理解を深めるのに最も適した場所です。この記事は、Firefox 3 に追加された機能をカバーする新しい記事の一覧を提供します。小さな変更が必ずしもすべてカバーされているわけではありませんが、主要な改善を学ぶ助けにはなるでしょう。

## Firefox 3 の開発者向け新機能

### ウェブサイトとウェブアプリケーション開発者向け

- [Firefox 3 のためのウェブアプリケーションの更新](/ja/docs/Mozilla/Firefox/Releases/3/Updating_web_applications)
  - : Firefox 3 における新機能を活用するためにウェブサイトやウェブアプリケーションで必要となるかもしれない変更についての情報を提供します。
- [オンライン・オフラインイベント](/ja/docs/Web/API/Navigator/onLine)
  - : Firefox 3 は WHATWG のオンライン・オフラインイベントをサポートします。これは、ウェブアプリケーションや拡張機能から、インターネットに接続しているかどうかや、接続開始・終了のタイミングを検出できるようにします。
- [ウェブベースのプロトコルハンドラー](/ja/docs/Web/API/Navigator/registerProtocolHandler)
  - : `navigator.registerProtocolHandler()` メソッドを利用して、ウェブアプリケーションをプロトコルハンドラーとして登録できるようになりました。
- [キャンバスを使用したテキストの描画](/ja/docs/Web/API/Canvas_API/Tutorial/Drawing_text)
  - : Firefox 3 でサポートされた標準化されていない API を利用して、キャンバス内にテキストを描画できるようになりました。
- [キャンバスの座標変換の対応](/ja/docs/Web/API/Canvas_API/Tutorial/Transformations#transforms)
  - : Firefox がキャンバスの `transform()` と `setTransform()` メソッドをサポートするようになりました。
- [マイクロフォーマットの使用](/ja/docs/Web/HTML/Guides/Microformats)
  - : Firefox にマイクロフォーマットを扱うための API が実装されました。
- [ドラッグ & ドロップイベント](/ja/docs/Web/API/HTML_Drag_and_Drop_API)
  - : Firefox 3 は、ドラッグが開始されるときと終了したときにドラッグ操作に対するソースノードへ送られる新しいイベントをサポートします。
- [HTML でのフォーカス管理](/ja/docs/Web/API/Document/hasFocus)
  - : 新しい HTML 5 の `activeElement` 及び `hasFocus` 属性がサポートされます。
- Firefox でのオフラインリソース
  - : Firefox で、ウェブアプリケーションがオフラインの間でも使えるようにするキャッシュリソースをリクエストできるようになりました。
- [Firefox 3 での CSS の改良](/ja/docs/CSS_improvements_in_Firefox_3)
  - : Firefox 3 は、CSS サポートにおける数々の改善を行っています。
- [Firefox 3 での DOM の改良](/ja/docs/Mozilla/Firefox/Releases/3/DOM_improvements)
  - : Firefox 3 は、DOM 実装において、いくつかの Internet Explorer 独自拡張を含む、多くの新機能を提供します。
- [JavaScript 1.8 対応](/ja/docs/New_in_JavaScript_1.8)
  - : Firefox 3 は JavaScript 1.8 をサポートします。
- [EXSLT support](/ja/docs/Web/XML/EXSLT)
  - : Firefox 3 は、 [XSLT](/ja/docs/Web/XML/XSLT) の拡張となる [EXSLT](/ja/docs/Web/XML/EXSLT) の実質的なサブセットのサポートを提供します。
- [Firefox 3 での SVG の改良](/ja/docs/Mozilla/Firefox/Releases/3/SVG_improvements)
  - : Firefox 3 での SVG サポートは、24 を超える新しいフィルター、いくつかの新しい要素と属性、そして、その他の改良を含み、大幅に強化されました。
- [アニメーション PNG グラフィック](/ja/docs/Web/Media/Guides/Formats/Image_types#apng_animated_portable_network_graphics)
  - : Firefox 3 は、アニメーション PNG (APNG) 画像形式をサポートしています。

### XUL と拡張機能開発者向け

#### 重要な変更と改良

- [Firefox 3 のための拡張機能の更新](/ja/docs/Mozilla/Firefox/Releases/3/Updating_extensions)
  - : 拡張機能を Firefox 3 に対応させるにあたって必要となることのガイドを提供します。
- [Firefox 3 での XUL の改良](/ja/docs/XUL_improvements_in_Firefox_3)
  - : Firefox 3 は、新しいスライドスケール、日付と時刻の選択ウィジェット、スピンボタンを含む、多くの新しい XUL 要素を提供します。
- [Firefox 3 でのテンプレート](/ja/docs/Templates_in_Firefox_3)
  - : テンプレートは Firefox 3 で大幅に改善されました。主な改善は、独自のクエリープロセッサーを使って、RDF 以外の種類のデータソースも扱えるようになったことです。
- [安全な更新](/ja/docs/Extension_Versioning,_Update_and_Compatibility#securing_updates)
  - : ユーザーにより安全な更新を提供するため、アドオンの更新をインストールする前に、安全な手段を使って更新情報を取得することが必須となりました。[Firefox Add-ons](https://addons.mozilla.org) に登録されているアドオンは、自動でこの手段を提供します。
- [位置情報のマイグレーションガイド](/ja/docs/Places_Developer_Guide)
  - : 既存の拡張機能を Places API に対応させる方法についての記事。
- [Firefox 3 でのダウンロードマネージャーの改良](/ja/docs/Download_Manager_improvements_in_Firefox_3)
  - : Firefox 3 のダウンロードマネージャーには、複数のプログレスリスナーへのサポートを含む、新たな API や改善された API が含まれています。
- nsILoginManager の使用
  - : パスワードマネージャーは、新しいログインマネージャーに置き換えられました。
- [埋め込み XBL バインディング](/ja/docs/XBL/XBL_1.0_Reference/Elements#binding)
  - : XBL バインディングを、別の XML ファイルから読み込む代わりに、Chrome コードから `data:` URL スキーマを使って直接組み込むことができるようになりました。
- [拡張機能の説明のローカライズ](/ja/docs/orphaned/Localizing_extension_descriptions)
  - : Firefox 3 では、アドオンのメタデータをローカライズする新しい方法がサポートされました。これにより、アドオンのダウンロード直後や無効時にローカライズされた詳細説明が表示されるようになりました。
- [ローカライズと複数形](/ja/docs/Localization_and_Plurals)
  - : Firefox 3 では、新しい PluralForm モジュールがサポートされました。このモジュールは、複数のローカライゼーションで複数形の単語を正しく扱うためのツールを提供します。
- [Firefox 3 でのテーマの変更](/ja/docs/Theme_changes_in_Firefox_3)
  - : Firefox 3 向けのテーマを作成したい方々にとって役立つ注意と情報です。

#### 新しいコンポーネントと機能

- [FUEL Library](/ja/docs/Toolkit_API/FUEL)
  - : FUEL は、XPCOM の形式的な部分を少なくし、いくつかの "モダンな" JavaScript のアイデアを追加することによって、拡張機能の開発をより生産的にします。
- [Places](/ja/docs/Places)
  - : 履歴とブックマークの API は、新しい [Places](/ja/docs/Places) API で完全に置き換えられます。
- [アイドルサービス](/ja/docs/nsIIdleService)
  - : Firefox 3 では、ユーザーが最後にキーを入力、もしくは、マウスを動かしてからどのくらいの時間が経過しているかを拡張機能が測定できるようにする、新しい `nsIIdleService` インターフェイスが追加されました。
- [ZIP ライター](/ja/docs/nsIZipWriter)
  - : 新しい `nsIZipWriter` インターフェイスによって拡張機能は ZIP アーカイブを作れるようになります。
- [フルページズーム](/ja/docs/Mozilla/Firefox/Releases/3/Full_page_zoom)
  - : Firefox 3 では、テキストのみのズームに加えて、フルページズームが追加されたことで、ユーザー体験が改善されています。
- [XPCOM サイクルコレクターとのインターフェイス](/ja/docs/Interfacing_with_the_XPCOM_cycle_collector)
  - : XPCOM コードが、使われていないメモリーをリークする代わりに解放させるようにする「サイクルコレクター」を活用できるようになりました。
- [スレッドマネージャー](/ja/docs/The_Thread_Manager)
  - : Firefox 3 は、自作コードの中でスレッドを作成、管理する際に役立つ便利な方法を提供する、スレッドとスレッドイベント関連の新しいインターフェイスとともに、新たな `nsIThreadManager` インターフェイスを提供します。
- [JavaScript モジュール](/ja/docs/Web/JavaScript/Guide/Modules)
  - : Firefox 3 は、共有ライブラリーのように、拡張機能や ウェブアプリケーションから読み込んで利用できる JavaScript モジュールを簡単に作成できるようにする、新たな共有コードモジュール機構を提供します。
- [`nsIJSON` インターフェイス](/ja/docs/nsIJSON)
  - : Firefox 3 は、[JSON](/ja/docs/Glossary/JSON) 文字列の高パフォーマンスなエンコードとデコードを提供する、新しい `nsIJSON` インターフェイスを提供します。
- `nsIParentalControlsService` インターフェイス
  - : Firefox 3 では、Microsoft Windows Vista の保護者による制限機能がサポートされ、その機能とやり取りするためのコードが使用できるようになります。
- [コンテンツ設定の使用](/ja/docs/Using_content_preferences)
  - : Firefox 3 には、拡張機能およびコアコードが各サイト用のユーザー設定を保存するために利用できる、任意のサイトごとの設定を取得または設定する新しいサービスが含まれています。
- [プラグインモニタリング](/ja/docs/Monitoring_plugins)
  - : プラグインシステムの新しいコンポーネントとして、プラグイン（例えば、Macromedia Flash) がどのくらい実行されているかを調べることができるコンポーネントが利用可能になりました。

#### 修正されたバグ

- [Firefox 3 で修正された主なバグ](/ja/docs/Mozilla/Firefox/Releases/3/Notable_bugs_fixed)
  - : この記事は、Firefox 3 で修正されたバグについての情報を提供します。

## エンドユーザー向け新機能

### ユーザー体験

- **より簡単なパスワード管理** - コンテンツ上部に表示される情報バーを使って、ログインが成功した後にパスワードを保存できるようになりました。
- **簡素化されたアドオンのインストール** - アドオンダウンロードサイトのホワイトリストが削除されたおかげで、サードパーティのダウンロードサイトからも、より少ないクリック回数で拡張機能をインストールできるようになりました。
- **新しいダウンロードマネージャー** - ダウンロードしたファイルを見つけやすくなりました。
- **再開可能なダウンロード** - ブラウザーの再起動後や、ネットワーク接続をリセットした後、ダウンロードを再開できるようになりました。
- **フルページズーム** - ［表示］メニューから、あるいはキーボードショートカットを使って、ページのコンテンツ全体を拡大・縮小できるようになりました。文字だけでなく、レイアウト全体や画像も併せて拡大・縮小できます。
- **タブのスクロールとクイックメニュー** - 新しいタブのスクロールとクイックメニュー機能で、目的のタブをより簡単に探せるようになりました。
- **作業の保存と復元** - Firefox 3 は、終了時に開いているタブの状態を保存するかどうか尋ねるダイアログを表示します。
- **タブを開く動作の最適化** - ブックマークフォルダーをタブに開く際、既存のタブを置き換える代わりに、新しいタブを追加するようになりました。
- **ロケーションバーと検索バーのサイズ調整** - ロケーションバーと検索バーの幅を、間にある小さなリサイズハンドルを使って簡単に変えられるようになりました。
- **文字列選択の改良** - Ctrl キー (Mac では Command キー) を使って、複数の文字列範囲を選択できるようになりました。また、文字列をダブルクリックした後にドラッグを開始すると、単語ごとに選択範囲が拡大・縮小されます。トリプルクリックした場合は段落全体が選択されます。
- **ページ内検索バー** - ページ内検索が、現在の選択範囲から開始されるようになりました。
- **プラグイン管理** - アドオンマネージャーでプラグインを個別に無効化できるようになりました。
- **Windows Vista との統合** - Firefox のメニューが Vista のネイティブテーマで表示されるようになりました。
- **Mac OS X との統合** - ダウンロード完了や更新の通知に [Growl](http://growl.info/) をサポートしました。
- **スターボタン** - ロケーションバーに表示される新しいスターボタンを使って、ワンクリックでブックマークを追加できるようになりました。もう一度クリックすると、その新しいブックマークを指定の場所に保存したり、タグを付けることができます。
- **タグ** - ブックマークにタグを関連付けて、トピックごとに簡単に分類できるようになりました。
- **ロケーションバーの自動補完** - ロケーションバーにページのタイトルやタグを入力するだけで、履歴やブックマークから目的のページをすばやく探し出せるようになりました。お気に入りアイコン、ブックマーク、タグも併せて表示されるので、それぞれの項目がどこから検索されたのかが分かりやすくなっています。
- **スマートブックマークフォルダー** - Firefox の新しい「スマートブックマークフォルダー」から、最近ブックマークしたりタグを付けたページ、あるいはよく訪れるページにすばやくアクセスできます。
- **ブックマークと履歴の整理** - 統合された新しいブックマークと履歴の管理画面では、複数の表示形式や、よく使う検索語を保存できるスマートフォルダーを使って、履歴やブックマークを簡単に検索できます。
- **ウェブベースのプロトコルハンドラー** - ページ上の `mailto:` リンクを開く際、デスクトップアプリケーションの代わりに、お気に入りの ウェブメールサービスなど、ウェブアプリケーションを使えるようになりました。他のプロトコルについても同様のサポートが提供されます。(なお、ウェブアプリケーションを連携させるには、最初にそれらを Firefox に登録する必要があります)
- **より便利になったダウンロードアクション** - 新しい「アプリケーション」設定画面は、様々なファイル形式やプロトコルスキーマの処理方法を設定するための、改良されたユーザーインターフェイスを提供します。
- **ルック＆フィールの改善** - グラフィックとフォント処理が改良され、ウェブページが画面上でより美しく表示されるようになりました。例えば、テキストの描画がよりシャープになり、リガチャや複雑な筆記体活字を含むフォントのサポートも改善されています。さらに、Mac と Linux (Gnome) では、新たなネイティブテーマが採用されたことで、Firefox の見た目がかつてなくネイティブアプリケーションに近づきました。
- **カラーマネジメントのサポート** - `about:config` の設定で `gfx.color_management.enabled` を設定すると、画像に埋め込まれたカラープロファイルを使って、コンピューターの画面に適したカラー調節が行われます。
- **オフラインサポート** - ウェブアプリケーションが、インターネットに接続していないときでも利用できるようにした新機能を活用できるようになりました。

### プライバシーとセキュリティ

- **サイト情報をワンクリックで表示** - 訪れたサイトに関する詳しい情報を知りたいときは、ロケーションバーに表示されるサイトアイコンをクリックすれば、サイトの所有者を確認することができます。識別情報がはっきりと表示され、前より分かりやすくなりました。
- **悪意のあるソフトウェアからの保護** - ウイルス、スパイウェア、トロイの木馬などの危険なソフトウェア (総称してマルウェア＝悪意のあるソフトウェアと呼ばれます) をインストールさせようとすることが知られているサイトを訪れてしまった場合、Firefox 3 は警告を表示します。
- **フィッシング詐欺サイトからの保護の改良** - フィッシング詐欺 (偽装) サイトと思われるページを開いてしまった場合、ページの内容とともに警告が表示されるのではなく、特別なページが表示されるようになりました。
- **より分かりやすくなった SSL エラー** - 不正な SSL 証明書に遭遇したときに表示されるエラーの内容がより明確になり、どのような問題が起きているのか分かりやすくなりました。
- **古いアドオンからの保護** - Firefox 3 は、アドオンやプラグインのバージョンを自動的に確認し、古い安全でないバージョンを無効化します。
- **安全なアドオンの更新** - 安全でない更新方法を用いているアドオンのインストールを禁止することで、アドオンの更新を行う際の安全性が向上しました。
- **ウイルス対策ソフトの統合** - Firefox 3 は、実行可能ファイルをダウンロードした際、ウイルス対策ソフトに通知を行い、即座にスキャンを開始できるようにします。
- **Windows Vista の保護者による制限機能のサポート** - Firefox 3 は、ファイルダウンロードの無効化に、Vista のシステム全体の保護者による制限 (ペアレンタルコントロール) 設定をサポートしました。

### パフォーマンス

- **信頼性** - Firefox 3 は、ブックマーク、履歴、Cookie、個人設定をトランザクション上安全なデータベース形式で保存します。つまり、システムがクラッシュした場合も、プロファイルデータが失われずに済みます。
- **高速化** - Firefox 3 では、画面上の描画処理と、ページレイアウトの処理を行う部分を完全に書き換えることで、パフォーマンスが劇的に向上しました。
- **メモリー使用量の削減** - Firefox 3 では、300 以上のメモリー「リーク」バグの修正に加えて、リークしたメモリーブロックを自動的に特定、処理する新機能によって、メモリー効率が大幅に向上しました。

## 関連記事

{{Firefox_for_developers('2')}}
