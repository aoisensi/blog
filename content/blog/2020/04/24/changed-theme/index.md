---
title: Changed blog theme
date: "2020-04-24T22:12:00.000+0900"
tags: ["blah"]
description: ブログのテーマを変えた
disqus: true
---

とりあえずデフォルトの https://github.com/gatsbyjs/gatsby-starter-theme でいいかーとか思ってたけど後から考えるとこれテーマの差し替えとても面倒そうだぞと気がついたので急いで移行  
https://github.com/thundermiracle/gatsby-simple-blog がよさげだったのでこれにしよう  
色々カスタマイズ楽しそう

しかし問題が起こった

どうやらCircle-CIを通さないとNetlifyにはデプロイできないらしい

結局`netlify-cli`を使ってデプロイすることにした