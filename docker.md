# Dockerで<br/>いろいろ動かしてみた

2016年7月9日

Иосиф Хуэйдэ Ежэн Такакура

（高倉　佑輔）

---

## 最近話題のDocker

Linuxコンテナを利用した、  
環境構築とかデプロイとか  
いろいろ楽になるツール群。

（多少の誤解あり）

---

## 何が便利になるのか

1. 環境構築
2. テスト
3. デプロイ

統一された環境ができるのがミソ

---

## Docker for Macのインストール

以下の条件が必要

1. 2010年以後に発売されたMacであること
2. OS X 10.10.3 Yosemite以後であること
3. メモリが最低4GB搭載されていること
4. VirtualBox 4.3.30以前がインストールされていないこと

---

## 今回Dockerで動かしてみたもの

- ASP.netのデモ
- Wordpress + HHVM + H2O + MariaDB

---

## とりあえずASP.net

1. `git clone git@github.com:aspnet/Home.git`
2. `cd Home/samples/1.0.0-rc1.update1/HelloMvc`
3. `docker build -t huideyeren/aspnet .`
4. `docker run -t -p 8080:5004 huideyeren/aspnet`
5. http://localhost:8080/

これで動くはず。

---

## 次はWordpress

https://github.com/huideyeren/wordpress-h2o-http2-hhvm

ここに一式作りました。

※ yewton氏のNginxのものをH2O向けに改変しました。

---

## 手順

1. `git clone git@github.com:huideyeren/wordpress-h2o-http2-hhvm.git`
2. `cd wordpress-h2o-http2-hhvm`
3. `docker-compose up --build`
4. https://localhost/

---

## 現在の課題

- PHPのファイルを編集できない
- MariaDBのダンプがとれない

---

## 次に動かしてみたいもの

- Railsアプリ
  - 現在行っているRuby勉強会で作成中のアプリ
  - https://github.com/yochiyochirb/kawaiichan

---

## Dockerの今後

WindowsコンテナーはDockerと互換性があるらしい

もしかしたらWindowsとLinuxでオーケストレーション？

---

ありがとうございました
