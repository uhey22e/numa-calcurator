---
slug: "/calc-procedure"
title: "レシピの計算方法について"
---


ここでは「かんたん沼計算機」の計算ロジックについて解説します。


## 1. 目標値の決定

まず最初に、目標値として以下4つの数値を決めます。

- 目標摂取カロリー [kcal]
- 目標PFCバランス
    - P: たんぱく質 [%]
    - F: 脂質 [%]
    - C: 炭水化物 [%]

ここでは、1日の目標摂取カロリーが1500kcal、PFCバランスが30% : 20% : 50%という目標値を例に沼のレシピを計算していきます。

- 目標摂取カロリー : 1500kcal
- 目標PFCバランス
    - P: たんぱく質 : 30%
    - F: 脂質 : 20%
    - C: 炭水化物 : 50%


## 2. 必要栄養素の計算

目標値を元に、各栄養素の量をグラムに変換します。

変換式は以下の通りです。

<div class="highlight">
目標摂取カロリー [kcal] * (栄養素比率 [%] / 100) / 1グラムあたりのカロリー [kcal/g]
</div>

総カロリーが1500kcal、PFCバランスが3:2:5の場合は以下の通りです。

- たんぱく質

<div class="highlight">
1500 [kcal] * (30 [%] / 100) / 4 [kcal/g] = 112.5 [g]
</div>

- 脂質

<div class="highlight">
1500 [kcal] * (20 [%] / 100) / 9 [kcal/g] = 33.3 [g]
</div>

- 炭水化物

<div class="highlight">
1500 [kcal] * (50 [%] / 100) / 4 [kcal/g] = 187.5 [g]
</div>


## 3. サブ食材・サプリメントの栄養素計算

沼に加えて食べたいものの栄養素を計算します。
ここでは例として、ゆで卵1個と、牛乳で割ったプロテインの栄養素を計算します。

完全に沼しか食べない場合、またほぼ無視できるカロリーの食材の場合はこの手順はスキップします。

まずは、卵1個あたり60gとしてゆで卵の栄養素を計算します。
卵100gあたりの栄養素は以下の通りです。

- たんぱく質 : 12.3g
- 脂質 : 10.3g
- 炭水化物 : 0.3g

ここから60gあたりの各栄養素を以下の式で計算します。

<div class="highlight">
食材の量 [g] / 栄養素の単位量 [g/g] * 単位量あたりの栄養素量 [g/g]
</div>

この式を使って計算した、卵60gの栄養素は以下の通りとなります。

- たんぱく質 : 7.4g
- 脂質 : 6.2g
- 炭水化物 : 0.2g

牛乳、プロテインについても同様に計算します。
プロテインはマイプロテインの"Impact ホエイプロテイン ミルクティー味"で計算を行いました。

- プロテイン : 25g
    - たんぱく質 : 20.5g
    - 脂質 : 1.9g
    - 炭水化物 : 1.0g

- 牛乳 : 200mL (206.4g)
    - たんぱく質 : 6.8g
    - 脂質 : 7.8g
    - 炭水化物 : 9.9g

最後に、1日の必要栄養素からこれらサブ食材・サプリメントの栄養素を引いて、沼から摂取する栄養素を計算します。

- 沼から摂取する栄養素
    - たんぱく質 : 77.8g (112.5g - 7.4g(卵) - 20.5g(プロテイン) - 6.8g(牛乳))
    - 脂質 17.4g (同上)
    - 炭水化物 176.4g (同上)


## 4. 白米の計算

沼の栄養素を構成するのは主に白米と皮無し鶏むね肉ですが、まずは必要な炭水化物を満たすだけの白米の量を計算します。
白米を先に計算するのは、鶏むね肉が炭水化物をほとんど含んでいないため、白米の量を必要な炭水化物量の1パラメータのみで計算出来るためです。

白米100gあたり栄養素は以下の通りです。

- たんぱく質 : 6.1 [g]
- 脂質 : 0.9 [g]
- 炭水化物 : 77.6 [g]

前節で求めた、沼から摂取したい炭水化物181.5gを満たすのに必要な白米の量を以下の式で計算します。

<div class="highlight">
(目標炭水化物量 / 白米単位量あたりの炭水化物量) * 白米単位量 = 必要な白米量<br>
(176.4 / 77.6) * 100 = 227.3 [g]
</div>

沼に入れる白米の量が決まったので、この白米から摂れるたんぱく質、脂質を計算します。
計算式は前節と同様です。

- たんぱく質 : 13.9g
- 脂質 : 2.0g


## 5. 皮無し鶏むね肉の計算

白米の量に続いて、皮無し鶏むね肉の量を計算します。
2節で求めた沼で摂取したい各栄養素の量から、白米の栄養素を引き算をすることで、残りの必要な栄養素量が計算できます。

- たんぱく質 : 63.9 [g]
- 脂質 : 15.4 [g]
- （クリア！）炭水化物 : 0 [g]

皮無し鶏むね肉100gあたり栄養素は以下の通りです。

- たんぱく質 : 24.4 [g]
- 脂質 : 1.9 [g]
- 炭水化物 : 0 [g]

ここから、必要なたんぱく質量を満たす皮無し鶏むね肉の量を計算します。

<div class="highlight">
(目標たんぱく質量 / 鶏むね肉単位量あたりのたんぱく質量) * 鶏むね肉単位量 = 必要な鶏むね肉量<br>
(63.9 / 24.4) * 100 = 261.9 [g]
</div>

皮無し鶏むね肉は脂質も含んでいますので、その量を計算します。

- 脂質 : 5.0g


## 6. 足りない脂質量の計算

ここまでの計算で、白米で炭水化物を、鶏むね肉でたんぱく質量を満たしていますが、
それぞれとても低脂質な食品のため、このままだと脂質が20%に届きません。

最後に、必要な残りの脂質量を計算します。

<div class="highlight">
沼から摂取する脂質 - 白米の脂質 - 鶏むね肉の脂質<br>
17.4 - 2.0 - 5.0 = 10.4 [g]
</div>

この10.4gの脂質をなんらかの食材で補えば、目標のPFCバランスが完成します。
[取り除いた鶏皮から採った鶏油](https://www.youtube.com/watch?v=MT3p04phfJA)を沼にかけたり、
[チョコを食べたり](https://www.youtube.com/watch?v=mL7W2YrmXHs&feature=youtu.be&t=637)して脂質を補いましょう。

なお、もしここで計算結果がマイナスとなってしまう場合は、2節のサブ食材・サプリメントから摂取する脂質量が多いものと考えられます。
その場合は量を見直し、2節から再計算を行います。


## 脚注

計算に使用している各食材の栄養素は、
特に但し書きの無い限り文部科学省発行の「日本食品標準成分表2015年版（七訂）」、
およびこれを元にした「食品成分データベース」より引用しています。

- 日本食品標準成分表2015年版（七訂）<br>
  https://www.mext.go.jp/a_menu/syokuhinseibun/1365295.htm
- 食品成分データベース<br>
  https://fooddb.mext.go.jp/
