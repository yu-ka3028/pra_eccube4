# ボタンのホバー設定 [2 系]()

## 調査

- 今回はこのボタンで調査した
  ec-cube/src/Eccube/Resource/template/default/Product/list.twig
  ```php
  <div class="ec-productRole__btn">
    <button type="submit" class="ec-blockBtn--action add-cart" data-cartid="{{ Product.id }}" form="productForm{{ Product.id }}">
        {{ 'front.product.add_cart'|trans }}
    </button>
  </div>
  ```
- 該当ファイル：ec-cube/html/template/default/assets/css/style.css
  - ブラウザの検証ツールでブタンを選択し該当ファイル探す
  - もちろん grep でも OK`grep -rl "class名" ./`
- 用意する画像：4系はCSSなのでなし
- 今回のボタン設定部分のコード抜き出し
```php
/*
ブロックボタン（全幅）

ボタンサイズは em で指定するため、テキストサイズの変更でボタンサイズを変更できます。

ex [商品詳細ページ　カートボタン部分](http://demo3.ec-cube.net/products/detail/30)

Markup:
p: .ec-blockBtn 住所検索
p: .ec-blockBtn--primary もっと見る
p: .ec-blockBtn--action カートに入れる
p: .ec-blockBtn--cancel キャンセル

Styleguide 2.1.2
*/
.ec-blockBtn--action {
  display: inline-block;
  margin-bottom: 0;
  font-weight: bold;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  --bs-btn-padding-y: 6px;
  --bs-btn-padding-x: 12px;
  --bs-btn-font-size: 0.875rem;
  --bs-btn-border-radius: 1.42857142;
  -webkit-user-select: none;
  -moz-user-select: none;
  user-select: none;
  padding: 10px 16px;
  text-decoration: none;
  color: #fff;
  background-color: #DE5D50;
  border-color: #DE5D50;
  display: block;
  width: 100%;
  height: 56px;
  line-height: 56px;
  padding-top: 0;
  padding-bottom: 0;
}

.ec-blockBtn--action:hover {
  color: #fff;
  background-color: #bd4f44;
  border-color: #b24a40;
}
```

