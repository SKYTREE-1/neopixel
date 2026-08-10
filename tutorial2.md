# micro:bit × NeoPixel（4球 I型）チュートリアル
```package
neopixel=github:microsoft/pxt-neopixel
```

## 光る！カラフル・ライトバーをつくろう@showdialog
この活動では、micro:bitとテープLEDを使って、自分だけのカラフルなライトバーを作ります。LEDの色や光り方をプログラミングで自由に変えることで、光のしくみやコンピュータの命令の考え方を楽しく学びましょう。

![NeoPixelの写真](images/img_neopixel.png)

---

## 1. 接続しよう@showdialog

まず、テープLED と micro:bit を接続しましょう。

**配線**
- micro:bit → テープLED（NeoPixel）  
  - 3V → VCC  
  - GND → GND  
  - P0 → DIN  

👉 赤い線は電気、黒か緑の線はマイナス、それ以外の線は信号  

![配線図](images/img_wiring.png)

---

## テープLEDを光らせよう1　LEDの個数の設定
``||neopixel: NeoPixel ||`` にある ``||basic:最初だけ||``にいれて、「24」とかいてあるところを「4」にかえます。  

   ```blocks
   let strip = neopixel.create(DigitalPin.P0, 4, NeoPixelMode.RGB)
   ```

## テープLEDを光らせよう2　全部赤で光らせる
``||input:入力||``から``||input:ボタンAが押されたとき||``をだして、``||neopixel:strip を赤色に点灯する||``をいれる。

   ```blocks
   input.onButtonPressed(Button.A, function () {
    strip.showColor(neopixel.colors(NeoPixelColors.Red))
})
let strip: neopixel.Strip = null
   ```


## テープLEDを光らせよう3　テスト@showdialog
ここまでのプログラムができたら、micro:bit にダウンロードして動かしてみよう。

   ```blocks
   input.onButtonPressed(Button.A, function () {
    strip.showColor(neopixel.colors(NeoPixelColors.Red))
    })
    let strip: neopixel.Strip = null
    strip = neopixel.create(DigitalPin.P0, 4, NeoPixelMode.RGB)
    basic.forever(function () {	

    })
  ```

## テープLEDを光らせよう3　テスト

できたら、Aボタンを押したときに、ほかの色が光るようにプログラムを変更してみよう。
また、色を順番に変えるにはどうしたらいいかを考えてみよう。


## もっとテープLEDを光らせよう 1 点滅（説明）　@showdialog
次に、LED全体を点滅（てんめつ）させてみましょう。
点滅の動きは、点灯　→　消灯　→　点灯　→　消灯 ... のように10回つけて、最後に消えるようにします。

![NeoPixelの点滅](images/img_f1.png)

まず、自分で考えた方法を試してから、次に進みましょう！

## もっとテープLEDを光らせよう ２ くりかえす
``||input:ボタンAが押されたとき||`` に ``||loops:ループ||`` にある、``||loops:くりかえし（4）回||`` を入れ4 を 10にかえて10回にする

```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 10; index++) {
    	
    }
    strip.showColor(neopixel.colors(NeoPixelColors.Red))
})
let strip: neopixel.Strip = null
```
## もっとテープLEDを光らせよう 3 くりかえす　
``||loops:くりかえし10回||`` に、``||neopixel:strip を赤色に点灯する||`` を入れ、そのあとに、もうひとつ ``||neopixel:strip を赤色に点灯する||`` を入れ、「赤」を「black」にかえます。**black** は **消す** という意味です。

```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 10; index++) {
        strip.showColor(neopixel.colors(NeoPixelColors.Red))
        strip.showColor(neopixel.colors(NeoPixelColors.Black))
    }
})
let strip: neopixel.Strip = null
```
## もっとテープLEDを光らせよう 4 テスト @showdialog
ここまでできたら、micro:bit にダウンロードして実際に動かしてみましょう。


```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 10; index++) {
        strip.showColor(neopixel.colors(NeoPixelColors.Red))
        strip.showColor(neopixel.colors(NeoPixelColors.Black))
    }
})
let strip: neopixel.Strip = null
```
## もっとテープLEDを光らせよう 4 テスト
ついたり、きえたり、しましたか？　もし、考えた通りに動かなかったら「どうしてか」考えてみてください。

## もっとテープLEDを光らせよう 5　ポーズ
``||neopixel:strip を赤色に点灯する||`` と ``||neopixel:strip をblack色に点灯する||`` の後に、それぞれ、``||basic:基本||`` の``||basic:一時停止（ミリ秒） 100||`` をいれ、「100」 を「500」にかえる。

```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 10; index++) {
        strip.showColor(neopixel.colors(NeoPixelColors.Red))
        basic.pause(500)
        strip.showColor(neopixel.colors(NeoPixelColors.Black))
        basic.pause(500)
    }
})
let strip: neopixel.Strip = null
strip = neopixel.create(DigitalPin.P0, 4, NeoPixelMode.RGB)
```

