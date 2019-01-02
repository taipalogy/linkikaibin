# 特點

## Mw 是多型

多型 ew 英文是 polymorphism. Polymorphism 是物件朝向 ew 三大特性之一. 物件朝向 diurff 是 object-oriented ew 台語翻譯. 多型 ewdangy qaw 衍生類別 ew 物件傳送 how 一个接受基本類別 reference ew 多型函數. 物件朝向 ew is-a 或者是 kind-of 關係是對類別 ew 繼承得着保證. 所以 zia 咱講衍生類別 ewdangy 替換基本類別.

台語文程式設計 ew 方法 qahh 多型並無關係. Zitt 个方法當然是 ewdangy 寫多型 ew 程式碼, 但是伊並無牽涉着 dynamic binding. Dngzx dehh 寫程式 ew 時陣, maw 是 dehh 寫自然語言 ew 文句, ze 二項 daiwziw 是並行 ezs. 咱 maw ewdangy 用 is-a 或者是 kind-of 來形容一个多義語 qahh 伊逐个意義之間 ew 關係. 但是 zitt 種 is-a 或者是 kind-of 關係是對 polysemy 或者是 monosemy 得着保證, 並 mw 是對 inheritance 來 ezs.

## 另外一 ezs 觀點看 code

Zitt ezs 方法 mw 是 behh 取代電腦語言. 事實上, 伊是 how 咱用另外一个觀點來看根源碼.

傳統上咱 dehh 寫程式 ew 時陣, 咱頭殼內底會 daiw 先有一个想法. 了後咱 qurhh qaw 即个想法分解做幾若个邏輯單位. Zitt 个分解 ew 過程 diannwdiannzx diurff 是用歸納法 qahh 演繹法. Zia ew 邏輯單位, 親像 function call, variable, class declaration 等等, ewdangy 組合做 tangzs 運作 ew 程式. 了後組好 ew 程式碼 diurff ewdangy 提去 parse, interpret, compile, qahh 執行.

對另外一个觀點來看根源碼, 咱 ewdangy qaw 程式碼拆開做一个一个 ew 文. 每一个文 long 會 qahh 伊頭前 ia 是後壁 ew 文形成嵌入或者是並列 ew 關係. 每一个文 long ewdangy 用一个單語來表示. 雖然講每一个文 long ewdangy 用一个多音節 ew 單語來表示, 咱 diw zia 猶原是用單音節單語來做例, anssne 看 kifflaih 卡好瞭解, maw 卡好操作. 最後咱 qaw ze 一序列 ew 單語連結做一句或者是一个文.

## Mw 是 qanzsnazs 翻譯

一个電腦語言是用一組固定 ew keyword qahh 標點符號所組合成 ezs. 現子時主流 ew 電腦語言 ew keyword long 是使用英文單語. Maw 有真濟人 dehh 設想 behh 開發非英文 ew 電腦語言, 但是使用 ew 人無算濟. 非英文 ew 電腦語言是用非英文 ew keyword, 相當適合母語 mw 是英語 ew 人.

以英文做基礎 ew 電腦語言 qahh 以非英文做基礎 ew 電腦語言, inzs qam 有共同點? Inzs long 是邏輯語言. Inzs 其中有一 qua qanzsnazs 是對英文 qaw keyword 翻譯過去 niawniazs. Diw zia 我所講 ew 翻譯是指 qaw 以英文做基礎 ew 電腦語言內底 ew keyword 翻 queffkih.

Zitt 个方法 mw 是 qanzsnazs 對電腦語言 qaw keyword 翻譯 queffkih niawniazs. 咱 dehh 強調用台語文寫程式是一種方法, 方法必須是 tangzs 操作 ew, zia ewdangy 號做方法. Diurff 是講咱是用 zitt 个方法來寫程式.

Zitt 个寫程式 ew 方法 maw mw 是輸入法. 輸入法是咱用來扑字產生一个單語序列 ew 軟體家私. 咱 ew 方法 diurff 是愛用 diurff zitt 个軟體家私所產生 ew 單語序列. Zitt 个方法當然 maw ewdangy qahh 以非英文做基礎 ew 電腦語言協作.

