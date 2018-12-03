---
title: Spectraspectacular(AMC Soundproject 2014)
thum: amc_soundproject.jpg
date : 2015-01-29
ogpimage: soundproject_ogp.png
category: artwork
tags:
- sound
- programming
---

AMC SOUND PROJECT 2014 成果発表-上野公園作品巡り- にて発表

[AMC（東京藝術大学情報芸術センター）アーカイブページ](https://geidaiamc.tumblr.com/post/114569954667/amc-sound-project-2014-%E6%88%90%E6%9E%9C%E7%99%BA%E8%A1%A8-%E4%B8%8A%E9%87%8E%E5%85%AC%E5%9C%92%E4%BD%9C%E5%93%81%E5%B7%A1%E3%82%8A-%E6%8B%85%E5%BD%93%E8%AC%9B%E5%B8%AB%E5%8F%A4%E6%BE%A4-%E9%BE%8D)

<iframe width="610" height="400" src="https://www.youtube.com/embed/ea4RPf-Qzak" frameborder="0" allowfullscreen></iframe>


東京藝術大学情報芸術センター（AMC）のプロジェクト"AMC SOUND PROJECT 2014"内で制作した作品。

以下プロジェクトの説明を引用

> 2014年度後期より、"環境に適合する音楽" をテーマにiPhone上で聴くことのできるインタラクティブな音楽アプリ・作品の制作のワークショップを隔週で続けてきました。モバイル端末の携帯性を生かした音楽の聴き方、ストリーミング再生が容易に行えるようになった時代のサウンドメディアの扱い方など、これからの音楽・サウンドの可能性を探るのがこのプロジェクトの目的です。
>
> 今回は半期を通して制作された作品を巡るツアーを公開で行います。
>
> 3作品と少ないですがgps情報を元に特定の場所、特定の時間でしか聴くことのできない作品や、加速度を扱った作品、方位をもとにした作品と多様な展開をみせています。
>
>  概要
>  
>  - 集合場所： AMC ラボラウンジ
>  - 日時：1月29日（木）13時00分〜15時00分
>  - 作品発表：松浦知也（音環）　濱崎 大吾（音環）　小宮知久（作曲）
>  - スケジュ−ル
>     + 13:00 AMC集合、アプリのインストール。Pdデータの共有
>     + 13:30-上野公園噴水前にて：松浦知也
>     + 14:00-上野公園中央広場にて：濱崎 大吾
>     + 14:30-御徒町公園ブランコにて：小宮知久
>   
>  主催 : 東京芸術大学 芸術情報センター


# 作品概要

このプロジェクトでは[Puredata](puredata.info)を用いて簡単にiPhone上の加速度、GPS、タッチセンサーのインプットを使ったりスピーカーで音を出すためのフレームワークが配布された。

松浦はサイトスペシフィック性に着目した、上野公園の噴水の動きに対応する音楽を聴くサウンドアプリを制作した。

# Spectraspectacular

![](spectraspectacular.png)

上野公園の噴水は7,8,7本の合計23本の噴水で構成されている。

iPhoneのマイク入力から一周期分の波形を切り出し、その波形のオシレータを23本分作る。23本の波形は中心の噴水をある周波数に設定し、その周波数の2のn乗*3のm乗の周波数のどれかに設定される。

オシレータの音量はそれぞれの噴水からの距離に比例して小さくなる、また噴水の出るパターンが変化するのに各オシレータの音量が追従するので、噴水の周りを歩き回ることで音色が変化する。

# Puredata patch

![](pd1.png)

メイン画面。

![](pd2.png)

噴水の位置の設定画面。噴水の位置そのものはGoogleMapから取得して使用したが、Puredataの小数点精度が32bitなので正確な緯度経度を組むのが難しかった。

![](pd3.png)

噴水の変化のプリセット画面。噴水のパターンの変化のデータを探したもののどこにも情報がなく、仕方なく冬の上野公園で4時間座り続けて観察した。

結果、30分休み30分噴水が出て、30分の中では30秒or60秒ごとにパターンが変化する。各噴水は無/低/中/高の4段階で変化し、パターンは15個ぐらいあった（はず）。

なお、噴水の変化は絶対時刻を利用してないらしく、1日毎に5秒くらいズレていくことが発表の時に判明した。