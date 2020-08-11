# docker-ec-cube3
ec-cube3の実行環境をDockerで構築

## 構成
| 分類 | ソフトウェア | バージョン |
| :---: | :---: | :---: |
| ECパッケージ | EC-CUBE | 3.0.18-p1 |
| OS（Webサーバー） | Debian GNU/Linux | 10（buster） |
| Webサーバー | Apache | 2.4 |
| 言語 | PHP | 7.1 |
| OS（DBサーバー） | Debian GNU/Linux | 10（buster） |
| DB | MySQL | 5.7 |

## 環境構築手順
※ 前提条件：Docker, Docker Composeを導入済みであること

①コンテナーを作成し実行
```
$ docker-compose up -d
```

②Webサーバーのコンテナーに接続
```
$ docker exec -it docker-ec-cube3_web_1 sh
```

③コンテナー内で依存ライブラリをインストール
```
$ composer install
$ exit
```

④下記URLにアクセスしてEC-CUBEの初期設定
```
http://localhost:8080/html
```

※データベースの設定は下記の通り
| 設定項目 | 設定値 |
| :---: | :---: |
| データベースのホスト名 | db |
| ポート | 3306 |
| データベース名 | ec_cube |
| ユーザー名 | root |
| パスワード | root |

④ 下記URLにアクセスしてphpMyAdmminに接続確認
```
http://localhost:8081
```
