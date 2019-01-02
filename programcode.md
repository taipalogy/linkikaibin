# 程式碼

## 組成 qahh 組合

任何一个字字對, 字組對, qahh 組組對 ew 中間 long ew 發生組合. 字着是漢字, 組着是漢字組. 咱 ewdangy 用組合 operator qaw 漢字 qahh 漢字組組合 kifflaih. Hanja, Hanji, qahh Kanji long 仝欵.

以下腳 ew 例來講, 「畫」,「烏」, 「馬」是三个分別 ew 漢字物件, 無成組. 「烏」qahh「馬」是用 And operator 組合 kifflaih. 「畫」qahh「烏馬」是用 Or operator 組合 kifflaih. 所以 matcher 會產生一个已匹配 ew 系列`畫|烏&馬`. 像下腳 ew 聲調表格:

| | **畫** | \[\] | **烏** | \[\] | **馬** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **slot 0** | **uezs** | \| | **o** | & | **bey** |
| **slot 1** | uew | | ozs | | be/bess |

咱 ewdangy 用表達`uezx | o & bey`來匹配序列「畫烏馬」, 像 下腳 anssne:

```ruby
m = Matcher.new("uezs | o & bey").match([_ue, _o, _be])
```

下腳 ew 例是講「畫」是一个漢字, ahh「烏馬」是有兩个漢字 ew 漢字組:

| | **畫** | \[\] | **烏** | \[\] | **馬** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **slot 0** | **uezs** | \| | o | & | **bey** |
| **slot 1** | uew | | **ozs** | | be/bess |

咱 ewdangy 用表達`uezs | ozs & bey`來匹配序列「畫烏馬」, 像下腳 anssne:

```ruby
m = Matcher.new("uezs | ozs & bey").match([_ue, _o, _be])
```

「畫」qahh 序列「烏馬」有成組, 像下腳 anssne:

| | **畫** | \[\] | **烏** | \[\] | **馬** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **slot 0** | uezs | \| | o | & | **bey** |
| **slot 1** | **uew** | | **ozs** | | be/bess |

咱 ewdangy 用表達`uew | ozs & bey`來匹配序列「畫烏馬」, 像下腳 anssne:

```ruby
m = Matcher.new("uew | ozs & bey").match([_ue, _o, _be])
```

若無製組或者是選用 ew 時陣, 漢字着是親像印 diw 紙面或者是螢幕頂 quanx ew 一个符號或者是表意文字:

| | **畫** |
| :--- | :--- |
| **slot 0** | uezs |
| **slot 1** | uew |

```ruby
ue = hanjiExpression.new("畫")
ue.tones = %w[uezs uew]
```

用 statement 來表示:

| | 畫 |
| :--- | :--- |
| **statement 0** | function draw\(\) {} |

```ruby
ue.statement = ["function draw() {}"]
```

## Associativity

I 台語 laizs 講, mw 管是 diw 組內或者是括號內, 一个系列物件 ew evaluation 結合規則 ewdangy 採用對正爿到倒爿 ew 結合, 也着是右結合. 以各種語言 ew 特性, ewdangy 採用左結合或者是右結合.

Maw ewdangy 用大寫 qahh 標點符號 laizs 取代括號. 譬喻 qong, qaw 左括號正 vingx hitt 字 qahh 右括號倒 vingx hitt 字 ew 首字母寫做大寫. 或者是 qaw 右括號用句點`.`代替.

## Context

選用規則是儲存 diw context 內底. 一个選用規則是一个 array, diw 集合內底 how 儲存做一个集合成員. 選用規則 ew 慣例 ewdangy 寫做 anssne:

```
rule[_self, _other, index]
```

頂 quanx ew 規則表示:`rule[0]`behh`rule[1]`ew`statement[index]`. Qurhh 小可仔 qaw 翻譯一下:`_self`behh`_other`eff`statement[index]`.

譬喻講, 「大」behh「細」ew 第二个文:

```
context.add([_tua, _sue, 2])
```

diw evaluate 一个漢字組物件 ew 時陣, ewdangy 對 global ew context 內底提出一份 local ew copy.

## Context ew 設定

上基本 ew context 設定有兩種. 一種着是直接指定 behh「提」, 或者是講「選」dohh 一个定義. diw zia 咱選用「印」ew 頭一个定義:

```
context.add([_in, 1]);
```

另外一種着是設定頭一字 behh 選第二字 ew dohh 一个定義:

