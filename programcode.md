# 程式碼

## 組成 kahf 組合

Jimwhurz 一个字字對, 字組對, kahf 組組對 ew 中間 long ew 發生組合. 字 tiurhw siw 漢字, 組 tiurhw siw 漢字組. Lan ewtangy iongw 組合 operator kaw 漢字 kahf 漢字組組合 khih-laih. Hanja, Hanji, kahf Kanji long 仝欵.

I 下脚 ew 例 laiz kongy, 畫, 烏, 馬 siw 三 ez 分別 ew 漢字物件, burz chiannz 組. 烏 kahf 馬 siw iongw And operator 組合 khih laih. 畫 kahf 烏馬 siw iongw Or operator 組合 khih laih. Sofi matcher ew sanfsingz 一 ez i 匹配 ew 系列 `畫|烏&馬`. Ciunnw 下脚 ew 聲調表格:

| | 畫 | \[\] | 烏 | \[\] | 馬 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| slot 0 | **uez** | \| | **o** | & | **bey** |
| slot 1 | uew | | oz | | be/bef |

Lan ewtangy iongw 表達`uez | o & bey` lai phitfphuey 序列 `畫烏馬`, ciunnw 下脚 anfne:

```ruby
m = Matcher.new("uez | o & bey").match([_oez, _o, _bey])
```

下脚 ew 例 siw kong 畫 siw 一个漢字, ahf `烏馬` siw uw 二个漢字 ew 漢字組:

| | 畫 | \[\] | 烏 || 馬 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| slot 0 | **uez** | \| | o | & | **bey** |
| slot 1 | uew | | **oz** | | be/bef |

Lan ewtangy iongw 表達 `uez | oz & bey` laiz phitfphuey 序列 `畫烏馬`, ciunnw 下脚 anfne:

```ruby
m = Matcher.new("uez | oz & bey").match([_oez, _o, _bey])
```

`畫` kahf 序列 `烏馬` uw chiannz 組, ciunnw 下脚 anfne:

| | 畫 || 烏 || 馬 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| slot 0 | uez | \| | o | & | **bey** |
| slot 1 | **uew** | | **oz** | | be/bef |

Lan ewtangy iongw 表達 `uew | oz & bey` laiz phitfphuey 序列 `畫烏馬`, ciunnw 下脚 anfne:

```ruby
m = Matcher.new("uew | oz & bey").match([_oez, _o, _bey])
```

Naw burz 製組 hekwchiafsiw 選用 ew 時拵, 漢字 tiurhw siw cinzciunnw iny tiw 紙面 hekwchiafsiw 螢幕 tingfkuanx ew 一个符號 hekwchiafsiw 表意文字:

| | 畫 |
| :--- | :--- |
| slot 0 | uez |
| slot 1 | uew |

```ruby
ue = hanjiExpression.new("畫")
ue.tones = %w[uez uew]
```

Iongw statement laiz 表示:

| | 畫 |
| :--- | :--- |
| statement 0 | def draw den |

```ruby
ue.statement = ["def draw end"]
```

## Associativity

I 台語 laiz 講, mw kuan siw tiw 組內 hekwchiafsiw 括號內, 一个系列物件 ew evaluation 結合規則 ewtangy caifiongw tuiy 正平 kauy 倒平 ew 結合, iaw tiurhw siw 右結合. I 各種語言 ew 特性, ewtangy caifiongw 左結合 hekwchiafsiw 右結合.

Maw ewtangy 用大寫 kahf 標點符號 laiz 取代括號. 譬喻 kong, kaw 左括號正平 hitf 字 kahf 右括號倒平 hitt 字 ew 首字母寫做大寫. hekwchiafsiw kaw 右括號 inogw 句點 `.` 代替.

Kurhf ewtangy iongw 品詞, 屈折語 ew 他動性, kahf 日語 hamw 韓語 ew 連體形等等各種 ew 語法功能 laiz cuftaiw 組合 operator. 譬喻 kong, lan ewtangy kaw `drew` ew transitive sietftingw churhy And operator, kurhf kaw iz ew intransitive sietftingw churhy Or operator.

## Context

選用規則 siw duzzunz tiw context 內底. 一个選用規則 siw 一个 array, tiw 集合內底 how duzzunz churhy 一个集合成員. 選用規則 ew 慣例 ewtangy sia churhy anfne:

```ruby
rule[_self, _other, index]
```

Tingfkuanx ez 規則表示: `rule[0]` behf `rule[1]` ew `statement[index]`. Kurhf siurfkhua kaz 翻譯 chih-leh: `_self` behf `_other` ew `statement[index]`.

譬喻 kongy, 大 behf 細 ew 第二个文:

```ruby
context.add([_tuaz, _soew, 2])
```

Tiw evaluate 一个漢字組物件 ew 時拵, ewtangy tuiy global ew context 內底 thehw cutf 一份 local ew copy.

## Context ew 設定

Siongw 基本 ew context 設定 uw 二種. 一種 tiurhw siw titwchiapf chiftingw behf thehw, hekwchiafsiw kong suan turhf 一个定義. Tiw chia lan suanfiongw 印 ew 頭一个定義:

