■サービス概要
・音楽ライブ・フェス終了後、参加者が感想や思い出を発信し合うことで、余韻に浸ったり、喪失感を緩和させたりする場を提供するサービスです。


■ このサービスへの思い・作りたい理由
・自分は音楽ライブ・フェスが趣味で、年に10回ほど参加します。イベントの後には必ず、「X」でトレンドに上がるほどの感想が参加者から発信されます。こうした参加者のイベントの余韻は1.2週間ほど続くと聞きました。（自分も余韻は一週間ほど残りライブで聴いた曲をなぞるように改めて聴きます）
　また、イベント終了後は、ライブの盛り上がりから解放され、現実に引き戻されることにより「悲しい」「寂しい」といった喪失感に襲われます。
・こういった「余韻」や「喪失感」を共有できるような場があれば、参加したもの同士で、より楽しく余韻に浸ることができたり、寂しい気持ちを共感し合い、喪失感を分かち合うことができると思いました。


■ ユーザー層について
音楽ライブ・フェスに参加する　[男女、20代〜30代、SNSを利用されている方、発信するのが好きな方]


■サービスの利用イメージ
・音楽フェス、ライブ終了後の控室のような感覚で利用。
・サービスはログイン必須。
・部屋は管理者がライブごとに作成し、ユーザーはその中に入りコメントをする。
・「ここが良かった！」「あの曲が聴けて良かった！」など感想を共有することで、余韻に浸ったり、
「ライブが終わって寂しい」「また次も参加しましょう！」など喪失感を分かち合うことで、落ちた感情を和らげることができる。


■ ユーザーの獲得について
・ターゲットは、音楽ライブ・フェスに参加する　[男女、20代〜30代、SNSを利用されている方、発信するのが好きな方]なので「X」でアプリ宣伝のポストをする。


■ サービスの差別化ポイント・推しポイント
・「X」がサービスとしては類似しているが、Xは規模が大きすぎる。規模を小さくし目的を音楽ライブ、フェスの感想共有に絞ることで、差別化を図る。

・「X」なら目的のポストを探すのに「文言」や「＃」で検索する必要があるが、このサービスではライブごとの部屋を作ることで同じ目的意識の人達が集まることができる。

・ライブのセットリスト表示、画像のアップ機能、音楽のダウンロード機能をつける。

■ 機能候補
MVPリリース時に作っていたいもの
・ユーザー認証（投稿者の識別）
・チャット機能（ActionCable）・チャット機能（ActionCable）
・ライブごとのチャットルームの識別
・画像のアップ機能

本リリースまでに作っていたいもの
・いいね機能
・曲のセットリスト表示
・音楽のダウンロード機能


■ 機能の実装方針予定
MVPリリース時に作っていたいもの
1. ユーザー認証（投稿者の識別）
概要: ユーザー登録、ログイン、ログアウト機能を実装して、投稿者を識別する。
使用技術: Devise
API: 自作の認証APIエンドポイント
2. チャット機能（ActionCable）
概要: ユーザー同士がリアルタイムでチャットできる機能。（チャットルームはライブごとに作成する）
使用技術: ActionCable
API: WebSocket通信によるリアルタイムデータ転送。
3. ライブごとのチャットルームの識別
概要: コメントルームのデータモデルを作成しライブごとにチャットルームを識別する。データモデルには、チャットやユーザーとの関連付けをする。
4. 画像のアップ機能
概要: ユーザーが画像をアップロードできる機能。
使用技術: ActiveStorage

本リリースまでに作っていたいもの
1. いいね機能
概要: 投稿やセットリストに対してユーザーが「いいね」を付けられる機能。
使用技術: Ajaxを使用した非同期処理。
API: 自作の「いいね」APIエンドポイント。
2. 曲のセットリスト表示
概要: ユーザーが作成したセットリストを表示する機能。
使用技術: Ruby on Railsのビュー機能。
3. 音楽のダウンロード機能
概要: ユーザーが音楽をダウンロードできる機能。
使用技術: ファイル処理ライブラリ。
API: 外部音楽サービスのAPIを活用。Spotifyなど


■ 使用予定の技術スタック
バックエンド
- Ruby on Rails
- Devise（ユーザー認証）
- ActiveStorage（画像アップロード）
- ActionCable（リアルタイムチャット）

フロントエンド
- JavaScript
- Bootstrap（CSSフレームワーク）

### データベース
- MySQL

### API
- 自作認証APIエンドポイント
- 自作「いいね」APIエンドポイント
- 外部音楽サービスAPI（Spotifyなど）

### テスト
- RSpec


### 画面遷移図
Figma：https://www.figma.com/board/OKJCxoKYBoldymLsJ65ihR/Untitled?node-id=0%3A1&t=LVJsXm6GHN7W2qk2-1

### READMEに記載した機能
- [ ] ユーザー認証機能（ログイン、ログアウト、メールアドレス変更、パスワード変更）
- [ ] チャット機能（ActionCable）
- [ ] 画像のアップ機能
- [ ] いいね機能
- [ ] いいね解除機能
- [ ] 曲のセットリスト表示機能
- [ ] 音楽のダウンロード機能
- [ ] チャットルームの作成機能（管理者が作成）
- [ ] チャットルームの削除機能（管理者が削除）


### メールアドレス・パスワード変更確認項目
直接変更できるものではなく、一旦メールなどを介して専用のページで変更する画面遷移になっているか？
- [ ] パスワード




### ER図
drawio：https://drive.google.com/file/d/1XiQqmXnuKYg-uxUN5sPH5lr9X92okIz6/view?usp=sharing