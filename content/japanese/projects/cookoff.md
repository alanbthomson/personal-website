---
date: '2026-07-27T15:19:34+09:00'
title: 'Cookoff'
summary: '「リトル・ガイズ」をテーマにしたオンライン・ゲームジャム。プレイヤーがユニットを指揮して料理を作るRTS形式の料理シミュレーションゲーム。'
description: '「リトル・ガイズ」をテーマにしたオンライン・ゲームジャム。プレイヤーがユニットを指揮して料理を作るRTS形式の料理シミュレーションゲーム。'
categories:
  - Game Dev
  - hackathon
tags:
  - godot
  - gdscript
featured: true
# cover:
#   image: "landing/graffcolorsquare.png"
#   # can also paste direct link from external site
#   # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
#   alt: "<alt text>"
#   caption: "<text>"
#   relative: true # To use relative path for cover image, used in hugo Page-bundles
---

## 概要
このゲームは、[Brainless Game Jam](https://itch.io/jam/brainless-game-jam)の一環として、2人チームで開発されました。

テーマは「小さなキャラクターたち」と発表され、ブレインストーミングを重ねた結果、料理をテーマにしたリアルタイムストラテジー（RTS）ゲームというアイデアを思いつきました。プレイヤーは小さなコックたちのグループを操作し、協力して客からの炒め物の注文をこなしていきます。

## 特徴
- ユニットの選択やグループ化を含むユニット操作
- 食材の管理と調理シミュレーション
- 注文票の発行と料理の評価システム
- UI要素とゲームロジックの連携
- ゲーム状態の管理とハイスコア記録

## 課題
主な課題は、限られた開発期間に加え、チームメイトが新しいツールセット（Godot）を習得するのをサポートすることでした。これは私たち二人にとって素晴らしい学習の機会となり、開発の進捗と、ツールセットやゲームロジックに対する互いの理解を深めることのバランスを取りながら作業を進めました。

このプロジェクトで私にとって特に興味深かったのは、汎用的なオブジェクトプーラーの実装でした。このシステムは、調理用食材のリソースインスタンスを効率的に管理するために使用されました。


## 使用した技術
- Godot
- GDScript

## ゲームをプレイする
このゲームは現在、[itch.io](https://notkomiyaki.itch.io/cookoff)で公開されています。

DeepL.com（無料版）で翻訳しました。
{{< itch
    game="18352517"
    width="1150"
    height="660"
>}}


<!--{{< highlight go "linenos=inline, hl_lines=3 6-8" >}}
package main

import "fmt"

func main() {
    for i := 0; i < 3; i++ {
        fmt.Println("Value of i:", i)
    }
}
{{< /highlight >}}-->
