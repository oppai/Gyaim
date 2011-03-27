# Gyaim

 * [MacRuby](http://www.macruby.org/)で作ったMac用のIMEです。
 * 数百行のRubyで実用レベルのIMEを作れることを示すものです
    * 単純な変換しかできませんがそれなりに使えます
    * 見栄えはInterfaceBuilderで簡単に変更できます
    * 変換アルゴリズムはRubyで簡単に変更できます
 * 現在の変換部分は超いい加減です
    * 予測機能がありません
    * そのかわり(?)パタンに正規表現が使えます
        * "ke.*da" と入力すると "慶應大" が候補に出たり

## インストール

 * [MacRuby](http://www.macruby.org/)のインストールが必要です
 * 多分SnowLeopardが必要です
 * "make small" または "make large" してからログアウトして再ログインすると
   「言語環境設定」からGyaimを選択できるようになります
 * PalmのIMEで利用してた「富豪辞書」を使っています
    * 自前の適当な辞書を使うことも可能です

## 使いかた

 * ローマ字を入力すると候補が表示されます
 * スペースキーで候補を選択し、改行キーで確定します
 * ローマ字入力の後ですぐ改行キーを押すと完全マッチで候補が検索されます
    * ひらがな、カタカナ入力に便利です
 * ローマ字入力した後「.」を入力するとGoogleSuggestが呼ばれます
    * 固有名詞の入力に便利です
    * "ottoga." などと入力するとひどいことになります
 * 単語登録
    - 登録したい単語をドラッグして選択した後で文字入力すると、選択した単語が第一候補に表示され、
      その単語をスペースキーで選択して改行キーで確定するとユーザ辞書に登録されます
 * ユーザ辞書、学習辞書は以下にセーブされます
    - ユーザ辞書: ~/.gyaimdict/localdict.txt
    - 学習辞書: ~/.gyaimdict/studydict.txt
    - ユーザ辞書は普通に編集可能です

## TODO

 * 様々な変換エンジンを切り替える
 * Romakana.rbをRuby1.9用に修正
 * 辞書キャッシュの扱い
    - Resourceに入れる
    - make dictでキャッシュをResource内に作る
        - Marshalを利用するのをやめる
 * 登録を簡単にしたい
    - 研究になるかも?
 * 単漢字変換
  - 候補が10個以上出るように
 * 予測機能
    - 実は要らないかも
 * SocialIMEとかGoogleIMEとかを呼ぶ
 * まともな変換システムを自力で作る

<!--
## 論文ネタ

 * IME用のヒントを与えるアプリケーション
        <input type="text" hint="kamakura_address">
   みたいにすると鎌倉の住所を入力しやすいIMEが出てくる
 * ヒントを出すだけだと既に色々あるかも
 * ヒントによって画像すら入れられるようにすると凄い
 * MacのIMEで画像を入力できる気がする
    - NSTextViewじゃなくてWebView(?)にすればよい
-->
