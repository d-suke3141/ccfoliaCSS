# css-for-obs-steram
OBS用のCSSまとめです
## CCFOLIA用
- [simple.css](ccfolia/simple.css)
  - シンプルな1ブラウザソース用
  - 使用方法
    - ```@import url("https://d-suke3141.github.io/css-for-obs-stream/ccfolia/simple.css");```
- [simple-transparent.css](ccfolia/simple-transparent.css)
  - simple.cssと同じ構成で下記の要素を非表示ではなく透明化したもの
    - 音量操作
    - 拡大操作
  - 使用方法
    - ```@import url("https://d-suke3141.github.io/css-for-obs-stream/ccfolia/simple-transparent.css");```
### パーツ分割
- [main.css](ccfolia/parts/main.css)
  - メイン画面用CSS
  - キャラクター・マーカーパネル・スクリーンパネルなどは表示される
  - 使用方法
    - ```@import url("https://d-suke3141.github.io/css-for-obs-stream/ccfolia/parts/main.css");```
- [main-no-character.css](ccfolia/parts/main-no-character.css)
  - main.cssからキャラクターのみを非表示にしたもの
  - 使用方法
    - ```@import url("https://d-suke3141.github.io/css-for-obs-stream/ccfolia/parts/main-no-character.css");```
- [popup.css](ccfolia/parts/popup.css)
  - チャット発言時のポップアップ
  - キャラ画像を丸く表示する
  - 使用方法
    - ```@import url("https://d-suke3141.github.io/css-for-obs-stream/ccfolia/parts/popup.css");```
- [status.css](ccfolia/parts/status.css)
  - 全員分のステータスを縦並びに表示する
  - 幅を狭くするとHPなどのステータス表示が省略される
  - 使用方法
    - ```@import url("https://d-suke3141.github.io/css-for-obs-stream/ccfolia/parts/status.css");```
- [status-text.css](ccfolia/parts/status-text.css)
  - 各キャラクターのステータスをテキスト形式で表示する
  - 使用方法
    - ```css 
      :root{
          --font-color: black;
          --font-family: "Noto Sans JP";
          --width: 250px;
      }
      .sc-cwpsFg > div:not(:nth-child({character_number})){
          display: none;
      }
      ```
    - --font-colorに文字の色を設定する
    - --font-familyに文字のフォントを設定する
    - --widthにステータス文字列の幅を設定する
    - {character_number}をCCFOLIAでのキャラのの表示順に置き換える(１からスタート)
## Discord Streamkit用
- [character.css](discord/character.css)
  - キャラクター表示用CSS
  - CSS変数を変更することで各種パラメーターを変更可能
  - 使用方法 
    - ```css
      @import url("https://d-suke3141.github.io/css-for-obs-stream/discord/character.css");
      :root {
          --image-url-1: url("{image_url1}");
          --image-url-2: url("{image_url2}");
          --name: "{name}";
          --name-size: 30px;
          --animation: begin-to-speak-jump;
      }
      li[class*="State"] > img:not([src*="{discord_id}"]){
          display: none;
      }
      ``` 
    - --image-url-1にキャラクターの画像URLを設定する  
    - --image-url-2に差分画像のURLを設定する(差分がない場合は行を削除)  
    - --nameにキャラクター名を設定する(名前を表示しない場合は行を削除)  
    - --name-sizeにキャラクター名の文字サイズを設定する(設定しない場合は30pxとなる) 
    - --animationにアニメーションを設定する(設定しない場合はbegin-to-speak-jump, speaking-secondimage)  
      - begin-to-speak-jump: 話し始めにぴょこんと跳ねる  
      - speaking-jump: 話してる途中にぴょこぴょこ跳ねる  
      - speaking-secondimage: 話してる途中に差分画像が交互に表示される  
    - {discord_id}をプレイヤーのDiscord IDに置き換える
