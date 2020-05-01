---
title: Draw Tiled stage on LÖVE
date: "2020-05-01T23:39:00.000+0900"
tags: ["unknown", "love2d", "lua"]
description: LÖVEでTiledのステージを描画する
disqus: true
---

とりあえず昨日言ってたゲームを[LÖVE](https://love2d.org/)を使って作っていってみてる

とりあえず[Tiled](https://www.mapeditor.org/)というマップエディタで作ったステージの描画ができた

データをエクスポートするとき`.lua`形式で吐き出せるの便利

ただし、タイルセットの`tiles`プロパティがTiled側で何かしらのプロパティを設定しないと`tiles`の中に出てこないのめんどくさかった

使わないタイルをたくさん読み込むのも微妙だと思ったので取り敢えず今は適当なプロパティをつけた

明日は当たり判定を実装してみます