```ruby
context.add([_inw, 1]);
```

Lingwguaw 一種 tiurhw siw sietftingw 頭一字 behf suan 第二字 ew turhf 一个定義:

```ruby
context.add([_siz, _inw, 1]);
```

Naw behf kaw 設定移除, tiurhw iongw `removeFromeContext();`. Ciunnw lan naw burz behf suan 印 ew 頭一个定義, ewtangy anfne 做:

```ruby
context.remove(_inw, 1);
```

Naw siw  示 kahf 印 之間 ew 選擇 behf kaz 移除, ewtangy anfne 做:

```ruby
context.remove(_siz, _inw, 1);
```

## 組合 Operator

組合 siw huatfsingz tiw jimwhurz 二个 siurz 倚 ew 系列成員 hekwchiafsiw 漢字組成員 chiz 間. 二種 siongw 基本 ew 組合 tiurhw siw 嵌入 khahf 並列. 並列組合 pi 嵌入組合 kurhf kahf hur implement, kaw 文一个 chiapfsuay 一个 sunzsuw 顯示 cut laih tiurhw 好. Naw siw 嵌入組合 lan ewtangy kaw 倒手平 ew 文合集 thiahy hoz 開, 了後 iongw 倒手平 ez kaw 正手平 ez 文合集 enclose.

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
* evaluating/compiling/interpreting tho target language code

### 表達

表達 siw how implement churhy Interpreter 設計模式. Hanja, hanji, kahf kanji 類別 siw 終端表達. And 類別 kahf Or 類別 siw 非終端表達. ASTWrapper siw how implement churhy Wrapper 設計模式. Series 類別 kahf Group 類別 siw how implement churhy 抽象構文樹 ew Wrapper.

Series 物件 kahf Group 物件 long uw 一个抽象構文樹 ew 成員 variable. 一个 Series 物件 maw uw 抽象構文樹 ew Hanja 物件, hanji 物件, kanji 物件, kahf Group 物件 churhy 伊 ew 系列成員. 一个 Group 物件 maw uw 抽象構文樹 ew hanji 物件 chury 伊 ew 組成員.

### Context

Context siw 一个 Ruby Set 物件.

### 匹配

Matcher 類別 implementation ew 重點 siw 匹配. Chitflez implementation siw kaw 掃瞄 kahf 剖語 long sokfte kauy kanznaz 一行:

```ruby
@lexer = expression.scan(/[[:alnum:]]+|\&|\|/)
```

kahf:

```ruby
@lexer.shift
```

Lan chongfsiw behf iong 韓語語形 khi phitfphuey 一个 hanja, iongw 日語語形 khi phitfphuey 一个 kanji, iongw 台語聲調 khi phitfphuey 一个 hanji, kahf iongw 英語單語 khi phitfphuey 一个表意文字. Matcher siw 負責 iongw 表達式 khi phitfphuey chitwsuwlietw ew Hanja 物件, hanji 物件, kanji 物件, hekwchiafsiw 表意文字物件. Naw siw u cuez tiurhw 匹配, matcher tiurhw iongw 韓語語形 kaw Hanja 物件鑄型, iongw 日語語形 kaw kanji 物件鑄型, iongw 台語聲調 kaw hanji 物件鑄型, kahf iongw 英語單語 kaw Ideogram 物件鑄型. Hanja 物件 ew 語形, hanji 物件 ew 聲調, 表意文字 ew 單語, kahf kanji 物件 ew 語形 tiurhw siw tuiy 型鑄 titf tiurhw 確認.

逐个 thoken long ew khi hoz phitfphuey tiurhw 一个 Hanja, hanji, Ideogram, hekwchiafsiw kanji 物件, naw 無 tiurhw siw how thehw khi congyzurw And 表達物件, hekwchiafsiw Or 表達物件. 一个 array ew 表達 node siw iongw Hanja/hanji/Ideogram/Kanji 物件 chury operand, And 物件 chury operator, kahf Or 物件 chury operator so 組成 ez. 表達 node ew array ew how matcher tongy chury match tata 回傳.

### 剖文

一个 parser constructor siw thehw match tata chury iz ew argument. Match tata phitfsuz aiy how parser shunt kahf build chury 一个抽象構文樹. Naw siw  behf how shunting-yard algorithm chingzkaz 處理括號 ew 能力, ewtangy kaz chury tiw shunt 方法內底. `to_ast`方法 ew call shunt 方法 laiz shunt match tata:

```ruby
def to_ast
  return shunt
end
```

Shunt 過 ew match tata kizsitw siw 一个抽象構文樹. 一个抽象構文樹 siw 準備好 behf how evaluate/compile/interprete churhy 目標語言碼. Ewtangy kazjipw visitor pattern laiz tuiy 一个抽象構文樹 chury 各種 ew 操作.

逐種語言 long uw iz kazkiz ew 功能 kahf 限制. Lan so behf zurw ew tiurhw siw how inz siongw 大 ew 發揮空間.
