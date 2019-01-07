# 對組字來看

組字着是 qaw 幾若 ezs 漢字部件組成一 ezs 漢字. 譬喻 qong "口包口" ew 組成 "回", "口併口" ew 組成 "吅", "口疊口" ew 組成 "吕", "口併口托口" ew 組成 "品" 等等.

組一 ezs 漢字組 ew 組字, diurff 是 qaw 一 ezs 漢字序列組成一 ezs 漢字組. 組一 ezs 漢字 ew 組字, diurff 是 qaw 一 ezs 部件序列組成一 ezs 漢字. Ze 兩種組字 so iongzs ew 方法是 qangw 欵 ew.

## 品詞

一句 "kau vauzs kauy" diurff ewdangy 用頭一 ezs 口 qaw 第二 ezs 口包 kifflaih. 其中兩 ezs 口 long 是名詞, ahh 包 siw 動詞. 頭一 ezs 口 siw 名詞 zury 主語, 第二 ezs 口 siw 名詞 zury 目的語. 一般 lan so qongy ew 電腦語言 vingw burzs 品詞 ew 概念. 品詞 ewdangy 用 enumeration laizs 設定, 譬喻 qong 動詞 siw`1`, 名詞 siw`2`.

## 變調組

系列「口包口」有四種台語讀音:

1. `Kau vauzs kauy`
2. `Kauy` `vau` `kauy`
3. `Kau vau` `kauy`
4. `Kauy` `vauzs kauy`

頭一種 siw 三 ezs 單語成 zury 一 ezs 變調組, inzsuiw 主語 uw 變調, 動詞 uw 變調, 目的語 burzs 變調. 第二種 siw 三 ezs 單語成做三 ezs 變調組, 一組一語, inzsuiw 主語 siw 原調, 動詞 siw 原調, 目的語 siw 原調. 第三種 siw 三ezs 單語成 zury 兩 ezs 變調組, 頭前一組 uw 二語, 後壁一組 uw 一語. 第四種 siw 三 ezs 單語成 zury 兩 ezs 變調組, 頭前一組 uw 一語, 後壁一組 uw 二語.

## 句

一 ezs 變調組 diurff siw 一句, diurff 是一个 phrase. 一句 qurhh ewtangy iongw 品詞 qazs 分做 quissnaw 句. 譬喻 qong 漢字序列 "浸磺水" naw 讀 zury `zimy hongzszuiy`, `zimy hongzszuiy`diurff 是一句, 動詞`zimy`maw 是一句, 名詞`hongzszuiy`maw 是一句. Qurhh 舉一例. 漢字序列 "哺檳榔" naw 讀 zury`vow vinzsnngx`, izs 總共 uw 三句. `vow`siw 一句, `vinzsnngx`siw 一句, `vow vinzsnngx` maw siw 一句. 頂一節變調組所列 ew 四種「口包口」讀音, 逐種 long uw 四句. 變調組本身是一句, 兩个名詞是兩句, 一个動詞是一句, 所以 longsszong 四句.

## Iongw dependency parser zury 句 ew 處理

Lan laizs 看一 ezs kahh 長 ew 例. 系列「口併口托口」有三 ezs 口是名詞, 一 ezs 併 qahh 一 ezs 托 long siw 動詞. 所以 "口併口托口" siw ansszuann 組成 "品" ew？首先 lan ewdangy iongw phrase detector 來處理`kau vingy kau tuhy kauy`. Phrase detector ewdangy 偵測`kau vingy kau tuhy kauy`內底 longsszongy uw quissnaw 句, qurhh qaw 偵測結果回傳. 偵測 siw i 變調組 zury 偵測單位:

```
phraseDetector = PhraseDectector.new()
detectedPhrases = pd.detect("kau pingy kau tuh kauy")
```

頂 quanx ew`phraseDetector`會偵測 diurff 一 ezs phrase. 紲 lurfflaih ewdangy qaw 偵測結果送 how phrase evaluator 處理:

```
phraseEvaluator = PhraseEvaluator.new()
actions = pe.evaluate(detectedPhrases)
```

Phrase evaluator 回傳 ew siw`actions`, iaw diurff siw 動詞`vingy`duiy izs 頭前 ew 名詞`kau`qahh izs 後壁 ew 名詞`kau`so 施加 ew 動作, qurhh 加上`tuhy`duiy izs 頭前 ew`kau`qahh 伊後壁 ew`kauy`施加 ew 動作. `vingy`duiy頭前 ew`kau`ew 產生一 ezs 動作, `vingy`duiy 後壁 ew`kau`ew 產生第二 ezs 動作. `tuhy`duiy 頭前 ew`kau vingy kau`ew 產生第三 ezs 動作, `tuhy`duiy 後壁 ew`kauy`ew 產生第四 ezs 動作. 所以 longsszongy uw 四 ezs 動作, iaw diurff siw uw 四 ezs action.

咱 ewdangy 設定頭一 ezs action siw qaw 口縮小. 第二 ezs action 是 qaw 口放大. Inzsuiw `vingy`uw qahy 主語 qahh 目的語, 所以 ew qaw 分別放大 qahh 縮小 ew 口合併 kifflaih. 第三 ezs action siw qaw`kau vingpy kau`徙 ki 下脚. 第四 ezs action siw qaw`kauy`徙 ki 頂 quanx. Inzsuiw`tuhy`有 qahy 主語 qahh 目的語, 所以 ew iongw 下脚 ew 吅 qaw 頂 quanx ew 口托 kifflaih. Anssne「品」diurff 組 kifflaih iaw.

Ze siw liwiongw dependency parser ew 作法, qahh 進前 Shunting Yard parser ew 作法 burzs 仝.

## Expression

Expression siw 表達或者是表達式 ew 意思. Zitt 句 "kau vauzs kauy" naw burzs iongw 品詞 ew 角度 ki qazs 看, izs qannzsnazs siw 一 ezs 單語 ew 序列, maw ewdangy qong siw 一 ezs 表達. Naw siw qaw zitt 句 "kau vauzs kauy" iongw 品詞 ew 角度 ki qazs 看, "kau" qahh "kauy" siw 名詞, "vauzs" siw 動詞, "kau vauzs kauy" zitt 句 diurff 變 zury 表達式, maw siw 一 ezs 單語系列. 因為名詞 "kau" qahh "kauy" ewdangy qazs 看 zury operand, 動詞 "vauzs" ewdangy qazs 看 zury operator.