## もっとテープLEDを光らせよう 6 テスト @showdialog
ここまでできたら、micro:bit にダウンロードして実際に動かしてみましょう。



### ここまでのプログラム
```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 10; index++) {
        strip.showColor(neopixel.colors(NeoPixelColors.Red))
        basic.pause(500)
        strip.showColor(neopixel.colors(NeoPixelColors.Black))
        basic.pause(500)
    }
})
let strip: neopixel.Strip = null
strip = neopixel.create(DigitalPin.P0, 4, NeoPixelMode.RGB)
```
## もっとテープLEDを光らせよう 6 テスト
ついたり、きえたりすることを確認したら、早く点滅させたり、ゆっくり点滅させたり、点滅の回数を増やしたりしてみてください。

## ライトウェーブ（説明）　 @showdialog

### 🌀 光の流れを操れ！

この活動では、micro:bitとNeoPixel（4個）を使って、光が流れるように見える「ライトウェーブ」を作ります。
✨スピードを変えたり、色を変えたり、リズムに合わせて光らせるても楽しいです。

はじめに、LEDの番号について確認しましょう。以下のように、micro:bit に近い方から、0番目、1番目、...のように数えます。


![流れる光のイメージ](images/img_flowing.png)

## ライトウェーブ１
``||input:入力||`` から ``||input:ゆさぶられたとき||`` をだして、``||neopixel:NeoPixel||`` のその他にある ``||neopixel:strip の（0）番目を[赤]色に設定する||`` を、いれる。０番目は、一番 micro:bit に近いLEDのことです。（色は自由に変更していいです。）

```blocks
input.onGesture(Gesture.Shake, function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Red))
})
let strip: neopixel.Strip = null
```


## ライトウェーブ２
同じように``||neopixel:strip の（0）番目を[赤]色に設定する||`` を使って、１番目～３番目のLEDの色を設定してください。色は自由に決めてください。

```blocks
input.onGesture(Gesture.Shake, function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Yellow))
    strip.setPixelColor(1, neopixel.colors(NeoPixelColors.Green))
    strip.setPixelColor(2, neopixel.colors(NeoPixelColors.Blue))
    strip.setPixelColor(3, neopixel.colors(NeoPixelColors.Violet))
})
let strip: neopixel.Strip = null
```

## ライトウェーブ3
４つのLEDの色を設定したら、``||neopixel:NeoPixel||``　の ``||neopixel:strip を設定した色で点灯する||`` を``||input:ゆさぶられたとき||`` の一番下に追加する。

```blocks
input.onGesture(Gesture.Shake, function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Yellow))
    strip.setPixelColor(1, neopixel.colors(NeoPixelColors.Green))
    strip.setPixelColor(2, neopixel.colors(NeoPixelColors.Blue))
    strip.setPixelColor(3, neopixel.colors(NeoPixelColors.Violet))
    strip.show()
})
let strip: neopixel.Strip = null
```
## ライトウェーブ4 テスト @showdialog
ここまでできたら、micro:bit にダウンロードして実際に動かしてみましょう。
設定した色で光らせることができたら、次へ進みます。次は、設定した色を順番に変えていきます。

### ここまでのプログラム
```blocks
input.onGesture(Gesture.Shake, function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Yellow))
    strip.setPixelColor(1, neopixel.colors(NeoPixelColors.Green))
    strip.setPixelColor(2, neopixel.colors(NeoPixelColors.Blue))
    strip.setPixelColor(3, neopixel.colors(NeoPixelColors.Violet))
    strip.show()
})
let strip: neopixel.Strip = null
strip = neopixel.create(DigitalPin.P0, 4, NeoPixelMode.RGB)
```

## ライトウェーブ5
``||input:ゆさぶられたとき||`` の一番下に　``||loops:ループ||`` の ``||loops:くりかえし（4）回||`` をいれる。
```blocks
input.onGesture(Gesture.Shake, function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Yellow))
    strip.setPixelColor(1, neopixel.colors(NeoPixelColors.Green))
    strip.setPixelColor(2, neopixel.colors(NeoPixelColors.Blue))
    strip.setPixelColor(3, neopixel.colors(NeoPixelColors.Violet))
    strip.show()
    for (let index = 0; index < 4; index++) {
       
    }
})
```

## ライトウェーブ6
追加した  ``||loops:くりかえし（4）回||`` の中に ``||neopixel:NeoPixel||``　の ``||neopixel:strip に設定されている色をLED（1）個分ずらす（ひとまわり）||`` と``||neopixel:strip を設定した色で点灯する||`` をいれる。そして、``||basic:一時停止（ミリ秒） 100||`` をいれ、「100」 を「500」にかえる。

