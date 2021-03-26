# 基礎から学ぶVue.js

書籍のメモ

## チャプタ 1

### §1

- フレームワークの使用理由
一つとして「設計」を考えなくていいこと
- フレームワークとライブラリ
  - ライブラリ: 使われる側
  - フレームワーク: 使う側

### §2

- データ駆動
  - VueはDOMではなくJSのデータを主体にする
- ディレクティブ
  - `v-if` みたいなVue独自のhtmlに突っ込む属性
- データバインディング
  - 描画とデータの同期
- テンプレート
  - #app にVueの要素をあてがう = マウント mount
- v- ディレクティブ
  - v-bind :value .sync = "message"
  - ディレクティブ, 引数, 修飾子, 式(ふつうにJSの式)
- コンポーネント指向 (template, css, js)

### §3

- リソースの活用
  - ElementUI
  - OnsenUI

### §4

Vueがelementを探せるように body の最後に置く、ないし以下のようにDOMを読み込んでからにする

```
document.addEventListener('DOMContentLoaded', ()=>{ window.app = new Vue()});
```

### §5

- 基本のデータバインディングなど
- 先出しサンプル

### §6

- Vueインスタンス内の各オプション
- フック = 決まったタイミングでの処理の割り込ませ
- ライフサイクルフック : created - インスタンス生成後すぐ、など

- §末尾にライフサイクルフック用のメソッド + ライフサイクルのダイヤグラムあり

## チャプタ 2

### §7

- リアクティブシステム ⊃ データバインディング
- dataのリアクティブな値はあとから定義できないので、予めある程度型を合わせてdataに定義しておく

### §8

- mustache {{ }}
  - mustache内は `式`
    - これは文 `var two = 1 + 1`
    - これは式 `1 + 1`
- htmlの属性にはmustacheは使用不可
  - ディレクティブを使用
  - v-bindの例 {{ message }} ではなく
    - v-bind:value="message"
    - 同上 :value="message"
  - 修飾子も活用 (例 prop: DOMのプロパティに直でバインドできる)
    - v-bind:text-content.prop="message"
    - text-contentはこのあたり参照: https://developer.mozilla.org/ja/docs/Web/API/Node/textContent

- dataの状態のデバッグ これでjsonで吐き出される
```
<pre>{{ $data }}</pre>
```

