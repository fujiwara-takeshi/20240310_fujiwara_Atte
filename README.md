# Atte（勤怠管理用Webアプリケーション）

![stamp](https://github.com/fujiwara-takeshi/20240310_fujiwara_Atte_EC2/assets/151005520/ede64ce3-3716-4222-b2f0-1a09f5776557)

## 作成目的
　社員の勤怠管理・人事評価のため

## 環境構築
#### Dockerビルド
　１．`git clone git@github.com:fujiwara-takeshi/20240310_fujiwara_Atte.git`</br>
　２．DockerDesktopアプリを立ち上げる</br>
　３．`docker-compose up -d --build`</br>

#### Laravel環境構築
　１．`docker-compose exec php bash`</br>
　２．`composer install`</br>
　３．「.env.example」ファイルを 「.env」ファイルに命名を変更。または、新しく.envファイルを作成</br>
　４．「.env」ファイルに以下の環境変数を追加</br>
　　`DB_CONNECTION=mysql`</br>
　　`DB_HOST=mysql`</br>
　　`DB_PORT=3306`</br>
　　`DB_DATABASE=laravel_db`</br>
　　`DB_USERNAME=laravel_user`</br>
　　`DB_PASSWORD=laravel_pass`</br>

#### 認証メールサーバー設定（gmailの場合）
　１．「.env」ファイルの以下の環境変数を追加</br>
　　`MAIL_MAILER=smtp`</br>
　　`MAIL_HOST=smtp.gmail.com`</br>
　　`MAIL_PORT=587`</br>
　　`MAIL_USERNAME=送信元に設定するgmailのアドレス`</br>
　　`MAIL_PASSWORD=gmailアカウントのアプリパスワード`</br>
　　`MAIL_ENCRYPTION=tls`</br>
　　`MAIL_FROM_ADDRESS=送信元に設定するgmailのアドレス`</br>
　　`MAIL_FROM_NAME="Atte"`</br>

　※アプリパスワードの発行方法は以下のWebサイトを参照願います。</br>
　　https://qiita.com/koru1893/items/e30d19ac97eac59b1e19</br>

#### アプリケーションキーの作成
　`php artisan key:generate`</br>

#### マイグレーションの実行
　`php artisan migrate`</br>

## 利用手順
　１．下記URLにアクセス</br>
　　http://localhost/</br>
　２．ユーザー新規登録ページにて登録処理</br>
　３．登録メールアドレス宛に確認メールが届くので、認証する</br>
　４．自動的に打刻ページに遷移</br>

　以降はログインページよりログインしご利用いただけます。</br>

## 機能一覧
　・ユーザーログイン機能</br>
　・ユーザー新規登録機能</br>
　・ユーザーログアウト機能</br>
　・打刻機能（勤務・休憩の開始終了時間登録）</br>
　・年月日別勤怠記録の表示</br>
　・ユーザー一覧の表示、及び検索機能</br>
　・ユーザー別勤怠記録の表示</br>

## 使用技術（実行環境）
　フレームワーク：Laravel 8.83</br>
　プログラミング言語：PHP 7.4.9</br>
　Webサーバーソフト：Nginx 1.21.1</br>
　データベースエンジン：MySQL 8.0.26</br>
　コンテナサービス：Docker 20.10.25</br>
　　　　　　　　　　Docker Compose 2.4.1</br>

## データベーステーブル設計書
![スクリーンショット 2024-05-08 171845](https://github.com/fujiwara-takeshi/20240310_fujiwara_Atte_EC2/assets/151005520/b26220b1-e4c4-4145-a87a-1a5785f86668)

## ER図
![スクリーンショット 2024-05-08 172017](https://github.com/fujiwara-takeshi/20240310_fujiwara_Atte_EC2/assets/151005520/802c7692-b862-4dc0-a087-d744a5e929af)
