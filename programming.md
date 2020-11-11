# Iongw 台語文 Sia 程式 ew 方法

電腦語言 ew 分類方式 uw chinz chew 欵, uw iongw 世代 laiz 分 e, uw iongw paradigm laiz 分 e, uw iongw kuanzkez laiz 分 e, kahf 其他 kokfchiong 分類. Sofuiw ew 程式語言, siw 電腦語言 ew 其中一種. Tiw chia so kongy ew iongw 台語文 sia 程式 pingw burz kiokwhanw tiw 程式語言內底. Inzuiw 所有 ew 電腦語言, pauzkhuatf 程式語言, script 語言, markup 語言等等, long uw 一 ez 共同 ez 特性, 一 ez 共同抽象化 ew 方式. Chitf ez 共同抽象化 ew 方式 tufuafhury ewtangy camz 台語 ew 造語機制結合. Sofi 下脚 ew ki chitwkua 無仝欵 ew 電腦語言 laiz chury 例, laiz khuanny inz uw siannfmihf 共同 ew 特性.

Tiw 語言學內底 uw sofuiw ew 同形異音語, 英語 hurw churhy heteronym. Pi 同形異音語 kurhf khahf 幼路 ew 分類 siw 同形異音異義語. 譬喻 kongy, 英語 bow naw thakw churhy `/boʊ/` tiurhw siw chi `弓`, naw thakw churhy `/baʊ/` siw chi `船頭`. 仝一 ez bow uw 二 ez 無仝欵 ew 發音, 二 ez 無仝欵 ew 發音 kurhf piaufsiw 二 ez 無仝欵 ew 意思:

| | bow | |
| :--- | :--- | :--- |
| 1 | /boʊ/ | 弓 |
| 2 | /baʊ/ | 船頭, 鞠躬 |

英語內底 ew 同形異音異義語 kurhf 有 lead 若讀做`/liːd/`siw`引𤆬` ew 意思, naw thakw churhy`/lɛd/`siw chi`鉛`; Row 若讀做`/roʊ/`kahf 讀做`/raʊ/`maw 是無仝欵 ew 意思.

台語 kanwkhuan maw uw 同形異音語, 譬喻 kong 加 naw siw thakw churhy `ka`, tiurhw siw `時間增加` ew 加, chitf 句 ka tiw 英語內底 ew 意思 siw `increase`. 加 naw thakw churhy `ke`, tiurhw siw `加一點鐘` ew ke, chitf 句 ke tiw 英語內底 ew 意思是 `add`:

| | 加 | |
| :--- | :--- | :--- |
| 1 | ka | increase |
| 2 | ke | add |

Tiw chia aiy tietwpietw 注意 ew siw, ka mw siw khienypaiy long huanzekw churhy increase, ke maw mw siw ingfuan long huanzekw churhy add. 翻譯 siw lingwguaw 一門學問, mw siw chitf pun 冊 ew 主題. 我 tiw tingfkuanz 表格內底 so 舉 ew 例, tiurhw siw hanwtingw tiw 時間增加 kahf 加一點鐘 chitf 二句內底 chiahf 成立. 時間增加 kahf 加一點鐘 tiurhw siw siw gua behf 使用 ew context.

Ciunnw bow chitf 字 uw 二个意思 - 一个 siw 弓, 一个 siw 船頭, tiurhw siw uw 二个定義, tiurhw siw uw 二 ez definition. Tiurhw cinzciunnw 一 lipw suanw 石 ew 二 ez facet ew 意思仝欵.

Naw anfne lan kaw 程式語言內底 ew 文 tongy churhy siw 加 ew 一个定義, `increase()` chitf ez 文 tiurhw ewtangy khngy jipwkhi 表格內底頭一行, kahf `increase` 仝欵做加 ew 一个定義. `add()` maw siw ewtangy khngy jipwkhi 表格內底第二行 chury 加 ew 第二个定義:

| | 加 | | |
| :--- | :--- | :--- | :--- |
| 1 | ka | increase | def increase end |
| 2 | ke | add | add |

Lan naw siw kurhf kaw 文 hunz churhy function-block kahf function-call che 二種 laiz 看, `increase();` tiurhw siw function-call, `increase(){}` tiurhw siw function-block:

| | 加 | |
| :--- | :--- | :--- |
| 1 | ka | increase |
| 2 | | def increase end |

## 有用台語文寫程式

Lan kurhf laiz khuanny 下脚 ew 表格. 單語 notify siw 告示, 通知 ew 意思, lan thehw 告示 ew 示 chitf 字 laiz 用. Ahf print siw 印 ew 意思. Lan kaw `def notify end` 文 sietftingw churhy 示 ew 頭一个定義:

| | 示 | |
| :--- | :--- | :--- |
| 1 | siz | def notify end |

Kaw `printToPdf` 文 sietftingw churhy 印 ew 頭一个定義, `printToPaper` sietftingw churhy 第二个定義. Sofi 印 uw 二个定義:

| | 印 | |
| :--- | :--- | :--- |
| 1 | inw | printToPdf |
| 2 | | printToPaper |

紲 lurhwlaih lan ewtangy kaw 示 camz 印 tauhy churhy 一字, tiurhw siw `siwinw`:

```ruby
#
# siwinw
#
def notify
  printToPdf
end
```

為啥乜 `def notify end` siw kaw 印 ew 頭一个定義 `printToPdf` 嵌 lipwkhih, mw siw kaw 第二个 neh? Inzuiw lan ewtangy tiw context 內底設定 behf cufiongw turhf 一个定義 laiz how `def notify end` 嵌 leh:

```ruby
context.add([_si, _in, 1])
```

Tingfkuanx ez 函數 piaufsiw 示 behf thehw 印 ew 頭一个定義 laiz kaz 嵌 leh. `context.add` piaufsiw tiw context 內底 chingzkaz 一項, hekwchiafsiw chingzkaz 一 hangw 選用規則 ew 意思.

為啥乜 `def notify end` ewtangy kaw `printToPdf` 嵌 lipwkhih? Inzuiw 示印 naw sia churhy `siwinw`, piaufsiw siz kahf inw siw iongw 變調造語 lienzkietf churhy 一个單語. 示印 naw sia churhy `siz inw`, piaufsiw siz kahf inw siw 二 ez 分別 ew 單語. Sofi sia churhy `siz inw` ew 示印, piaufsiw `def notify end` kahf `printToPdf` siw 並列 ew 關係:

```ruby
#
# siz inw
#
def notify
end

printToPdf
```

Tiw 台語文程式設計內底, jimwhurz 二个文 ew 組合 naw mw siw 嵌入 tiurhw siw 並列.
