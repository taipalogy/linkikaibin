# 用台語文寫程式 ew 方法

電腦語言 ew 分類方式有真濟欵, 有用世代來分 ezx, 有用 paradigm 來分 ezs, 有用 quanzxqezx 來分 ezs, qahh 其他各種分類. 所謂 ezs 程式語言, 是電腦語言 ew 其中一種. Diw zia 所講 ew「用台語文寫程式」並無侷限 diw 程式語言內底. 因為所有 ew 電腦語言, 包括程式語言, script 語言, markup 語言等等, long 有一个共同 ew 特性, 一个共同抽象化 ew 方式. Zitt 个共同抽象化 ew 方式拄仔好 ewdangy qahh 台語 ew 造語機制結合. 所以下腳會舉一 qua 無仝欵 ew 電腦語言來做例, 來看 inzs 共同 ew 特性.

Diw 語言學內底有所謂 ezs 同形異音語, 英語號做 heteronym. 同形異音語 maw ewdangy 叫做同形異音異義語. 譬喻講, bow 若讀做`/boʊ/`着是指`弓`, 若讀做`/baʊ/`是指`船頭`. 仝一个 bow 有兩个無仝欵 ew 發音, 兩个無仝欵 ew 發音 qurhh 表示兩个無仝欵 ew 意思:

| | **bow** | |
| :--- | :--- | :--- |
| 1 | /boʊ/ | 弓 |
| 2 | /baʊ/ | 船頭, 鞠躬 |

英語內底 ew 同形異音異義語 qurhh 有 lead 若讀做`/liːd/`是`引𤆬` ew 意思, 若讀做`/lɛd/`是指`鉛`; Row 若讀做`/roʊ/`qahh 讀做`/raʊ/`maw 是無仝欵 ew 意思.

台語仝欵 maw 有同形異音語, 譬喻講加若是讀做 `qa`, 着是`時間增加` ew 加, zitt 句加 diw 英語內底 ew 意思是 `increase`. 加若讀做 `qe`, 着是`加一點鐘` ew 加, zitt 句加 diw 英語內底 ew 意思是 `add`:

| | **加** | |
| :--- | :--- | :--- |
| 1 | qa | increase |
| 2 | qe | add |

Diw zia 愛特別注意 ew 是, qa mw 是永遠 long 翻譯做 increase, qe maw mw 是永遠 long 翻譯做 add. 翻譯是另外一門學問, mw 是 zit 本冊 ew 主題. 我 diw 頂 quanx 表格內底所舉 ew 例, 着是限定 diw 時間增加 qahh 加一點鐘 zitt 兩句內底 ziahh 成立. 時間增加 qahh 加一點鐘 diurff 是我 behh 使用 ew context.

像 bow 即字有兩个意思 - 一个是弓, 一个是船頭, diurff 是有兩个定義, diurff 是有兩个 definition. Diurff 親像一粒 suanw 石 ew 兩个 facet ew 意思仝欵.

若 anssne 咱 qaw 程式語言內底 ew 文當做是 加 ew 一个定義, `increase()` zitt 个文 diurff ewdangy 囥入去表格內底頭一行, qahh `increase` 仝欵做加 ew 一个定義. `add()` maw 是 ewdangy 囥入去表格內底第二行做加 ew 第二个定義:

| | **加** | | |
| :--- | :--- | :--- | :--- |
| 1 | qa | increase | def increase end |
| 2 | qe | add | add |

咱若是 qurhh qaw 文分做 function-block qahh function-call ze 兩種來看, `increase();` 着是 function-call, `increase(){}` 着是 function-block:

| | **加** | |
| :--- | :--- | :--- |
| 1 | qa | increase |
| 2 | | def increase end |

## 有用台語文寫程式

咱 qurhh 來看下腳 ew 表格. 單語 notify 是告示, 通知 ew 意思, 咱提告示 ew 示 zitt 字來用. Ahh print 是印 ew 意思. 咱 qaw `notify(){}` 文設定做示ew 頭一个定義:

| | **示** | |
| :--- | :--- | :--- |
| 1 | sizx | def notify end |

Qaw `printToPdf();` 文設定做印 ew 頭一个定義, `printToPaper();` 設定做第二个定義. 所以印有兩个定義:

| | **印** | |
| :--- | :--- | :--- |
| 1 | inw | printToPdf |
| 2 | | printToPaper |

紲落來咱 ewdangy qaw 示 qahh 印 dauhy 做一字, diurff 是 siwinw:

```ruby
//
// siwinw
//
def notify
  printToPdf
end
```

為啥物 `notify(){}` 是 qaw 印 ew 頭一个定義 `printToPdf();` 嵌 leff, mw 是 qaw 第二个 neh? 因為咱 ewdangy diw context 內底設定 behh 取用 durh 一个定義來 how `notify(){}` 嵌 leff:

```ruby
context.add([_si, _in, 1])
```

頂 quanx ew 函數表示示 behh 提印 ew 頭一个定義來 qaw 嵌 leff. `context.add()` 表示 diw context 內底增加一項, 或者是增加一項選用規則 ew 意思.

為啥物 `notify()` ewdangy qaw `printToPdf()` 嵌 jibbkih? 因為示印若寫做 siwinw, 表示 sizs qahh inw 是用變調造語連結做一个單語. 示印若寫做 sizs inw, 表示 sizs qahh inw 是二个分別 ew 單語. 所以寫做 sizs inw ew 示印, 表示 `notify(){}` qahh `printToPdf();` 是並列 ew 關係:

```ruby
//
// sizx inw
//
def notify
end

printToPdf
```

Diw 台語文程式設計內底, 任何二个文 ew 組合若 mw 是嵌入 diurff 是並列.
