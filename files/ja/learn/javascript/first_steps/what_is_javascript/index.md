---
title: JavaScript とは
slug: Learn/JavaScript/First_steps/What_is_JavaScript
tags:
  - 3rd party
  - API
  - Article
  - Beginner
  - Browser
  - CodingScripting
  - Core
  - JavaScript
  - Learn
  - Script
  - comments
  - external
  - inline
  - l10n:priority
  - what
translation_of: Learn/JavaScript/First_steps/What_is_JavaScript
---
{{LearnSidebar}}{{NextMenu("Learn/JavaScript/First_steps/A_first_splash", "Learn/JavaScript/First_steps")}}

MDN 初心者向け JavaScript コースへようこそ！ この最初の記事では、高水準から JavaScript を見ていき、「JavaScript とは何か？」「これを使うと何ができるか？」などの質問に答えます。JavaScript の用途にきっちりと親しめるようになります。

| 前提知識: | 基本的なコンピューターリテラシー、HTML および CSS の基本的な理解。                      |
| --------- | --------------------------------------------------------------------------------------- |
| 到達目標: | JavaScript とは何か、何ができるか、どのようにウェブサイトに適用できるかについて親しむ。 |

## 高水準の定義

JavaScript はウェブページにて複雑な機能をできるようにするプログラミング言語です —ウェブページが読み込まれるたびに、単にあなたが見ている静的な情報を表示する以上のことをしています— 更新されたコンテンツの定期表示や、インタラクティブな地図や、2D/3D グラフィックのアニメーションや、ビデオジュークボックスのスクロールなど — たぶん JavaScript が組み込まれています。ウェブ技術をケーキだとするとこれは 3 つ目の層で、他の 2 つ ([HTML](/ja/docs/Learn/HTML) と [CSS](/ja/docs/Learn/CSS)) は学習エリアの他の部分でもっと詳しく扱ってきました。

