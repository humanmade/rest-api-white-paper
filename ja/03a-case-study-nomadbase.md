# 事例: NOMADBASE

[Nomadbase](http://nomadbase.io)は、リモートワーキングやノマド風のライフスタイルを支援するためのサービスです。ソーシャルネットワークサービスのAPIを使用して、世界中のノマドワーカーたちの位置情報を地図上に表示しています。

> 私たちの開発チームはWordPressを使用した開発において非常に多くの経験を持っています。そしてWordPressを使ったアプリケーション開発において優れた実績を持っていると自負しています。ユーザー管理やサインアップ、その他のコミュニケーションを行うためのREST API、そして一般的なサーバー環境で動作することなどのWordPressの優れた特徴を生かすことにより、数週間もしくは数ヶ月かけることなく、わずか数日でプロトタイプを作り上げることができました。私たちはREST APIをフロントエンドとのコミュニケーションに使用するだけでなく、FacebookやFoursquareなどとのユーザーの位置情報のやり取りにも使用しています。

Joe Hoyle, Nomadbase

## なぜWordPressとREST APIを使うのか？

WordPress enabled the developers to get the first version of Nomadbase up and running quickly, providing both a stable central platform where data can be aggregated and an API for delivering the data to the frontend.

Nomadbaseの最初のバージョンを立ち上げる際に、WordPressを使うことで開発期間を短くすることができました。WordPressは、データを収集するための中心的な役割と、フロントエンドにデータを提供するためのAPIとしての役割の双方を安定して提供しています。

## 仕様

Nomadbaseは、Facebook、Swarm、Twitter、Instagram、そしてTripItのAPIを使用して、それらから得た位置情報を集約しています。このデータはMySQL内のカスタムテーブル内に保存されます。その後このデータは、REACTベースで構築されたフロントエンドからREST API経由で使用され、ブラウザに表示されます。地図上にオーバレイを作成するには、[Leaflet](http://leafletjs.com/)を使用しています。

新しいユーザーがNomadbaseにサインアップする際には、5つの異なるソーシャルネットワークからのリクエストを受けます。これは大きなバックグラウンドプロセスを必要とします。これを高速化するためにwp-cronを、Human Madeによって大規模WordPressサイト向けに開発された[Cavalcade](https://github.com/humanmade/Cavalcade)というシステムツールに置き換えています。

Nomadbaseの次のステップは、ブラウザベースのアプリのコードを再利用したReact NativeベースのiOSアプリです。すべてのデータとユーザーのアクションはREST APIによって実現しています。新しいアプリケーションを開発するのに際して、新たなバックエンドは必要ありません。
