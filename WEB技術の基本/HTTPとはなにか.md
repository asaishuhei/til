## HTTPとは
　HTTPは、WebクライアントとWebサーバー間でHTMLなどのテキストファイルや、画像などのコンテンツをやり取りする際に使われるプロコトル。そのやり取りをする際に利用されているデータ形式のことを『HTTPメッセージ』と呼ぶ。
  
### ２種類のHTTPメッセージ
　HTTPメッセージには、Webブラウザからの要求である『HTTPリクエスト』とWebサーバーからの応答である『HTTPレスポンス』の次の2種類がある。  
- **HTTPリクエスト**：『リクエスト行』、『メッセージヘッダー』、『メッセージボディ』の３つに分けることができる。
  - リクエスト行：Webサーバーに対してどのような処理を依頼するのかを伝える情報が含まれている。
  - メッセージヘッダー：Webブラウザの種類や、対応しているデータのタイプ、データの圧縮方法、言語などの情報を伝えている。
  - メッセージボディ：Webサーバーにデータを送るために使われる。
- **HTTPレスポンス**：『ステータス行』、『メッセージヘッダー』、『メッセージボディ』の３つに分けることができる。
  - ステータス行：HTTPリクエストに対してWebサーバー内での処理の結果を知らせる。
  - メッセージヘッダー：Webサーバーのソフトウェア情報や、返信するデータのタイプ。
  - メッセージボディ：HTMLや画像データ等のデータを格納する場所。
  
## HTTPメソッド
　HTTPリクエストを用いてWebサーバーに具体的な内容を伝えているのは、HTTPリクエストのリクエスト行に含まれる『HTTPメソッド』である。HTTPメソッドは目的別に複数定義されており、例えばHTMLファイルなどのコンテンツを取得したい場合は『GET』メソッド、データをWebサーバーに対して送信する場合は『POST』メソッドが利用される。
- GETメソッド：URLにユーザー名やパスワードが含まれるため、それらの情報がWebブラウザの履歴に残ってしまうので機密性がが低い。
- POSTメソッド：情報をメッセージボディに記録して送信することで、Webブラウザの履歴には残らない。よってGETメソッドよりも機密性が高い。

### ステータスコード
HTTPレスポンス内には、HTTPリクエストに対するWebサーバー内での３桁の数字からなる処理結果が含まれている。それが『ステータスコード』である。 
ステータスコードは、次の５種類に分類される。
- １００番台：リクエスト継続中を通知している。
- ２００番台：リクエストが正常に受理されたことを通知している。
- ３００番台：転送処理などのWebブラウザ側で追加の処理が必要であることを通知している。
- ４００番台：Webブラウザ側のエラーであることを通知している。
- ５００番台：Webサーバー側のエラーであることを通知している。

### 上記の内容を実際に処理が行われた画像で説明する
[![Image from Gyazo](https://i.gyazo.com/3eb7baef71dc2488a9078063180aac01.png)](https://gyazo.com/3eb7baef71dc2488a9078063180aac01)

- Request URL：Webサーバーに『』を要求している。
- Request Method：URLにHTMLファイルや画像といったデータを取得する際に使われるGETメソッドが利用されている。
- Status Code：リクエストされたコンテンツが未更新であることを意味するステータスコード『304』が通知されている。

[![Image from Gyazo](https://i.gyazo.com/e91685442505e885e6fea3db722f7274.png)](https://gyazo.com/e91685442505e885e6fea3db722f7274)

『リクエスト』をみてみると、クライアント側から要求されたリクエストURLをWebサーバー側が処理し、要求されたHTMLファイルの内容がレスポンスされているのが分かる。
