---
title: Hell of UE4 C++
date: "2020-04-26T23:28:00.000+0900"
tags: ["ue4", "cpp", "unreal4tress"]
description: UE4C++の地獄
disqus: true
---

SourceEngineにAimmatrixという仕組みがある

10フレームのアニメーションにそれぞれ

左下、下、右下、左、正面、右、左上、上、右上、真上

の方向を向いたポーズを割り当てて、色んな方向にエイムしてるときのブレンドポーズのソースにするというものだ

アニメーションデータはこんな感じ

(早すぎてフレームレートが追いつかなかったので手でシークバーを動かしてる)

[![こんな感じ](https://i.gyazo.com/17bbfb593162dc868903112588ffb761.gif)](https://gyazo.com/17bbfb593162dc868903112588ffb761)

これをUE4のAimOffsetにするのはそんなに難しくない

[ここ](https://docs.unrealengine.com/ja/Engine/Animation/AnimHowTo/AimOffset/index.html)に書いてあるとおりにすれば簡単にできる

ただしすべてのアセットで10回コピーして10回リネームし、18回フレームを削除し、新しくAimOffsetを作って10回割り当てるのはめんどくさい

しかも、TF2のAimmatrixは

9(クラス) x 3(武器の種類) x 4(姿勢) = 108 個もある

実際にはスパイとエンジニアは武器の種類がもういくつかあるのでそれ以上

しかも、後々新しい武器を追加していくとなると更に50個以上は増える

これは自動化しなくては

ということで最初はPythonでやろうとしたのだが使いたいAPIがサポートしてないので断念

断念したのが3週間くらい前

そして最近になって数年ぶりのC++でプラグインを書くことにした

今日はかなりいい線まで行ったが結局完成には至らなかった

今日の成果は[これ](https://github.com/aoisensi/UE4-TF2HelperPlugin/blob/767ccd2c2e21b73f39dabc8d94e45a6c9a7cbe67/Source/TF2HelperPlugin/Private/TF2HelperPlugin.cpp#L80)

なぜかアセットは完成するが一旦アセットをコンテンツブラウザから開き、一度何かの値を再割り当てしないと正常に表示されない…

一日中コード書いてたのに完成しなかった…

特にリフレクションをいじらないといけないのが辛かった

`UE4 Reflection`で検索しても`Reflection Environment`ばっかり出てくるし…

Preview版のUE4.25で書いてて、4.25から`UProperty`が`FProperty`に変更になるので情報ほぼ出てこないし

(でもマクロの`UPROPERTY`とクラスの`UProperty`がダブっててググラビリティが増えるのは嬉しい)

疲れた

今日はもう寝る

明日は完成するといいな
