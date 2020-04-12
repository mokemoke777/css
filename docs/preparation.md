## 前準備

[docsifyのリポジトリ](https://github.com/docsifyjs/docsify) をcloneして、以下のコマンドをたたく
```
npm install
npm run dev
```

## いろいろ持ってくる

#### docsify.min.js
- 前準備でできたファイル（docsifyトップ/lib/docify.min.js)を`lib/docify.min.js`に配置

#### Themes
- 前準備でできたCSSが格納されているフォルダ（docsifyトップ/thmes)を`lib/themes`に配置
- CSSはminifyしないで使うことにする

#### index.html
- docifyの[Manual initialization](https://docsify.js.org/#/quickstart?id=manual-initialization)のコードをコピー
- configのところとCSS参照しているところは、リポジトリTOPの[index.html](https://github.com/docsifyjs/docsify/blob/develop/index.html)からてきとうにコピー
- docify.min.jsの参照先をローカルファイルに変更
  ```html
  <script src="./lib/docsify.min.js">
  ```
- CSSの参照もコピーローカルファイルに変更

#### docsフォルダ
以下のファイルをdocifyのリポジトリからコピーしてきて適当に編集
- README.md
- _sidebar.md

#### buildできるようにする
- buildフォルダ
  css.jsだけコピー
- src/thmesフォルダを構成保ってコピー
- npm install
  ```
  npm install --save-dev autoprefixer-stylus
  npm install --save-dev stylus
  ```
- npm scripts
  package.jsonに以下追加
  ```json
  "scripts": {
    "css": "node build/css",
    "watch:css": "npm run css -- -o lib/themes -w"
  },
  ```

#### ためしにつくってみる
- memo.styl
 dark.stylをコピーして名前変更
 適当に編集
 index.htmlのCSS参照先も変更