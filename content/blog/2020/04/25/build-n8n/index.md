---
title: Building n8n...
date: "2020-04-25T21:41:00.000+0900"
tags: ["blah"]
description: n8n構築中...
disqus: true
---

今日は午前中 というか0:00から20:00くらいまでずっと寝てた

なんかしんどくて…

さて本題

ifttt いいんだけど複数アカウント使えなかったり色々制約が多いので他のソフトを探してた

そしたらn8nというのが見つかったのでVPSに入れてみる

どうやらデータベースも使ってないらしく、docker(docker-composeではない)で一発で建てれるみたい

nginxのリバースプロキシ書いてdockerコマンドポチ

で、アプリは動いたのだがなんか右上に`Connection lost`と書いてある…

いろいろ試してDockerやめたりしたけどうまくいかず

結局nginxのリバースプロキシに追加設定しないといけないのがわかった

https://github.com/n8n-io/n8n/issues/36#issuecomment-539647882

さてとりあえずブログの投稿をTwitterとMastodonに自動投稿するのを試してみよう…

と思ったらTwitterに対応してない… なんだと…

素直にifttt使います…

Factorioしたい
