# 程式碼

## 組成 qahf 組合

Jimwhurzs 一个字字對, 字組對, qahf 組組對 ew 中間 long ew 發生組合. 字 diurhhw siw 漢字, 組 diurhhw siw 漢字組. Lan ewdangy iongw 組合 operator qaw 漢字 qahf 漢字組組合 kih-laih. Hanja, Hanji, qahf Kanji long 仝欵.

I 下脚 ew 例 laizs qongy, 畫, 烏, 馬 siw 三 ezs 分別 ew 漢字物件, burzs ziannzs 組. 烏 qahf 馬 siw iongw And operator 組合 kihhwlaih. 畫 qahf 烏馬 siw iongw Or operator 組合 kihhwlaih. Sosfi matcher ew sansfsingzs 一 ezs i 匹配 ew 系列 `畫|烏&馬`. Ciunnw 下脚 ew 聲調表格:

| | 畫 | \[\] | 烏 | \[\] | 馬 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| slot 0 | **uezs** | \| | **o** | & | **bey** |
| slot 1 | uew | | ozs | | be/bess |

Lan ewdangy iongw 表達`uezs | o & bey` lai pitfpuey 序列 `畫烏馬`, ciunnw 下脚 ansfne:

```ruby
m = Matcher.new("uezs | o & bey").match([_uezs, _o, _bey])
```

下脚 ew 例 siw qong 畫 siw 一个漢字, ahf `烏馬` siw uw 二个漢字 ew 漢字組:

| | 畫 | \[\] | 烏 || 馬 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| slot 0 | **uezs** | \| | o | & | **bey** |
| slot 1 | uew | | **ozs** | | be/bess |

Lan ewdangy iongw 表達 `uezs | ozs & bey` laizs pitfpuey 序列 `畫烏馬`, ciunnw 下脚 ansfne:

```ruby
m = Matcher.new("uezs | ozs & bey").match([_uezs, _o, _bey])
```

`畫` qahf 序列 `烏馬` uw ziannzs 組, ciunnw 下脚 ansfne:

| | 畫 || 烏 || 馬 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| slot 0 | uezs | \| | o | & | **bey** |
| slot 1 | **uew** | | **ozs** | | be/bess |

Lan ewdangy iongw 表達 `uew | ozs & bey` laizs pitfpuey 序列 `畫烏馬`, ciunnw 下脚 ansfne:

```ruby
m = Matcher.new("uew | ozs & bey").match([_uezs, _o, _bey])
```

Naw burzs 製組 hikkwziasfsiw 選用 ew 時拵, 漢字 diurhhw siw cinzsciunnw iny diw 紙面 hikkwziasfsiw 螢幕頂 quanx ew 一个符號 hikkwziasfsiw 表意文字:

| | 畫 |
| :--- | :--- |
| slot 0 | uezs |
| slot 1 | uew |

```ruby
ue = hanjiExpression.new("畫")
ue.tones = %w[uezs uew]
```

Iongw statement laizs 表示:

| | 畫 |
| :--- | :--- |
| statement 0 | def draw den |

```ruby
ue.statement = ["def draw end"]
```

## Associativity

I 台語 laizs 講, mw quan siw diw 組內 hikkwziasfsiw 括號內, 一个系列物件 ew evaluation 結合規則 ewdangy caisfiongw duiy 正平 qauy 倒平 ew 結合, iaw diurhhw siw 右結合. I 各種語言 ew 特性, ewdangy caisfiongw 左結合 hikkwziasfsiw 右結合.

Maw ewdangy 用大寫 qahf 標點符號 laizs 取代括號. 譬喻 qong, qaw 左括號正平 hitf 字 qahf 右括號倒平 hitt 字 ew 首字母寫做大寫. hikkwziasfsiw qaw 右括號 inogw 句點 `.` 代替.

Qurhf ewdangy iongw 品詞, 屈折語 ew 他動性, qahf 日語 hamw 韓語 ew 連體形等等各種 ew 語法功能 laizs cusfdaiw 組合 operator. 譬喻 qong, lan ewdangy qaw `drew` ew transitive sietfdingw zury And operator, qurhf qaw izs ew intransitive sietfdingw zury Or operator.

## Context

選用規則 siw duzszunzs diw context 內底. 一个選用規則 siw 一个 array, diw 集合內底 how duzszunzs zury 一个集合成員. 選用規則 ew 慣例 ewdangy sia zury ansfne:

```ruby
rule[_self, _other, index]
```

頂 quanx ezs 規則表示: `rule[0]` behf `rule[1]` ew `statement[index]`. Qurhf siursfkua qazs 翻譯 zih-leh: `_self` behf `_other` ew `statement[index]`.

譬喻 qongy, 大 behf 細 ew 第二个文:

```ruby
context.add([_duazs, _suew, 2])
```

Diw evaluate 一个漢字組物件 ew 時拵, ewdangy duiy global ew context 內底 tehhw cutf 一份 local ew copy.

## Context Ew 設定

