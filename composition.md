# 對組字來看

組字著是 qaw 幾若个漢字部件組成一个漢字. 譬喻講「口包口」會組成「回」, 「口併口」會組成「吅」, 「口疊口」會組成「吕」, 「口併口托口」會組成「品」等等.

組一个漢字組 ew 組字, diurff 是 qaw 一个漢字序列組成一个漢字組. 組一个漢字 ew 組字, diurff 是 qaw 一个部件序列組成一个漢字. Ze 兩種組字所用 ew 方法是仝款 ew.

廈英大辭典內底有定義字母 diurff 是一个 word ew radical, diurff 是 alphabet ew letter.

## 品詞

一句「Kau vauzs kauy」diurff ewtangy 用頭一个口 qaw 第二个口包 kifflaih. 其中兩个口 long 是名詞, ahh 包是動詞. 頭一个口是名詞做主語, 第二个口是名詞做賓語. 一般咱所講 ew 電腦語言並無品詞 ew 概念. 品詞 ewtangy 用 enumeration 來設定, 譬喻講動詞是`1`, 名詞是`2`.

## 變調組

系列「口包口」有四種台語讀音:

1. `Kau vauzs kauy`
2. `Kauy` `vau` `kauy`
3. `Kau vau` `kauy`
4. `Kauy` `vauzs kauy`

頭一種是三个單語成做一个變調組, 因為主語有變調, 動詞有變調, 賓語無變調. 第二種是三个單語成做三个變調組, 一組一語, 因為主語是原調, 動詞是原調, 賓語是原調. 第三種是三个單語成做兩个變調組, 頭前一組有兩語, 後壁一組有一語. 第四種是三个單語成做兩个變調組, 頭前一組有一語, 後壁一組有兩語.

## 句

一个變調組 diurff 是一句, diurff 是一个 phrase. 一句 qurhh ewtangy 用品詞 qaw 分做幾若句. 譬喻講漢字序列「浸磺水」若讀做`zimy hongzszuiy`, `zimy hongzszuiy`diurff 是一句, 動詞`zimy`maw 是一句, 名詞`hongzszuiy`maw 是一句. qurhh 舉一例. 漢字序列「哺檳榔」若讀做`vow vinzsnngx`, 伊總共有三句. `vow`是一句, `vinzsnngx`是一句, `vow vinzsnngx` maw 是一句. 頂一節變調組所列 ew 四種「口包口」讀音, 逐種 long 有四句. 變調組本身是一句, 兩个名詞是兩句, 一个動詞是一句, 所以 long 總四句.

## 句 ew 處理

咱來看一 ezs khahh 長 ew 例. 系列「口併口托口」有三个口是名詞, 一个併一个托 long 是動詞. 所以「口併口托口」是 ansszuann 組成「品」ew？首先咱 ewtangy 用 phrase detector 來處理`kau vingy kau tuhy kauy`. Phrase detector ewtangy 偵測`kau vingy kau tuhy kauy`內底 long 總有幾若句, qurhh qaw 偵測結果回傳. 偵測是以變調組做偵測單位:

```
phraseDetector = PhraseDectector.new()
detectedPhrases = pd.detect("kau pingy kau tuh kauy")
```

頂 quanx ew`phraseDetector`會偵測 diurff 一 ezs phrase. 紲 lurfflaih ewtangy qaw 偵測結果送 how phrase evaluator 處理:

```
phraseEvaluator = PhraseEvaluator.new()
actions = pe.evaluate(detectedPhrases)
```

Phrase evaluator 回傳 ew 是`actions`, 也 diurff 是動詞`vingy`對伊頭前 ew 名詞`kau`qahh 伊後壁 ew 名詞`kau`所施加 ew 動作, qurhh 加上`tuhy`對伊頭前 ew`kau`qahh 伊後壁 ew`kauy`施加 ew 動作. `vingy`對頭前 ew`kau`會產生一个動作, `vingy`對後壁 ew`kau`會產生第二个動作. `tuhy`對頭前 ew`kau vingy kau`會產生第三个動作, `tuhy`對後壁 ew`kauy`會產生第四个動作. 所以 long 總有四个動作, 也 diurff 是有四个 action.

咱 ewtangy 設定頭一个 action 是 qaw 口縮小. 第二个 action 是 qaw 口放大. 因為`vingy`有 qay 主語 qahh 賓語, 所以會 qaw 分別放大 qahh 縮小 ew 口合併 kifflaih. 第三个 action 是 qaw`kau vingpy kau`徙去下腳. 第四个 action 是 qaw`kauy`徙去頂 quanx. 因為`tuhy`有 qay 主語 qahh 賓語, 所以會用下腳 ew 吅 qaw 頂 quanx ew 口托 kifflaih. Anssne「品」diurff 組 kifflaihiaw.

## 用 Parser 做句 ew 處理

頂 quanx 變調組 hitt 節內底 「口包口」ew 第三个讀音 ewtangy 用 parser 來處理. 一个變調組 diurff 是一个 node. 若是拄 diurff 一个動詞是單獨一 ezs 變調組, ewtangy qaw zitt 个動詞囥 diw internal node.

## Expression

Expression 是表現或者是表現式 ew 意思. Zitt 句 "kau vauzs kauy" 若無用品詞 ew 角度去 qahh 看, 伊 qannzsnannzs 是一个單語 ew 序列, maw ewdangy 講是一个表現. 若是 qaw zitt 句 "kau vauzs kauy" 用品詞 ew 角度去 qahh 看, "kau" qahh "kauy" 是名詞, "vauzs" 是動詞, "kau vauzs kauy" zitt 句 diurff 變做表現式, maw 是一个單語系列. 因為名詞 "kau" qahh "kauy" ewdangy qaw 看做 operand, 動詞 "vauzs" ewdangy qaw 看做 operator.
