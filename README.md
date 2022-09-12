# HTMLとCSSだけで機能するコンタクトフォームの作成

[作成したデモサイトはこちら](https://taku-web3.com/project/contact-form/index.html)

## ■改めて学んだこと
- フォームを作るときはformで囲うことでデータのやりとりができる
- static formsの使い方
- labelとinputの関係
- コンテンツを中央寄せにする方法
- labelとinputはfloat: left;で引き離す
- inputの入力欄はpaddingで広げる
- textareaはheightとwidthを使う
- inputを使ったボタン


## グーグルフォントの読み込み
```css
@import url("https://fonts.googleapis.com/css2?family=M+PLUS+Rounded+1c:wght@300;400;500;700&display=swap");

* {
  font-family: "M PLUS Rounded 1c", sans-serif;
}
```

## コンテンツを中央寄せ
```css
body {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
```


## labelとinputの位置を調節する
```css
.label {
  float: left;
  margin-right: 25px;
  width: 135px;
}
.inputs {
  width: 250px;
  float: left;
}
```

## inputを使ったボタン
```html
<input type="submit" value="予約決定">
<!-- リセットできる機能 -->
<input type="reset" value="リセット">
```

## static formsについて
サーバー側のコードなしでHTMLフォームを統合することができる。
※セキュリティは脆弱なので本番環境ではあまり使えない。

[static forms](https://www.staticforms.xyz/)

```html
　　　<!-- APIのURL -->
    <form action="https://api.staticforms.xyz/submit" method="post">
      <!-- これは絶対に必要 -->
        <input type="hidden" name="accessKey" value="ここにアクセストークン"> <!-- Required -->

        <input type="text" name="name"> 
        <input type="text" name="subject"> 
        <input type="text" name="email"> 
        <input type="text" name="phone"> 
        <textarea name="message"></textarea> 

        <input type="text" name="replyTo" value="myreplytoemail@example.com"> <!-- Optional -->
        <input type="hidden" name="replyTo" value="@"> <!-- Optional -->
        <input type="hidden" name="redirectTo" value="https://example.com/contact/success"> <!-- Optional -->
        <input type="submit" value="Submit" />
    </form>
```