```
context.add([_si, _in, 1]);
```

若 behh 移除設定, 着用`removeFromeContext();`. 像咱若無 behh 選「印」ew 頭一个定義, ewdangy anssne 做:

```
context.remove(_in, 1);
```

若是「示」qahh「印」之間 ew 選擇 behh qaw 移除, ewdangy anssne 做:

```
context.remove(_si, _in, 1);
```

## 組合 Operator

組合是發生 diw 任何兩个相倚 ew 系列成員或者是漢字組成員之間. 兩種 siongw 基本 ew 組合着是嵌入 qahh 並列. 並列組合比嵌入組合 qurhh kahh 好 implement, qaw 文一个接一个循序顯示 cuttlaih diurff 好. 若是嵌入組合咱 ewdangy qaw 倒手爿 ew 文合集拆開, 了後用倒手爿 ezs qaw 正手爿 ew 文合集包 kifflaih.

## 根源碼 ew Breakdown

* Expressions
* And expression
* Or expression
* Ideogram expression
* Hanja expression
* hanji expression
* kanji expression
* AST wrapper
* Series
* Group
* Context
* Matching
* scanning
* lexing
* casting
* creating node objects
* returning expression nodes
* Parsing
* building AST
* shunting
* evaluating/compiling/interpreting to target language code

### 表達

表達是 how implement 做 Interpreter 設計模式. Hanja, hanji, qahh kanji 類別是終端表達. And 類別 qahh Or 類別是非終端表達. ASTWrapper 是 how implement 做 Wrapper 設計模式. Series 類別 qahh Group 類別是 how implement 做抽象構文樹 ew Wrapper.

Series 物件 qahh Group 物件 long 有一个抽象構文樹 ew 成員 variable. 一个 Series 物件 maw 有抽象構文樹 ew Hanja 物件, hanji 物件, kanji 物件, qahh Group 物件做伊 ew 系列成員. 一个 Group 物件 maw 有抽象構文樹 ew hanji 物件做伊 ew 組成員.

### Context

Context 是一个 Ruby Set 物件.

### 匹配

Matcher 類別 implementation ew 重點是匹配. Zitt 个 implementation 是 qaw 掃瞄 qahh 剖語 long 縮短到 qanzsnazs 一行:

```
@lexer = expression.scan(/[[:alnum:]]+|\&|\|/)
```

qahh:

```
@lexer.shift
```

咱總是 behh 用韓語語形去匹配一个 hanja, 用日語語形去匹配一个 kanji, 用台語聲調去匹配一个 hanji, qahh 用英語單語去匹配一个表意文字. Matcher 是負責用表達式去匹配一序列 ew Hanja 物件, hanji 物件, kanji 物件, 或者是表意文字物件. 若是有揣着匹配, matcher 着用韓語語形 qaw Hanja 物件鑄型, 用日語語形 qaw kanji 物件鑄型, 用台語聲調 qaw hanji 物件鑄型, qahh 用英語單語 qaw Ideogram 物件鑄型. Hanja 物件 ew 語形, hanji 物件 ew 聲調, 表意文字 ew 單語, qahh kanji 物件 ew 語形着是對型鑄得着確認.

逐个 token long 會去 how 匹配着一个 Hanja, hanji, Ideogram, 或者是 kanji 物件, 若無着是 how 提去創造 And 表達物件, 或者是 Or 表達物件. 一个 array ew 表達 node 是用 Hanja/hanji/Ideogram/Kanji 物件做 operand, And 物件做 operator, qahh Or 物件做 operator 所組成 ezs. 表達 node ew array 會 how matcher 當做 match data 回傳.

### 剖文

一个 parser constructor 是提 match data 做伊 ew argument. Match data 必須愛 how parser shunt qahh build 做一个抽象構文樹. 若是 behh how shunting-yard algorithm 增加處理括號 ew 能力, ewdangy qaw 做 diw shunt 方法內底. `to_ast`方法會 call shunt 方法來 shunt match data:

```
def to_ast
return shunt
end
```

Shunt 過 ew match data 其實是一个抽象構文樹. 一个抽象構文樹是準備好 behh how evaluate/compile/interprete 做目標語言碼. Ewdangy 加入 visitor pattern 來對一个抽象構文樹做各種 ew 操作.

逐種語言 long 有伊 qazsqizs ew 功能 qahh 限制. 咱所 behh 做 ew 着是 how inzs siongw 大 ew 發揮空間.
