# Iongw 台語文 Sia 程式 ew 方法

電腦語言 ew 分類方式 uw chinz chew 欵, uw iongw 世代 laiz 分 e, uw iongw paradigm laiz 分 e, uw iongw qoanzqez laiz 分 e, qahf 其他 qokfchiong 分類. Sosfuiw ew 程式語言, siw 電腦語言 ew 其中一種. Diw chia so qongy ew iongw 台語文 sia 程式 vengw burz qiokkwhanw diw 程式語言內底. Inzuiw 所有 ew 電腦語言, vauzkoatf 程式語言, script 語言, markup 語言等等, long uw 一 ez 共同 ez 特性, 一 ez 共同抽象化 ew 方式. Chitf ez 共同抽象化 ew 方式 dusfoasfhury ewdangy camz 台語 ew 造語機制結合. Sosfi 下脚 ew qi chittwqoa 無仝欵 ew 電腦語言 laiz chury 例, laiz koanny inz uw siannsfmihf 共同 ew 特性.

Diw 語言學內底 uw sosfuiw ew 同形異音語, 英語 hurw chury heteronym. Vi 同形異音語 qurhf kahf 幼路 ew 分類 siw 同形異音異義語. 譬喻 qongy, 英語 bow naw thakkw chury `/boʊ/` diurhhw siw chi `弓`, naw takkw chury `/baʊ/` siw chi `船頭`. 仝一 ez bow uw 二 ez 無仝欵 ew 發音, 二 ez 無仝欵 ew 發音 qurhf viausfsiw 二 ez 無仝欵 ew 意思:

| | bow | |
| :--- | :--- | :--- |
| 1 | /boʊ/ | 弓 |
| 2 | /baʊ/ | 船頭, 鞠躬 |

英語內底 ew 同形異音異義語 qurhf 有 lead 若讀做`/liːd/`siw`引𤆬` ew 意思, naw takkw chury`/lɛd/`siw chi`鉛`; Row 若讀做`/roʊ/`qahf 讀做`/raʊ/`maw 是無仝欵 ew 意思.

台語 qanwkoan maw uw 同形異音語, 譬喻 qong 加 naw siw takkw chury `qa`, diurhhw siw `時間增加` ew 加, chitf 句 qa diw 英語內底 ew 意思 siw `increase`. 加 naw takkw chury `qe`, diurhhw siw `加一點鐘` ew qe, chitf 句 qe diw 英語內底 ew 意思是 `add`:

| | 加 | |
| :--- | :--- | :--- |
| 1 | qa | increase |
| 2 | qe | add |

Diw chia aiy diettwviettw 注意 ew siw, qa mw siw kienyvaiy long hoanzekkw chury increase, qe maw mw siw engsfoan long hoanzekkw chury add. 翻譯 siw lengwgoaw 一門學問, mw siw chitf vun 冊 ew 主題. 我 diw dengsfqoanz 表格內底 so 舉 ew 例, diurhhw siw hanwdengw diw 時間增加 qahf 加一點鐘 chitf 二句內底 chiahf 成立. 時間增加 qahf 加一點鐘 diurhhw siw siw goa behf 使用 ew context.

Ciunnw bow chitf 字 uw 二个意思 - 一个 siw 弓, 一个 siw 船頭, diurhhw siw uw 二个定義, diurhhw siw uw 二 ez definition. Diurhhw cinzciunnw 一 lippw soanw 石 ew 二 ez facet ew 意思仝欵.

Naw ansfne lan qaw 程式語言內底 ew 文 dongy chury siw 加 ew 一个定義, `increase()` chitf ez 文 diurhhw ewdangy kngy jippwki 表格內底頭一行, qahf `increase` 仝欵做加 ew 一个定義. `add()` maw siw ewdangy kngy jippwki 表格內底第二行 chury 加 ew 第二个定義:

| | 加 | | |
| :--- | :--- | :--- | :--- |
| 1 | qa | increase | def increase end |
| 2 | qe | add | add |

Lan naw siw qurhf qaw 文 hunz chury function-block qahf function-call che 二種 laiz 看, `increase();` diurhhw siw function-call, `increase(){}` diurhhw siw function-block:

| | 加 | |
| :--- | :--- | :--- |
| 1 | qa | increase |
| 2 | | def increase end |

## 有用台語文寫程式

Lan qurhf laiz koanny 下脚 ew 表格. 單語 notify siw 告示, 通知 ew 意思, lan tehhw 告示 ew 示 chitf 字 laiz 用. Ahf print siw 印 ew 意思. Lan qaw `def notify end` 文 sietfdengw chury 示 ew 頭一个定義:

| | 示 | |
| :--- | :--- | :--- |
| 1 | siz | def notify end |

Qaw `printToPdf` 文 sietfdengw chury 印 ew 頭一个定義, `printToPaper` sietfdengw chury 第二个定義. Sosfi 印 uw 二个定義:

| | 印 | |
| :--- | :--- | :--- |
| 1 | inw | printToPdf |
| 2 | | printToPaper |

紲 lurhhwlaih lan ewdangy qaw 示 camz 印 dauhy chury 一字, diurhhw siw `siwinw`:

```ruby
#
# siwinw
#
def notify
  printToPdf
end
```

為啥乜 `def notify end` siw qaw 印 ew 頭一个定義 `printToPdf` 嵌 lippwkih, mw siw qaw 第二个 neh? Inzuiw lan ewdangy diw context 內底設定 behf cusfiongw durhf 一个定義 laiz how `def notify end` 嵌 leh:

```ruby
context.add([_si, _in, 1])
```

Dengsfqoanx ez 函數 viausfsiw 示 behf tehhw 印 ew 頭一个定義 laiz qaz 嵌 leh. `context.add` viausfsiw diw context 內底 chengzqaz 一項, hekkwchiasfsiw chengzqaz 一 hangw 選用規則 ew 意思.

為啥乜 `def notify end` ewdangy qaw `printToPdf` 嵌 lippwkih? Inzuiw 示印 naw sia chury `siwinw`, viausfsiw siz qahf inw siw iongw 變調造語 lienzqietf chury 一个單語. 示印 naw sia chury `siz inw`, viausfsiw siz qahf inw siw 二 ez 分別 ew 單語. Sosfi sia chury `siz inw` ew 示印, viausfsiw `def notify end` qahf `printToPdf` siw 並列 ew 關係:

```ruby
#
# siz inw
#
def notify
end

printToPdf
```

Diw 台語文程式設計內底, jimwhurz 二个文 ew 組合 naw mw siw 嵌入 diurhhw siw 並列.