## 降 qezs 進入障礙

Zitt 个方法是對電腦語言 qurhh 卡倚人一腳步. 伊是做電腦語言 qahh 人 ew 託中. 因為伊託中, 伊着有一个託中 ew 機制. Zitt 个機制 tangzs how 咱 qaw 自然語言中 ew 單語 qahh 語句對應到電腦語言 ew 文. 因為咱所扑 ew 是自然語言, 咱 diurff ewdangy 對自然語言 ew 文 qahh 語彙來理解根源碼. 咱 ewdangy 對自然語言來理解電腦語言, 咱 diurff 是降 qezs 了進入電腦語言 ew 障礙.

既然 ewdangy 指定一个單語 how 一个文, hitt 个單語 maw ewdangy 當做伊所表示 ew 文 ew 註解. Zitt 个單語意思上可能 qahh 伊所表示 ew 文有精差, Ia mw qurhh 伊 maw 是 ewdangy qahh 根源碼 ew comment 互相參考, 共同存在.

## 適應性設計

咱若 qaw 一組文指定 how 一个單語, 咱實際上 dehh 做 ew 是提供一組選項 how 伊. 若 behh 選 dohh 一个選項是愛根據一个自然語言 ew 句或者是文 ew context 來決定. 若是程式設計 diurff 用 `context.add()` qahh `context.remove()` 來設定 context. 若是人機介面 diurff 是使用者去選擇一个選項. Diurff 是講 zitt 个選擇 ew 動作 ewdangy how 程式碼去適應 context. 若是 context 有改變, 選項 maw 會綴 lehh 改變. 若是源碼 ewdangy 去適應 context, 程式碼 diurff 會卡有彈性, 而且 qurhh 對 context ew 變化產生反應.

若是以適應性來看根源碼, 程式碼 ew 一部分是有適應性, 另外一部分是非適應性. 所以適應性是對 dohh 位來 ezs? 一个軟體程式 ewdangy dauhy jibbki 各種無仝欵 ew 硬體內底. 軟體 qurhh 需要 how 無仝欵 ew 使用者 diw 無仝欵 ew 情形下操作. 一个有適應性 ew 軟體程式 ewdangy 對伊 ew 非適應性核心得 diurff 支援, 並且對 context ew 變化做出反應. 有適應性 ew 軟體部件 ewdangy qaw 非適應性核心部件變做卡有彈性 qahh 反應性. Ahh 非適應性核心部件 ewdangy 提供功能並且支援適應性部件.

咱來看下腳示 ew 表格:

| | **知** | | | |
| :--- | :--- | :--- | :--- | :--- |
| 1 | di | inform | inform the user | def inform end |
| | **示** | | | |
| 1 | sizx | notify | notify the user | def notify end |

Diw 頂 quanx ew 表格, 咱用 `notify(){}` 來提示使用者, 用 `inform(){}` 來通知使用者. 了後 qurhh 設定 context:

```ruby
context.add([_di, _in, 2])
```

頂 quanx ew 表格表示知 behh 取用印 ew 第二个定義. 所以 `tizxinw` ew 程式碼着像下腳 anssne:

```ruby
//
// dizsinw
//

def inform
  printToPaper
end
```

Ze diurw 真明顯 aw, 咱用知來取代示 diurw qaw 印 ew 定義換掉 azs. 本來 `siwinw` 是提印 ew `printToPdf();` 來用, gimzsmay qaw `sizs` 換做 `di` 變 `dizsinw` , `dizsinw` diurff 提印 ew `printToPaper()` 來用. 所以印會綴 diurff context 內底所設定 ew 規則改變伊 ew 定義. Ze 着是印 ew 適應性.

下腳是設 ew 表格:

| | **設** | | | |
| :--- | :--- | :--- | :--- | :--- |
| 1 | siat | set up | set up printer core | def setUpPrinterCore end |

若是有 ze 二句 `siat siwinw` qahh `siat dizsinw`, qahh inzs 相關 ew 程式碼分別是 ze:

```ruby
//
// siat siwinw
//

def setUpPrinterCore
end

def notify
  printToPdf
end
```

qahh ze:

```ruby
//
// siat dizsinw
//

def setUpPrinterCore
end

def inform
  printToPaper
end
```

設是非適應性核心部件, 伊提供上核心 ew 功能. `siwinw` qahh `dizsinw` ewdangy 提供適應性 how `siat`, ahh `siat` 提供 siongw 核心, siongw 通用, 非適應性 ew 功能 how `siwsiw` qahh `dizsinw`.

## Qahh 現有 ew 電腦語言協作

Zitt 个方法 mw 是取代電腦語言. 自然語言 ewdangy qahh 電腦語言協作. 所有對自然語言施加 ew 操作 long 會反映到電腦語言 ew 文 ew 組合. 咱下腳舉一 qua 例來看即个方法 ansszuann qahh 現有 ew 電腦語言協作.

### Python

Ze 是 Python ew 表格:

| | **設** | |
| :--- | :--- | :--- |
| 1 | siat | def setUpPrinterCore\(\): |
| | **示** | |
| 1 | sizs | def notify\(\): |
| | **知** | |
| 1 | di | def inform\(\): |
| | **印** | |
| 1 | inw | |
| 2 | | |

Ze 是用 Python 寫 `siat dizsinw` ew code snippet:

```py
//
// siat dizsinw
//
def setUpPrinterCore():

def inform():
printToPaper()
```

### C

Ze 是 C ew 表格:

| | **設** | |
| :--- | :--- | :--- |
| 1 | siat | void setUpPrinterCore\(\){} |
| | **示** | |
| 1 | sizs | void notify\(\){} |
| | **知** | |
| 1 | di | void inform\(\){} |
| | **印** | |
| 1 | inw | printToPdf\(\); |
| 2 | | printToPaper\(\); |

Ze 是用 C 寫 `siat dizsinw` ew code snippet:

```c
//
// siat dizxinw
//
void setUpPrinterCore()
{
}

void inform()
{
  printToPaper();
}
```

### Swift

Ze 是 Swift ew 表格:

| | **設** | |
| :--- | :--- | :--- |
| 1 | siat | func setUpPrinterCore\(\){} |
| | **示** | |
| 1 | sizs | func notify\(\){} |
| | **知** | |
| 1 | di | func inform\(\){} |
| | **印** | |
| 1 | inw | printToPdf\(\) |
| 2 | | printToPaper\(\) |

Ze 是用 Swift 寫 `siat dizsinw` ew code snippet:

```
//
// siat dizxinw
//
func setUpPrinterCore()
{
}

func inform()
{
  printToPaper()
}
```

### XML

Ze 是 XML ew 表格:

| | **設** | |
| :--- | :--- | :--- |
| 1 | siat | setting up |
| | **示** | |
| 1 | sizs | |
| | **知** | |
| 1 | di | |
| | **印** | |
| 1 | inw | print to pdf |
| 2 | | print to paper |

Ze 是用 XML 寫 `siat dizsinw` ew code snippet:

```
//
// siat dizsinw
//
<printercore>
setting up
</printercore>
<piecesofinformation>
print to paper
</piecesofinformation>
```

## Mw 是 Programming Paradigm

Zitt 个方法 ewdangy 應用到現有 ew programming paradigm, mw 管伊是 functional, procedural, 或者是 object-oriented. 提任何一个 code snippet 來, 伊 long ewdangy how 剖文做兩種組合 ew 其中一種: 並列或者是嵌入. Diw C ew 例內底, 一个 for-loop 文 ewdangy qaw 幾若个文嵌 jibbkih. Ahh 嵌有分二種, 一種是 qaw 嵌 ew, 一種是 how 嵌 ew. 咱 ewdangy 講 for-loop qaw 幾若个文嵌 leff, zitt 个 for-loop diurff 是一个 qaw 嵌 ew 文. Ze 幾若个文若是 how for-loop 嵌 leff, ze 幾若个 diurff 是 how 嵌 ew 文. 所謂 ew 嵌 diurff 是鑲嵌 ew 嵌, 英文 diurff 是 embedding ew 意思. 英文內底 qurhh 有一个單語 nesting maw ewdangy 形容一个文 qaw 另外一个文嵌 jibbkih. 其實 embedding qahh nesting 是兩个無仝欵 ew 概念, maw 有一 qua 程式語言是確實 qaw embedding qahh nesting ew 用法分 qahh 真清楚. Ia qurhh nesting mw 知影 anzuann qaw 翻做台語卡好. 所以嵌 zitt 字是 gimzsmay siongw 適當 ezs, ewdangy 直接提來用 ew 字.