![](https://mdn.mozillademos.org/files/13502/cake.png)

- {{glossary("HTML")}} はマークアップ言語で、これを使ってウェブコンテンツに構造と意味を与えます。例えば段落や見出しや表を定義したり、ページに画像や動画を入れたりします。
- {{glossary("CSS")}} は HTML コンテンツに適用するスタイリング規則の言語です。例えば背景とフォントの色を設定したり、複数カラムにコンテンツをレイアウトしたりします。
- {{glossary("JavaScript")}} は動的にコンテンツを更新したり、マルチメディアを管理したり、その他多くのことができるスクリプト言語です。(ええ、すべてできるわけではないですが、JavaScript の数行でできることは素晴らしいです。)

この 3 層は素晴らしい構成です。例としてシンプルなテキストラベルを見てみます。HTML を使って構造と意図をマークアップできます:

```html
<p>Player 1: Chris</p>
```

![](https://mdn.mozillademos.org/files/13422/just-html.png)

次に、CSS を加えて、見栄えをよくします:

```css
p {
  font-family: 'helvetica neue', helvetica, sans-serif;
  letter-spacing: 1px;
  text-transform: uppercase;
  text-align: center;
  border: 2px solid rgba(0,0,200,0.6);
  background: rgba(0,0,200,0.3);
  color: rgba(0,0,200,0.6);
  box-shadow: 1px 1px 2px rgba(0,0,200,0.4);
  border-radius: 10px;
  padding: 3px 10px;
  display: inline-block;
  cursor: pointer;
}
```

![](https://mdn.mozillademos.org/files/13424/html-and-css.png)

最後に、JavaScript を加えて動的なふるまいを実装します:

```js
const para = document.querySelector('p');

para.addEventListener('click', updateName);

function updateName() {
  let name = prompt('名前を入力して下さい');
  para.textContent = 'Player 1: ' + name;
}
```

{{ EmbedLiveSample('A_high-level_definition', '100%', 80, "", "", "hide-codepen-jsfiddle") }}

テキストラベルの最新バージョンをクリックしてみて、何が起きるのか見てみます (このデモは GitHub でも見られます— [ソースコード](https://github.com/mdn/learning-area/blob/master/javascript/introduction-to-js-1/what-is-js/javascript-label.html)または[ライブ実行](http://mdn.github.io/learning-area/javascript/introduction-to-js-1/what-is-js/javascript-label.html)を参照してください)。

JavaScript はそれ以上のことができます — もっと詳しく見てみましょう。

## 実際に何ができるのか

JavaScript は次のことを実現する一般的なプログラミング機能で構成されています。

- 有用な値を変数に格納する。上の例では、ユーザーに新しい名前を問いかけて、`name` と名付けられた変数に入力された新しい名前を格納しています。
- 連なった文字 (プログラミングでは「文字列」と呼ばれます) に対する操作。上の例では「Player 1: 」という文字列と `name` 変数を繋げて「Player 1: Chris」というような新しいラベルを生成しています。
- ウェブページで起きる事柄に対処する。先ほどの例では {{Event("click")}} イベントを使用して、ボタンがクリックされたことを検出し、ラベルを更新するコードを実行しました。
- 他にもたくさんのことができます！

さらにワクワクするのは、JavaScript からすぐに使えるように構築されている機能です。それは **Application Programming Interface** (**API**) と呼ばれ、JavaScript のコードにさらなる強力な力を与えてくれることでしょう。

API がなければ難しかったり、不可能であるようなコードを、すぐに使えるブロックのように、開発者がプログラムを作ることを可能にします。家を作るときの既製の家具と同じことを、プログラミングでしてくれるのです。自分で設計し、使用する木材を選定し、正しい形で板を切り出して、正しいサイズのネジを見つけて、自分で組み立てるよりも、既に切り出されたボードとネジを使って本棚を組み立てるだけの方がずっと簡単ですよね。

API は大まかに 2 種類に分けられます。

![](https://mdn.mozillademos.org/files/13508/browser.png)

**ブラウザー API** はウェブブラウザーに組み込まれていて、コンピューターを取り巻く環境からデータを取り出したり、複雑で便利なことをしてくれたりします。例えば、

- {{domxref("Document_Object_Model","DOM (Document Object Model) API")}} は HTML と CSS の操作を可能とします。HTML を生成し、削除し、変更し、動的にページの見た目を変更することなどが可能です。もし (先ほどの簡単な例で見たように) ページ内でポップアップウィンドウを見たり、新しいコンテンツが表示されたりしたのなら、DOM が使用されていることでしょう。
- {{domxref("Geolocation","Geolocation API")}} は地理的な情報を取得します。これは [Google マップ](https://www.google.com/maps)があなたの所在地を見つけて地図上にプロットする場合に使用されています。
- {{domxref("Canvas_API","Canvas")}} と {{domxref("WebGL_API","WebGL")}} の API は 2D や 3D グラフィックでのアニメーションを可能とします。このウェブ技術を使用してすごいことをやってのける人たちがいます。[Chrome Experiments](https://www.chromeexperiments.com/webgl) や [webglsamples](http://webglsamples.org/) などのページを見てください。
- [音声と動画の API](/ja/Apps/Fundamentals/Audio_and_video_delivery)、たとえば {{domxref("HTMLMediaElement")}} や {{domxref("WebRTC API", "WebRTC")}} などは適切な音声・動画をウェブページで再生することや、ウェブカメラの動画を撮って他の人のコンピューターで流すといった、マルチメディアの可能性を示してくれます (我々が作った[ Snapshot demo](http://chrisdavidmills.github.io/snapshot/) を見てみてください)。

> **Note:** **注**: 上記の多くは古いブラウザーでは動作しません。試すには Firefox、Chrome、Edge、Opera といったモダンなブラウザーを使うのがよいでしょう。プロダクションコードを提供する (顧客に実際のコードを納品する) 段になったら、[クロスブラウザーテスト](/ja/docs/Learn/Tools_and_testing/Cross_browser_testing)を読んでみるとよいでしょう。

**サードパーティ API** はブラウザーには組み込まれておらず、さらに普通はウェブ上のどこかからそのコードと情報を探さなければなりません。例えば、

- [Twitter API](https://dev.twitter.com/overview/documentation) を使用して、ウェブサイトに最新のツイートを表示させることができます。
- [Google マップ API](https://developers.google.com/maps/) と [OpenStreetMap API](https://wiki.openstreetmap.org/wiki/API) を使用して、ウェブサイトに専用の地図を埋め込み、付加機能を付けることもできます。

> **Note:** **注**: このような API は先進的ですが、このモジュールでは扱いません。詳しく知りたければ [Client-side web APIs module](/ja/docs/Learn/JavaScript/Client-side_web_APIs) で扱っています。

ワクワクすることはもっとたくさんあります！ ですが、まだ興奮しすぎないでください。24 時間程度の勉強だけでは、Facebook や Google マップや Instagram は作れません。まずはやらなければならない基本がたくさんあるのです。さあ、先に進みましょう！

## JavaScript は何をするのか

まずは実際にコードを見てみましょう。そしてページで JavaScript を動かすと何が起きるのか見てみましょう。

ブラウザーをウェブページに読み込んだときの話を簡単に説明します ([How CSS works](/ja/Learn/CSS/Introduction_to_CSS/How_CSS_works#How_does_CSS_actually_work) の記事で最初に出てきました)。ウェブページをブラウザーで見たとき、実行環境 (ブラウザーのタブ) の中で、コード (HTML、CSS そして JavaScript) が実行されます。これは素材 (コード) を加工して製品 (ウェブページ) を出力する工場のようなものです。

![](https://mdn.mozillademos.org/files/13504/execution.png)

JavaScript のごく一般的な用途は、(先ほど例示した) Document Object Model API を介して動的に HTML と CSS を変更し、ユーザーインターフェイスを更新することです。なお、ウェブドキュメント上のコードは通常、ページ上に現れる順序で読み込まれて実行されます。もし JavaScript がロードされ、影響を受ける HTML および CSS がロードされる前に実行しようとすると、エラーが発生する可能性があります。この回避策については、記事の後半の「[スクリプトの読み込み方針](/ja/docs/Learn/JavaScript/First_steps/What_is_JavaScript#Script_loading_strategies)」セクションで学習します。

### ブラウザーのセキュリティ

ブラウザーのそれぞれのタブは、コードを実行するための入れ物を個別に持ちます (この入れ物を技術的用語では「実行環境」と呼びます)。つまり、それぞれのタブ内でコードは完全に分かれて実行されており、あるタブで動いているコードは他のタブや他のウェブサイトのコードに、直接的には干渉できません。これは良いセキュリティ対策です。互いに干渉することが出来てしまえば、ウェブの悪党たちは、他のタブで開いているウェブサイトから情報を盗み出したり、もっとひどいことをするためにコードを書き始めることでしょう。

> **Note:** **注**: 他のウェブサイトや、タブに安全にデータや実行可能なコードを送る方法はあります。けれども、このコースでは扱わない高度な技術です。

### JavaScript の実行順序

ブラウザーが JavaScript のブロックを見つけたとき、たいていは先頭から最後に向かって順番に実行されます。つまりどの順番で実行されるかということに気を配らなければなりません。例えば、最初の例で見た　 JavaScript のブロックに戻りましょう。

```js
const para = document.querySelector('p');

para.addEventListener('click', updateName);

function updateName() {
  let name = prompt('名前を入力して下さい');
  para.textContent = 'Player 1: ' + name;
}
```

このコードでは文章段落を選択して (1 行目)、イベントリスナーを登録して (3 行目) 段落がクリックされたとき、`updateName()` というコードブロック (5 行目から 8 行目) が実行されるようにしています。`updateName()` というコードブロック (再利用可能なコードブロックで「関数」と呼びます) は、ユーザーに新しい名前を尋ねて、表示内容を変更するため、段落にその名前を挿入します。

もし、最初の 2 行を入れ替えた場合、動かなくなってしまいます。代わりに[ブラウザーの開発者コンソール](/ja/docs/Learn/Common_questions/What_are_browser_developer_tools)に `TypeError: para is undefined` というエラーが出るでしょう。この意味は `para` オブジェクトがまだ存在しないため、イベントリスナーを設定できないということを表しています。

> **Note:** **注**: これはとてもよくあるエラーです。オブジェクトに対して何かをする前にはそのオブジェクトへの参照が存在していることに気を配らなければなりません。

### インタープリターとコンパイルコード

もしかしたら、**インタープリター**と**コンパイル**という用語をプログラミングの文脈で聞いたことがあるかもしれませんね。インタープリターでは、コードが上から下に実行されてコードの実行結果がすぐに返ってきます。ブラウザーが実行する前にコードを何らかの形に変換する必要はありません。コードはプログラマーに親しみやすいテキストで受け取って、それから直接処理されます。

反対に、コンパイル言語はコンピューターで実行する前に他の形式に変換 (コンパイル) しなければなりません。例えば C/C++ は機械語にコンパイルされてから、コンピューターで実行されます。プログラムは、元のプログラムソースコードから生成されるバイナリーフォーマットで実行されます。

JavaScript は軽量なインタープリター型プログラミング言語です。ウェブブラウザーは元のテキストの形で JavaScript コードを受け取り、それからスクリプトを実行します。技術的な見地からは、たいていの JavaScript インタープリターは **just-in-time compiling** というテクニックを使ってパフォーマンスを向上させています; スクリプトが使われるときに、JavaScript コードが速いバイナリーフォーマットにコンパイルされて、可能な限り高速に実行されます。しかし、JavaScript は、事前ではなく実行時にコンパイルされるために、インタープリター言語と考えられています。

ここで詳細は話しませんが、どちらの方式も長所と短所があります。

### サーバーサイドコードとクライアントサイドコード

**サーバーサイド**と**クライアントサイド**という言葉も聞いたことがあるかもしれません。特にウェブ開発でよく聞かれます。クライアントサイドコードはユーザーのコンピューター上で実行されるコードです。ウェブページを見ているとき、ページのクライアントサイドコードがダウンロードされて、ブラウザーで実行されて表示されます。この JavaScript モジュールのことを明示的に**クライアントサイド JavaScript** と言います。

反対に、サーバーサイドコードはサーバー上で実行され、結果がブラウザーにダウンロードされて表示されます。ウェブで人気のあるサーバーサイドの言語は、PHP、Python、Ruby や ASP.NET など。そして JavaScript です！ JavaScript はサーバーサイドの言語としても使われます。人気のある Node.js 環境がその例です。サーバーサイドの JavaScript については [Dynamic Websites – Server-side programming](/ja/docs/Learn/Server-side) のトピックを見てください。

### 動的コードと静的コード

クライアントサイドの JavaScript と、サーバーサイドの言語を説明するのに**動的**という言葉を使います。これはウェブページやウェブアプリが必要に応じてコンテンツを生成し、異なる状況において異なる表示ができるという能力を指しています。サーバーサイドのコードは、データベースからデータを取得して動的にコンテンツを生成します。一方、クライアントサイドの JavaScript はクライアント上のブラウザーで HTML のテーブルを生成したり、そのテーブルにサーバーから指示を受け、データを追加したり、ウェブページ上でユーザーにテーブルを表示したりするなどして、動的にコンテンツを生成します。それぞれの文脈で、少し異なる意味合いではありますが、関連しています。そしてどちらの方式も (サーバーサイドもクライアントサイドも) たいていは同時に使用されます。

動的に更新されるコンテンツを含まないウェブページは**静的**と表現されます。静的なウェブページとは常に同じコンテンツを表示するページのことです。

## ページに JavaScript を追加する方法

JavaScript は CSS と同じような方法で、HTML ページに適用することができます。CSS では {{htmlelement("link")}} 要素を使用することで外部のスタイルシートを適用することができ、また、{{htmlelement("style")}} 要素を使用することで HTML 内部に書かれたスタイルシートを適用することが出来ました。しかし、JavaScript で HTML に書く必要があるのは {{htmlelement("script")}} 要素だけです。どのように書くのか見てみましょう。

### 内部の JavaScript

1.  まずは [apply-javascript.html](https://github.com/mdn/learning-area/blob/master/javascript/introduction-to-js-1/what-is-js/apply-javascript.html) ファイルを自分のコンピューターにコピーします。どこか適当な場所に保存してください。
2.  テキストエディターとウェブブラウザーでそのファイルを開いてください。クリックできるボタンが 1 つあるウェブページを作る HTML だということがわかりますね。
3.  次に、テキストエディターで `</head>` タグの直前に以下のコードを追加します。

    ```html
    <script>

      // JavaScript をここに書きます

    </script>
    ```

4.  それでは {{htmlelement("script")}} 要素内に JavaScript を書いて、もうちょっと面白いことをしてみましょう。「// JavaScript をここに書きます」と書いてあるすぐ下に、以下のコードを追加してください。

    ```js
    document.addEventListener("DOMContentLoaded", function() {
      function createParagraph() {
        let para = document.createElement('p');
        para.textContent = 'ボタンが押されました!';
        document.body.appendChild(para);
      }

      const buttons = document.querySelectorAll('button');

      for(let i = 0; i < buttons.length ; i++) {
        buttons[i].addEventListener('click', createParagraph);
      }
    });
    ```

5.  ファイルを保存してブラウザーを更新してください。ボタンを押す度に新しい段落が作られて、下に表示されるようになりましたね。

> **Note:** **注**: もし上記の例が上手く動いていないとしたら、もう一度最初から手順を確認してください。コピーしてコードを書いたファイルは `.html` というファイル名ですか？ {{htmlelement("script")}} 要素を `</head>` タグの直前に追加しましたか？ JavaScript を上の例の通りに書きましたか？ **JavaScript は大文字小文字を区別しますので、見えている通りに書かなければなりません。正しく書いていなければ、動いてくれません。**文字化けしているなら、テキストエディターの文字エンコーディングの設定が UTF-8 になっていることを確認してください。

> **Note:** **注**: GitHub にあるこちらのバージョン、[apply-javascript-internal.html](https://github.com/mdn/learning-area/blob/master/javascript/introduction-to-js-1/what-is-js/apply-javascript-internal.html) ([動くバージョンもあります](http://mdn.github.io/learning-area/javascript/introduction-to-js-1/what-is-js/apply-javascript-internal.html)) を見ることもできます。

### 外部の JavaScript

これで JavaScript が動きましたね。しかし、JavaScript を外部のファイルに書きたいときはどうすればよいでしょうか？ 次の例を見てみましょう。

1.  まず、先ほどの HTML ファイルと同じディレクトリーに新しいファイルを作ります。これを `script.js` と名付けます。.js という拡張子であることを確認してください。それで JavaScript であると認識されるのです。
2.  {{htmlelement("script")}} 要素を以下のコードで置き換えます。

    ```html
    <script src="script.js" defer></script>
    ```

3.  `script.js` に、次のスクリプトを追加します。

    ```js
    function createParagraph() {
      let para = document.createElement('p');
      para.textContent = 'ボタンが押されました!';
      document.body.appendChild(para);
    }

    const buttons = document.querySelectorAll('button');

    for(let i = 0; i < buttons.length ; i++) {
      buttons[i].addEventListener('click', createParagraph);
    }
    ```

4.  HTML ファイルを保存して、ブラウザーを更新してください。同じページが見えますね！ 同じように動いていますが、今回は外部の JavaScript ファイルです。コードを整理して、複数の HTML ファイルから再利用できるようにするには、このようにするのが良いでしょう。大きなスクリプトの塊がないほうが、HTML も読みやすくなります。

> **Note:** **注**: GitHub でこちらのバージョンも見られます。[apply-javascript-external.html](https://github.com/mdn/learning-area/blob/master/javascript/introduction-to-js-1/what-is-js/apply-javascript-external.html) と [script.js](https://github.com/mdn/learning-area/blob/master/javascript/introduction-to-js-1/what-is-js/script.js) です ([動いているバージョンもあります](http://mdn.github.io/learning-area/javascript/introduction-to-js-1/what-is-js/apply-javascript-external.html))。

### インラインの JavaScript ハンドラー

たまに JavaScript のコードが HTML の途中に書かれているのを見かけます。こんな感じで。

```js example-bad
function createParagraph() {
  let para = document.createElement('p');
  para.textContent = 'ボタンが押されました！';
  document.body.appendChild(para);
}
```

```html example-bad
<button onclick="createParagraph()">押してください</button>
```

このバージョンのデモを下のボタンを押して確認してください。

{{ EmbedLiveSample('inline_js_example', '100%', 150, "", "", "hide-codepen-jsfiddle") }}

このデモは先ほどのセクションのものと同じ機能を持っていますが、{{htmlelement("button")}} 要素に `onclick` 属性を付けてボタンが押されたときに関数が実行されるようにハンドラーを直接書いています。

**書けはしますが、このようにはしないでください。**この書き方は HTML を JavaScript で汚してしまう悪い書き方です。さらに、`onclick="createParagraph()"` という属性を JavaScript を適用したいボタンすべてに書かなければなりませんので、とても非効率です。

純粋な JavaScript では、1 つの命令ですべてのボタンが取得できます。先ほど使用した、すべてのボタンを取得するためのコードは以下の通りでした。

```js
const buttons = document.querySelectorAll('button');

for(let i = 0; i < buttons.length ; i++) {
  buttons[i].addEventListener('click', createParagraph);
}
```

これは `onclick` 属性を用いて書くより少し長いように見えますが、どれだけそのページにボタンを追加し、削除し、いくつあろうとも期待通りに動くでしょう。コードを変更することなく。

> **Note:** **注**: 自分の `apply-javascript.html` ファイルを編集して、いくつかボタンを追加してみて下さい。再度読み込むとどのボタンを押しても段落が作られるのがわかるでしょう。素敵でしょ！

### スクリプトの読み込み方針

スクリプトを適切なタイミングで読み込むためには、いくつかの問題があります。 それは見掛けほど簡単ではありません！ 一般的な問題は、ページ上のすべての HTML が、現れた順に読み込まれることです。JavaScript を使用してページ上の要素（またはより正確には、[Document Object Model](/ja/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents#The_document_object_model)）を操作している場合、何かをしようとする HTML の前に JavaScript が読み込まれ、解析されてもコードは機能しません。

上のコード例では、内部の例と外部の例は、HTML 本文が解析される前に JavaScript が読み込まれて文書の head で実行されています。これによりエラーが発生する可能性があるため、いくつかの構文を使用して回避しています。

内部の例では、コードの周りにこの構造を見ることができます。

```js
document.addEventListener("DOMContentLoaded", function() {
  ...
});
```

これはブラウザーの "DOMContentLoaded" イベントをリッスンするイベントリスナーで、HTML body が完全に読み込まれて解析されたことを示します。このブロック内の JavaScript はそのイベントが発生するまで実行されないため、エラーは回避されます (コースの後半で[イベントについて学習](/ja/docs/Learn/JavaScript/Building_blocks/Events)します) 。

外部の例では、より現代的な JavaScript 機能の `defer` 属性を使用して問題を解決し、`<script>` 要素に達した後も HTML コンテンツのダウンロードを続行するようブラウザーに指示します。

```js
<script src="script.js" defer></script>
```

この場合、スクリプトと HTML の両方が同時に読み込まれ、コードが機能します。

> **Note:** **注**: 外部のケースでは、`defer` 属性が問題を解決したため、`DOMContentLoaded` イベントを使用する必要はありませんでした。`defer` は外部スクリプトに対してのみ機能するため、内部の例では `defer` による解決策を使用しませんでした。

この問題に対する昔ながらの解決策は、すべての HTML が解析された後に読み込まれるように、body の下部に（たとえば `</body>` タグの直前に）script 要素を置くことでした。この解決策（および上記の `DOMContentLoaded` による解決策）の問題点は、HTML DOM が読み込まれるまでスクリプトの読み込みと解析が完全にブロックされることです。JavaScript がたくさんある大規模なサイトでは、これは大きなパフォーマンス上の問題を引き起こす可能性があり、サイトを遅くします。

#### async と defer

実際には、スクリプトのブロッキングの問題を回避できるモダンな機能が 2 つあります — `async` と `defer`(すでに見てきました)。これらの 2 つの違いを見てみましょう。

`async` 属性を使って読み込むスクリプトは(下記を見てください)、ページのレンダリングをブロックせずにスクリプトをダウンロードし、スクリプトのダウンロードが終了すると直ちに実行します。複数のスクリプトが特定の順序で実行されるという保証はありませんが、ページの残りの部分の表示を停止することはありません。ページ内のスクリプトが互いに独立して実行され、ページ上の他のスクリプトに依存しない場合は、`async` を使用することをお勧めします。

たとえば、次のスクリプト要素があるとします。

```html
<script async src="js/vendor/jquery.js"></script>

<script async src="js/script2.js"></script>

<script async src="js/script3.js"></script>
```

スクリプトが読み込まれる順序に依存することはできません。`jquery.js` は `script2.js` と `script3.js` に前後して読み込まれます。この場合、`jquery` に依存するこれらのスクリプトの関数は、スクリプトの実行時に `jquery` が定義されないため、エラーを生成します。

読み込むバックグラウンドスクリプトがいくつもあって、それらをできるだけ早く実行したい場合に `async` を使用するべきです。例えば、ゲームを実際に開始するときに必要になるいくつかのロードすべきゲームデータファイルがあるとして、今のところは、スクリプトのロードによってブロックされずに、ゲームのイントロ、タイトル、ロビーを表示したいだけ、という場合です。

`defer` 属性つきのスクリプト(下記のようなもの)は、ページに現れた順序でスクリプトを実行し、スクリプトとコンテンツがダウンロードされるとすぐにスクリプトを実行します。

```html
<script defer src="js/vendor/jquery.js"></script>

<script defer src="js/script2.js"></script>

<script defer src="js/script3.js"></script>
```

`defer` 属性を持つすべてのスクリプトは、ページに現れた順序で読み込まれます。したがって、2 番目の例では、`jquery.js` が `script2.js` と `script3.js` の前に読み込まれ、`script2.js` が `script3.js` の前に読み込まれることは確実です。ページコンテンツがすべて読み込まれるまでは、実行せず、これはスクリプトが DOM 配置に依存している場合に便利です(例: ページの要素を変更する場合)

要約すると、

- `async` と `defer` の両方とも、ページのその他の部分 (DOM など) がダウンロード中な時でも、ブラウザーにスクリプトを別々のスレッドでダウンロードするよう指示して、このためページ読み込みはスクリプトでブロックされません。
- 依存関係なしでスクリプトを単独ですぐに実行できる場合は、`async` を使用します。
- スクリプトが他のスクリプトや DOM 配置に依存している場合は、`defer` を使用してスクリプトを読み込み、対応する `<script>` 要素をブラウザーで実行して欲しい順序で配置します。

## コメント

HTML や CSS と同様に、JavaScript でもコード内にブラウザーが実行しない「コメント」を書くことができます。仲間の開発者 (または、6 カ月後のコードを忘れた自分自身) に対して動作方法を書くことができます。コメントはとても便利ですしたくさん書きましょう。大きなプログラムを書くのならなおのことです。コメントの書き方は 2 種類あります。

- 1 行で収まるコメントは 2 つのスラッシュ (//) のあとに続けて書きます。

  ```js
  // これはコメントです
  ```

- 複数行に渡るコメントは /\* から \*/ の間に書きます。

  ```js
  /*
    これも
    コメントです
  */
  ```

先ほどのデモでコメントを書くならば、以下のようにします。

```js
// 関数: HTML の body タグ内の一番下に新しい段落を追加します。

function createParagraph() {
  let para = document.createElement('p');
  para.textContent = 'ボタンが押されました！';
  document.body.appendChild(para);
}

/*
  1. ページ内のボタンへの参照をすべて取り出して配列に入れる。
  2. すべてのボタンをループで回し、クリックイベントのリスナーを追加する

  どのボタンが押されても、createParagraph() 関数が実行されるようにする。
*/

const buttons = document.querySelectorAll('button');

for (let i = 0; i < buttons.length ; i++) {
  buttons[i].addEventListener('click', createParagraph);
}
```

> **Note:** **メモ**: 一般的にコメントは多いほうが少ないよりも優れていますが、変数が何であるかを説明する (変数名はおそらくもっと直感的にするべきです) ため、または非常に単純な操作を説明する (コードが複雑すぎるかもしれません) ために、多くのコメントを追加する場合は注意が必要です。

## まとめ

さて、JavaScript の世界に足を踏み入れましたね。なぜ JavaScript を使い、何ができるのかということに慣れるため、まずは理論から始めました。進むにつれ、少しでしたが例を見て、何よりも JavaScript がどのようにウェブサイトの他のコードに組み込まれているかを学習しました。

JavaScript が少し大変だと思いましたか。でも心配は無用です。このコースを受講することで一歩ずつ、理解しながら前に進んで行きましょう。次の記事で、まっすぐに飛び込んで自分で JavaScript のページを作って[実践に飛び込んでいきましょう](/ja/docs/Learn/JavaScript/First_steps/A_first_splash)。

{{NextMenu("Learn/JavaScript/First_steps/A_first_splash", "Learn/JavaScript/First_steps")}}

## このモジュール

- [JavaScript とは](/ja/docs/Learn/JavaScript/First_steps/What_is_JavaScript)
- [JavaScript への最初のダイブ](/ja/docs/Learn/JavaScript/First_steps/A_first_splash)
- [何が間違っている? JavaScript のトラブルシューティング](/ja/docs/Learn/JavaScript/First_steps/What_went_wrong)
- [必要な情報を保存する — 変数](/ja/docs/Learn/JavaScript/First_steps/Variables)
- [JavaScript での演算の基本 — 数値と演算子について](/ja/docs/Learn/JavaScript/First_steps/Math)
- [テキストを扱う — JavaScript での文字列](/ja/docs/Learn/JavaScript/First_steps/Strings)
- [便利な文字列メソッド](/ja/docs/Learn/JavaScript/First_steps/Useful_string_methods)
- [配列](/ja/docs/Learn/JavaScript/First_steps/Arrays)
- [評価: バカ話ジェネレーター](/ja/docs/Learn/JavaScript/First_steps/Silly_story_generator)