```blocks
input.onGesture(Gesture.Shake, function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Yellow))
    strip.setPixelColor(1, neopixel.colors(NeoPixelColors.Green))
    strip.setPixelColor(2, neopixel.colors(NeoPixelColors.Blue))
    strip.setPixelColor(3, neopixel.colors(NeoPixelColors.Violet))
    strip.show()
    for (let index = 0; index < 4; index++) {
        strip.rotate(1)
        strip.show()
    }
})
let strip: neopixel.Strip = null
```
## ライトウェーブ7
追加した  ``||loops:くりかえし（4）回||`` の中の一番下に、``||basic:一時停止（ミリ秒） 100||`` をいれ、「100」 を「500」にかえる。

```blocks
input.onGesture(Gesture.Shake, function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Yellow))
    strip.setPixelColor(1, neopixel.colors(NeoPixelColors.Green))
    strip.setPixelColor(2, neopixel.colors(NeoPixelColors.Blue))
    strip.setPixelColor(3, neopixel.colors(NeoPixelColors.Violet))
    strip.show()
    for (let index = 0; index < 4; index++) {
        strip.rotate(1)
        strip.show()
        basic.pause(500)
    }
})
let strip: neopixel.Strip = null
```
## ライトウェーブ4 テスト @showdialog
ここまでできたら、micro:bit にダウンロードして実際に動かしてみましょう。
光の色が動くことを確認できたら、色を変えたり、動くスピードを変えて自由に光らせてみよう。

### ここまでのプログラム
```blocks
input.onGesture(Gesture.Shake, function () {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Yellow))
    strip.setPixelColor(1, neopixel.colors(NeoPixelColors.Green))
    strip.setPixelColor(2, neopixel.colors(NeoPixelColors.Blue))
    strip.setPixelColor(3, neopixel.colors(NeoPixelColors.Violet))
    strip.show()
    for (let index = 0; index < 4; index++) {
        strip.rotate(1)
        strip.show()
        basic.pause(500)
    }
})
let strip: neopixel.Strip = null
strip = neopixel.create(DigitalPin.P0, 4, NeoPixelMode.RGB)
```

## 💡 点滅（交互に光る）@showdialog

### 参考：ひとつおきに、を交互に光らせる。

次のプログラムは「画面を下にしたとき」交互についたり、きえたりするプログラムです。
ほかにも、いろいろなパターンで光らせたり、色を変えたり、うごかしたりすることができます。

![交互点滅のイメージ](images/img_blink.png)

```blocks
input.onGesture(Gesture.ScreenDown, function () {
    for (let index = 0; index < 10; index++) {
        strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Blue))
        strip.setPixelColor(1, neopixel.colors(NeoPixelColors.Black))
        strip.setPixelColor(2, neopixel.colors(NeoPixelColors.Blue))
        strip.setPixelColor(3, neopixel.colors(NeoPixelColors.Black))
        strip.show()
        basic.pause(500)
        strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Black))
        strip.setPixelColor(1, neopixel.colors(NeoPixelColors.Blue))
        strip.setPixelColor(2, neopixel.colors(NeoPixelColors.Black))
        strip.setPixelColor(3, neopixel.colors(NeoPixelColors.Blue))
        strip.show()
        basic.pause(500)
    }
})
let strip: neopixel.Strip = null
```


---

## 4. もっと工夫しよう（自由な活動・15分）@showdialog

さいごは、じぶんのすきな色や光りかたをつかって、じゆうにあそんでみよう！

たとえば…

🔄「じゅんばんに色がかわるライト」 　→ 赤→青→みどり→黄色…と、色がながれるように光らせるよ！

🎵「おんがくにあわせて光るライト」 　→ すきなうたにあわせて、ピカピカ光るようにしてみよう！

💬「メッセージライト」 　→ うれしい気もちのときはピンク、がんばるぞ！のときは赤など、気もちを色であらわしてみよう！

🌀「まほうのライト」 　→ ボタンをおすと、ひみつの色が出てくる！どんな色になるかはおたのしみ♪

じぶんで色やうごきをえらんで、オリジナルのライトをつくると、まるで光のアーティストみたい✨ おともだちと見せあったり、いっしょにアイデアを出しても楽しいよ！

![子どもたちが活動している](images/img_presentation.png)

---

## 5. まとめ（5分）@showdialog

* 今日できたこと：

  * NeoPixelを「つないだ」
  * 色を「自由に変えた」
  * 「順番や点滅」で動きを作った
  * オリジナルパターンを作った

* 次の発展例：
  * LEDを増やして光らせる
  * 音やセンサーと組み合わせる

---

*Credits: The illustrations used in this tutorial were generated with OpenAI's image generation tools.*

<script src="https://cdn.jsdelivr.net/gh/jp-rad/pxt-ubit-extension@0.5.0/.github/statics/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", ["neopixel=github:microsoft/pxt-neopixel",]);</script>
