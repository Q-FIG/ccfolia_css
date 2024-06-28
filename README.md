# OBSで使用するCSS集

## 基本的な使い方

1. OBSの「ソース>ブラウザ」を追加
2. 「URL」にココフォリアのURLを追加
3. 「カスタムCSS」に、選択したCSSを追加

## ココフォリア

### ゲーム盤面

#### 基本的な表示

- 表示　：背景、前景、キャラクター、スクリーン、マーカーパネル
- 非表示：操作系UI、ステータス、チャット、カットイン、発言

```css
@import url("https://q-fig.github.io/ccfolia_css/ccfolia/board.css");
```

![board](/images/board.png)

#### 背景のみ

- 表示　：背景
- 非表示：操作系UI、ステータス、チャット、カットイン、前景、キャラクター、スクリーン、マーカーパネル、発言

```css
@import url("https://q-fig.github.io/ccfolia_css/ccfolia/background.css");
```

#### 背景削除

背景のみを削除する。他と組み合わせて使用する。

- 非表示：背景

```css
@import url("https://q-fig.github.io/ccfolia_css/ccfolia/board.css");
@import url("https://q-fig.github.io/ccfolia_css/ccfolia/board_option/delete_background.css");
```

#### キャラのみ

- 表示　：キャラクター

```css
@import url("https://q-fig.github.io/ccfolia_css/ccfolia/character.css");
```

### チャット

> [!TIP]
> 画面サイズによってサイズが変わる。
> ココフォリアのURLの最後に、「/chat」を追加しての使用も可能。

- 表示　：チャット
- 非表示：操作系UI、ステータス、カットイン、背景、前景、キャラクター、スクリーン、マーカーパネル、発言

```css
@import url("https://q-fig.github.io/ccfolia_css/ccfolia/chat.css");
```

![img](/images/chat.png)

#### 追加の効果

他と組み合わせて使用する。

| 概要 | カスタムCSS |
| --- | --- |
| 右からフェードイン、フェードアウト← | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/chat_option/slide_right.css");` |
| →左からフェードイン、フェードアウト | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/chat_option/slide_left.css");` |
| 角を丸くする | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/chat_option/panel_cycle20.css");` |
| 区切り線なし | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/chat_option/panel.css");` |
| 吹き出し1 | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/chat_option/talk.css");` |
| 吹き出し1白 | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/chat_option/talk_white.css");` |
| 吹き出し2 | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/chat_option/talk2.css");` |
| 吹き出し2白 | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/chat_option/talk2_white.css");` |

> [!TIP]
> 吹き出し1,2の色は、変更することができる。
>
> ##### 変更可能箇所
> | css | キャラアイコン枠線 | 背景 | 枠線 | 文字色 | ダイス結果箇所の背景色 |
> | --- | :---: | :---: | :---: | :---: | :---: |
> | 吹き出し1 | ○ | ○ | × | × | × |
> | 吹き出し1白 | ○ | ○ | × | ○ | ○ |
> | 吹き出し2 | ○ | ○ | ○ | × | × |
> | 吹き出し2白 | ○ | ○ | ○ | ○ | ○ |
> 
> ##### 変数名
> | 変更箇所 | 変数名 |
> | --- | --- |
> | キャラアイコン枠線 | --custom-avatar-border-col |
> | 背景 | --custom-bg-col |
> | 枠線 | --custom-bg-border-col |
> | 文字色 | --custom-txt-col |
> | ダイス結果箇所の背景色 | --custom-dice-bg-col |
>
> ##### 例
> ```css
> /* 色変更 */
> .MuiPaper-root {
>   --custom-avatar-border-col: white;
>   --custom-bg-col: rgba(44, 44, 44, 0.87);
> }
> ```

### 発言

- 表示　：発言
- 非表示：操作系UI、ステータス、チャット、カットイン、背景、前景、キャラクター、スクリーン、マーカーパネル

```css
@import url("https://q-fig.github.io/ccfolia_css/ccfolia/balloon.css");
```

![img](/images/balloon.png)

#### 追加の効果

他と組み合わせて使用する。

| 概要 | カスタムCSS | イメージ |
| --- | --- | --- |
| 立ち絵を円に収める | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/balloon_option/cycle_img.css");` | ![img](/images/balloon_cycle.png) |
| 立ち絵非表示 | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/balloon_option/none_img.css");` | ![img](/images/balloon_none_img.png) |
| 背景なし | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/balloon_option/textonly_style.css");` | ![img](/images/balloon_textonly.png) |

### ステータス

> [!NOTE]
> イニシアチブにより、`div:nth-child(1)`の数字を変更する

```css
@import url("https://q-fig.github.io/ccfolia_css/ccfolia/status.css");
#root>div>div>div>div:nth-child(1) {
  display: flex;
}
```

![img](/images/status.png)

#### ステータスを横に並べる数を変更

ステータスに追加
他と組み合わせて使用する。

```css
/* 横並び（200の倍数） */
span.MuiBadge-root+div>div {
  max-width: 200px;
}
```

![img](/images/status_horizon.png)

#### 表示する人数の指定

他と組み合わせて使用する。

```css
/* 全員表示 */
#root>div>div>div>div:nth-child(n) {
  display: flex;
}
```

```css
/* 2番目以降表示 */
#root>div>div>div>div:nth-child(n+2) {
  display: flex;
}
```

```css
/* 4番目まで表示 */
#root>div>div>div>div:nth-child(-n+4) {
  display: flex;
}
```

> [!TIP]
> 記載以外をやりたい場合、nth-childについて調べること。<br>
> 参考のサイト：https://web-camp.io/magazine/archives/99177

#### ステータスの色変更

他と組み合わせて使用する。

```css
/* ステータスの色変更 */
span.MuiBadge-root + div > div > div > div:nth-child(2) > div:nth-child(2) {
  /* #ffffff のような表記でも可 */
  background-color: rgb(0,148,161);
}
```

![img](/images/status_change_color.png)

#### 追加の効果

他と組み合わせて使用する。

> [!WARNING]
> 追加効果を入れる場合、`@import`の行はまとめて上に書くこと。

| 概要 | カスタムCSS | イメージ |
| --- | --- | --- |
| アイコン非表示 | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/status_option/none_img.css");` | ![img](/images/status_none_img.png) |
| ステータス背景部分を高さ3pxの下線にする | `@import url("https://q-fig.github.io/ccfolia_css/ccfolia/status_option/line1.css");` | |

## Discord
