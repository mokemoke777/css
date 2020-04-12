## searchプラグイン

### JSのコピー
前準備で作ったファイルから`\lib\plugins\search.min.js`をフォルダ構成たもったままコピー

### index.htmlに追加

```html
<script src="./lib/plugins/search.min.js"></script>
```

## htmlに埋め込むやつ

index.htmlのコンフィグに追加
docifyリポジトリ直下のindex.htmlからコピーしてurlだけ修正
```javascript
      plugins: [
        function (hook, vm) {
          hook.beforeEach(function (html) {
            if (/githubusercontent\.com/.test(vm.route.file)) {
              url = vm.route.file
                .replace('raw.githubusercontent.com', 'github.com')
                .replace(/\/master/, '/blob/master')
            } else {
              url = 'https://github.com/cocoakamen/memo-docsify/blob/master/docs/' + vm.route.file
            }
            var editHtml = '[:memo: Edit Document](' + url + ')\n'

            return editHtml
              + html
              + '\n\n----\n\n'
              + '<a href="https://docsify.js.org" target="_blank" style="color: inherit; font-weight: normal; text-decoration: none;">Powered by docsify</a>'
          })
        },
      ]
```