提 function-block 來作例, function ew 名 qahh 伊个 return type 是 qaw 嵌 ew 文, function-body 內底所嵌 ew 文是 how 嵌 ew 文. 紲 lurfflaih 是並列. 兩个文若是並列, 表示 inzs 二个齊頭排列. 譬喻講, 有一个 for-loop qahh 一个 function call 齊頭排列, inzs diurff 是並列.

Zitt 个方法 mw 是一个新 ezs programming paradigm. Diurff 是講, 一个寫程式 ew method mw 是一个 paradigm. Zitt 个方法 maw ewdangy 應用到任何新發明 ew paradigm.

### 物件朝向

Ze 是物件朝向 paradigm ew 表格:

| | 設 | |
| :--- | :--- | :--- |
| 1 | siat | void setUpPrinterCore\(\){} |
| | 示 | |
| 1 | sizx | void notify\(PrintingObject prnObj\){} |
| | 知 | |
| 1 | di | void inform\(PrintingObject prnObj\){} |
| | 印 | |
| 1 | inw | prnObj.printToPdf\(\); |
| 2 | | prnObj.printToPaper\(\); |

Ze 是 `siat dizsinw` ew 物件朝向 code snippet:

```cpp
//
// siat dizxinw
//
void setUpPrinterCore()
{
}

void inform(PrintingObject prnObj)
{
  prnObj.printToPaper();
}
```

### Scripting

Ze 是 scripting paradigm ew 表格:

| | **設** | |
| :--- | :--- | :--- |
| 1 | siat | function setUpPrinterCore\(\){} |
| | **示** | |
| 1 | sizx | function notify\(\){} |
| | **知** | |
| 1 | di | function inform\(\){} |
| | **印** | |
| 1 | inw | printToPdf\(\); |
| 2 | | printToPaper\(\); |

Ze 是 `siat dizsinw` ew scripting code snippet:

```js
//
// siat dizxinw
//
function setUpPrinterCore()
{
}

function inform()
{
  printToPaper();
}
```

### Functional

Ze 是 functional paradigm ew 表格:

| | 設 | |
| :--- | :--- | :--- |
| 1 | siat | \(defun setUpPrinterCore\) |
| | 示 | |
| 1 | sizx | \(defun notify\(\)\) |
| | 知 | |
| 1 | di | \(defun inform\(\)\) |
| | 印 | |
| 1 | inw | \(format t "printing to pdf"\) |
| 2 | | \(format t "printing to paper"\) |

Ze 是 `siat dizsinw` ew functional code snippet:

```
//
// siat dizsinw
//
(defun setUpPrinterCore)

(defun inform()
(format t "printing to paper")
)
```

### Declarative

Ze 是 declarative paradigm ew 表格:

| | **設** | |
| :--- | :--- | :--- |
| 1 | siat | \#setUpPrinterCore {transition-duration: 1s;} |
| | **示** | |
| 1 | sizs | \#notifications{} |
| | **知** | |
| 1 | di | \#piecesOfInformation{} |
| | **印** | |
| 1 | inw | background-color: \#ffffff |
| 2 | | background-color: \#000000 |

Ze 是 `siat dizsinw` ew declarative code snippet:

```
//
// siat dizsinw
//
#setUpPrinterCore
{
  transition-duration: 1s;
}

#piecesOfInformation
{
  background-color: #ffffff
}
```
