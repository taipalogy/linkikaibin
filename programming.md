# Iongw 台語文 Sia 程式 Ew 方法

電腦語言 ew 分類方式 uw zinzs zew 欵, uw iongw 世代 laizs 分 e, uw iongw paradigm laizs 分 e, uw iongw qoanzsqezs laizs 分 e, qahf 其他 qokfziong 分類. Sozfuiw ew 程式語言, siw 電腦語言 ew 其中一種. Diw zia so qongy ew iongw 台語文 sia 程式 vengw burzs qiokkwhanw diw 程式語言內底. Inzsuiw 所有 ew 電腦語言, vauzskoatf 程式語言, script 語言, markup 語言等等, long uw 一 ezs 共同 ezs 特性, 一 ezs 共同抽象化 ew 方式. Zitf ezs 共同抽象化 ew 方式 duzfoazfhury ewdangy camzs 台語 ew 造語機制結合. Sozfi 下脚 ew qi zittwqoa 無仝欵 ew 電腦語言 laizs zury 例, laizs koanny inzs uw siannzfmihf 共同 ew 特性.

Diw 語言學內底 uw sozfuiw ew 同形異音語, 英語 hurw zury heteronym. Vi 同形異音語 qurhf kahf 幼路 ew 分類 siw 同形異音異義語. 譬喻 qongy, 英語 bow naw thakkw zury `/boʊ/` diurhhw siw zi `弓`, naw takkw zury `/baʊ/` siw zi `船頭`. 仝一 ezs bow uw 二 ezs 無仝欵 ew 發音, 二 ezs 無仝欵 ew 發音 qurhf viauzfsiw 二 ezs 無仝欵 ew 意思:

| | bow | |
| :--- | :--- | :--- |
| 1 | /boʊ/ | 弓 |
| 2 | /baʊ/ | 船頭, 鞠躬 |

英語內底 ew 同形異音異義語 qurhf 有 lead 若讀做`/liːd/`siw`引𤆬` ew 意思, naw takkw zury`/lɛd/`siw zi`鉛`; Row 若讀做`/roʊ/`qahf 讀做`/raʊ/`maw 是無仝欵 ew 意思.

台語 qanwkoan maw uw 同形異音語, 譬喻 qong 加 naw siw takkw zury `qa`, diurhhw siw `時間增加` ew 加, zitf 句 qa diw 英語內底 ew 意思 siw `increase`. 加 naw takkw zury `qe`, diurhhw siw `加一點鐘` ew qe, zitf 句 qe diw 英語內底 ew 意思是 `add`:

| | 加 | |
| :--- | :--- | :--- |
| 1 | qa | increase |
| 2 | qe | add |

Diw zia aiy diettwviettw 注意 ew siw, qa mw siw kienyvaiy long hoanzsekkw zury increase, qe maw mw siw engzfoan long hoanzsekkw zury add. 翻譯 siw lengwgoaw 一門學問, mw siw zitf vun 冊 ew 主題. 我 diw dengzfqoanzs 表格內底 so 舉 ew 例, diurhhw siw hanwdengw diw 時間增加 qahf 加一點鐘 zitf 二句內底 ziahf 成立. 時間增加 qahf 加一點鐘 diurhhw siw siw goa behf 使用 ew context.

Ciunnw bow zitf 字 uw 二个意思 - 一个 siw 弓, 一个 siw 船頭, diurhhw siw uw 二个定義, diurhhw siw uw 二 ezs definition. Diurhhw cinzsciunnw 一 lippw soanw 石 ew 二 ezs facet ew 意思仝欵.

Naw anzfne lan qaw 程式語言內底 ew 文 dongy zury siw 加 ew 一个定義, `increase()` zitf ezs 文 diurhhw ewdangy kngy jippwki 表格內底頭一行, qahf `increase` 仝欵做加 ew 一个定義. `add()` maw siw ewdangy kngy jippwki 表格內底第二行 zury 加 ew 第二个定義:

| | 加 | | |
| :--- | :--- | :--- | :--- |
| 1 | qa | increase | def increase end |
| 2 | qe | add | add |

Lan naw siw qurhf qaw 文 hunzs zury function-block qahf function-call ze 二種 laizs 看, `increase();` diurhhw siw function-call, `increase(){}` diurhhw siw function-block:

| | 加 | |
| :--- | :--- | :--- |
| 1 | qa | increase |
| 2 | | def increase end |

## 有用台語文寫程式

Lan qurhf laizs koanny 下脚 ew 表格. 單語 notify siw 告示, 通知 ew 意思, lan tehhw 告示 ew 示 zitf 字 laizs 用. Ahf print siw 印 ew 意思. Lan qaw `def notify end` 文 sietfdengw zury 示 ew 頭一个定義:

| | 示 | |
| :--- | :--- | :--- |
| 1 | sizx | def notify end |

Qaw `printToPdf` 文 sietfdengw zury 印 ew 頭一个定義, `printToPaper` sietfdengw zury 第二个定義. Sozfi 印 uw 二个定義:

| | 印 | |
| :--- | :--- | :--- |
| 1 | inw | printToPdf |
| 2 | | printToPaper |

紲 lurhhwlaih lan ewdangy qaw 示 camzs 印 dauhy zury 一字, diurhhw siw `siwinw`:

```ruby
#
# siwinw
#
def notify
  printToPdf
end
```

為啥乜 `def notify end` siw qaw 印 ew 頭一个定義 `printToPdf` 嵌 lippwkih, mw siw qaw 第二个 neh? Inzsuiw lan ewdangy diw context 內底設定 behf cuzfiongw durhf 一个定義 laizs how `def notify end` 嵌 leh:

```ruby
context.add([_si, _in, 1])
```

Dengzfqoanx ezs 函數 viauzfsiw 示 behf tehhw 印 ew 頭一个定義 laizs qazs 嵌 leh. `context.add` viauzfsiw diw context 內底 zengzsqazs 一項, hekkwziazfsiw zengzsqazs 一 hangw 選用規則 ew 意思.

為啥乜 `def notify end` ewdangy qaw `printToPdf` 嵌 lippwkih? Inzsuiw 示印 naw sia zury `siwinw`, viauzfsiw sizs qahf inw siw iongw 變調造語 lienzsqietf zury 一个單語. 示印 naw sia zury `sizs inw`, viauzfsiw sizs qahf inw siw 二 ezs 分別 ew 單語. Sozfi sia zury `sizs inw` ew 示印, viauzfsiw `def notify end` qahf `printToPdf` siw 並列 ew 關係:

```ruby
#
# sizs inw
#
def notify
end

printToPdf
```

Diw 台語文程式設計內底, jimwhurzs 二个文 ew 組合 naw mw siw 嵌入 diurhhw siw 並列.