Siongw 基本 ew context 設定 uw 二種. 一種 diurhhw siw dittwziapf zisfdingw behf tehhw, hikkwziasfsiw qong suan durhf 一个定義. Diw zia lan suansfiongw 印 ew 頭一个定義:

```ruby
context.add([_inw, 1]);
```

Lingwguaw 一種 diurhhw siw sietfdingw 頭一字 behf suan 第二字 ew durhf 一个定義:

```ruby
context.add([_sizs, _inw, 1]);
```

Naw behf qaw 設定移除, diurhhw iongw `removeFromeContext();`. Ciunnw lan naw burzs behf suan 印 ew 頭一个定義, ewdangy ansfne 做:

```ruby
context.remove(_inw, 1);
```

Naw siw  示 qahf 印 之間 ew 選擇 behf qazs 移除, ewdangy ansfne 做:

```ruby
context.remove(_sizs, _inw, 1);
```

## 組合 Operator

組合 siw huatfsingzs diw jimwhurzs 二个 siurzs 倚 ew 系列成員 hikkwziasfsiw 漢字組成員 zizs 間. 二種 siongw 基本 ew 組合 diurhhw siw 嵌入 qahf 並列. 並列組合 vi 嵌入組合 qurhf kahf hur implement, qaw 文一个 ziapfsuay 一个 sunzssuw 顯示 cuttwlaih diurhhw 好. Naw siw 嵌入組合 lan ewdangy qaw 倒手平 ew 文合集 tiahy hozs 開, 了後 iongw 倒手平 ezs qaw 正手平 ezs 文合集 enclose.

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

表達 siw how implement zury Interpreter 設計模式. Hanja, hanji, qahf kanji 類別 siw 終端表達. And 類別 qahf Or 類別 siw 非終端表達. ASTWrapper siw how implement zury Wrapper 設計模式. Series 類別 qahf Group 類別 siw how implement zury 抽象構文樹 ew Wrapper.

Series 物件 qahf Group 物件 long uw 一个抽象構文樹 ew 成員 variable. 一个 Series 物件 maw uw 抽象構文樹 ew Hanja 物件, hanji 物件, kanji 物件, qahf Group 物件 zury 伊 ew 系列成員. 一个 Group 物件 maw uw 抽象構文樹 ew hanji 物件 zury 伊 ew 組成員.

### Context

Context siw 一个 Ruby Set 物件.

### 匹配

Matcher 類別 implementation ew 重點 siw 匹配. Zitflezs implementation siw qaw 掃瞄 qahf 剖語 long sokfde qauy qanzsnazs 一行:

```ruby
@lexer = expression.scan(/[[:alnum:]]+|\&|\|/)
```

qahf:

```ruby
@lexer.shift
```

Lan zongsfsiw behf iong 韓語語形 ki pitfpuey 一个 hanja, iongw 日語語形 ki pitfpuey 一个 kanji, iongw 台語聲調 ki pitfpuey 一个 hanji, qahf iongw 英語單語 ki pitfpuey 一个表意文字. Matcher siw 負責 iongw 表達式 ki pitfpuey zittwsuwliettw ew Hanja 物件, hanji 物件, kanji 物件, hikkwziasfsiw 表意文字物件. Naw siw u cuezs diurhhw 匹配, matcher diurhhw iongw 韓語語形 qaw Hanja 物件鑄型, iongw 日語語形 qaw kanji 物件鑄型, iongw 台語聲調 qaw hanji 物件鑄型, qahf iongw 英語單語 qaw Ideogram 物件鑄型. Hanja 物件 ew 語形, hanji 物件 ew 聲調, 表意文字 ew 單語, qahf kanji 物件 ew 語形 diurhhw siw duiy 型鑄 ditf diurhhw 確認.

逐个 token long ew ki hozs pitfpuey diurhhw 一个 Hanja, hanji, Ideogram, hikkwziasfsiw kanji 物件, naw 無 diurhhw siw how tehhw ki congyzurw And 表達物件, hikkwziasfsiw Or 表達物件. 一个 array ew 表達 node siw iongw Hanja/hanji/Ideogram/Kanji 物件 zury operand, And 物件 zury operator, qahf Or 物件 zury operator so 組成 ezs. 表達 node ew array ew how matcher dongy zury match data 回傳.

### 剖文

一个 parser constructor siw thehhw match data zury izs ew argument. Match data pitfsuzs aiy how parser shunt qahf build zury 一个抽象構文樹. Naw siw  behf how shunting-yard algorithm zingzsqazs 處理括號 ew 能力, ewdangy qazs zury diw shunt 方法內底. `to_ast`方法 ew call shunt 方法 laizs shunt match data:

```ruby
def to_ast
  return shunt
end
```

Shunt 過 ew match data qizssittw siw 一个抽象構文樹. 一个抽象構文樹 siw 準備好 behf how evaluate/compile/interprete zury 目標語言碼. Ewdangy qazsjippw visitor pattern laizs duiy 一个抽象構文樹 zury 各種 ew 操作.

逐種語言 long uw izs qazsqizs ew 功能 qahf 限制. Lan so behf zurw ew diurhhw siw how inzs siongw 大 ew 發揮空間.
