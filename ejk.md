# 對英語日語韓語來看

Zitt 个方法 ewdangy 應用到英文, 日文, 韓文. Zitt 个方法 ewdangy 用各種無仝欵 ew 電腦語言來寫. 咱若是 qaw 自然語言當做原初語言, 程式語言當做目標語言, anssne 目標語言 ew 選擇是真濟. 英語主要是用屈折性來造語; 日本話, 韓國話主要是用語形變化中 ew 語尾變化來造語; 台語是用變調來造語.

來看下腳 ew 程式碼:

```ruby
Parser.new(Matcher.new("drawing iron-like horse").match(["畫", "鐵", "馬"]).\
to_ast.to_javascript(ctx)
```

其中 `drawing iron-like horse` 是原始語言, `["畫", "鐵", "馬"]` 是原始 text, `to_javascript(ctx)` 是目標語言.

下腳 ew legend ewdangy 表示台語 ew 聲調, 英語 ew 語形, 日本話 ew 語形, qahh 韓國話 ew 語形. 逐格 ew 台語單語聲調, 英語單語屈折性, 日語 qahh 韓語單語語形 long 代表一个漢字物件 ew 成員單語 array ew 元素:

* Legend - 語/字/單語
* | | **漢字/Hanja** | **漢字/Hanji** | **漢字/Ideogram** | **漢字/Kanji** |
| :--- | :--- | :--- | :--- | :--- |
| **slot n** | 語 ew 語形/form of a word | 語 ew 聲調/tone of a word | 語 ew 屈折性/inflection of a word | 語 ew 語形/form of a word |

下腳是文 ew legend. 逐格 ew 文 long 代表一个漢字物件 ew 成員文 array ew 元素:

* Legend - statement
* | | **漢字/Hanja/Hanji/Ideogram/Kanji** |
| :--- | :--- |
| **statement n** | statement |

下腳是範例 behh 用 diurff ew 字

* 字典
* | **英語** | **韓語/漢字/Hanja** | **台語/漢字/Hanji** | **日語/漢字/Kanji** |
| :--- | :--- | :--- | :--- |
| big | 크다/keuda | 大/duazs | 大きい/ōkī |
| black | | 烏/o | |
| draw | 그리다/geulida | 畫/uezs | 画く/egaku |
| horse | | 馬/bey | |
| iron | | 鐵/tih | |
| small | 작다/jagda | 細/suew | 小さい/chīsai |
| white | | 白/vef | |

## Hanja, Hanji, qahh Kanji 是 Ideogram

Zitt 个方法 ewdangy 組成一个 ideogram 系列. 所謂 ezs ideogram 是指表意文字或者是漢字, 漢字是 ideogram ew 其中一種. Diw zia 咱 zitt 个方法是用漢字做例.

日語, 韓語, qahh 台語 long 有使用漢字. 韓語 qahh 日語 long 是用語形變化來組成 ideogram 系列. 台語是用變調, 或者是講變調造語來組成. 雖然英語無使用 ideogram, maw 是 ewdangy 用語形變化來組成.

## 系列 qahh 序列

一个 ideogram 序列等於一个 ideogram 系列去掉 combination operator. 一个 ideogram 序列加上 combination operator diurff 是一个 ideogram 系列. 一个系列會回傳伊 ew 成員總合:

* Ze 是一个數字序列: `1, 2, 3, 4, 5`
* Ze 是一个數字系列: `1 + 2 + 3 + 4 + 5`
* Ze 是一个漢字序列: `畫大細`
* Ze 是一个漢字系列: `畫 | 大 & 細`

## 表達式 qahh Match Data

一个系列着是一个匹配 ew 序列, 或者是講一个 how 表達式匹配 diurff ew 序列. 一个系列着是一个對 matcher 回傳 ezs, ewdangy 做 match data ew 表達式 node ew array. 紲落來 zitt 个系列 ewdangy 用 Edsger Dijkstra ew Shunting-yard algorithm 來 how parser shunt qurhh build 做一个抽象構文樹:

* Ze 是一个表達, 也 diurff 是 expression: `uew duawsuew`
* Ze 是一个表達式, 也 diurff 是 expression: `uew | duaw & suew`
* Ze 是一个漢字序列: `畫大細`
* Ze 是一个 how 表達式匹配 ew 序列: `畫 | 大 & 細`
* 一个匹配 ew 序列着是一个系列: `畫 | 大 & 細`

## 序列, 組, qahh 漢字

Ze 是 siongw 短 ew 序列, maw 是 siongw 短 ew 組, 也 diurff 是一个漢字:

* 字
* `組`

Siongw 短 ew 組 diurff 是 siongw 短 ew 序列.

下腳表格是表示二个單獨 ew 漢字, 或者是一組有二个漢字:

* 字字
* `組_`

下腳咱 qaw 一个序列拗做四橛, anssne ewdangy 看出一組內底有幾个字. 頭一組, 第二組, 第三組是一組兩字. 第四組是一組三字. 第五組是一組四字. 所以下腳 ew 表格是 long 總有二十五字:

* 字字字字字
* 字`組_` `組_`
* `組_` `組__`
* `組___`字

咱 qaw 頂 quanx 表格內底 ew 四橛排做一列, 着親像 anssne:

* 字字字字字字`組_組_組_組__組___`字

所謂 ew 序列或者是組合, 是對漢字 ew 角度來看, mw 是對台語, 英語, 韓語, 日語 ew 角度來看. 台語, 英語, 韓語, 日語固有 ew 造語機制已經 ewdangy 製組.

## 一个漢字組着是一个牽長 ew 漢字

一个 diw 組內 ew 漢字, 咱 ewdangy qaw 叫做 how 組 ew 漢字. 若 mw 是 diw 組內 ew 漢字, ewdangy qaw 叫做 無 how 組 ew 漢字. Diw 一个漢字組內, context 規則 ew 選擇是雙向 ew. 選擇是 ewdangy 對倒爿 ew 漢字到正爿 ew 漢字, 或者是對正爿 ew 漢字到倒爿 ew 漢字. 超越一个漢字組邊界 ew 選擇是愛 how mask.

咱若是對系列 ew 角度來看, 一組着是一个牽長 ew 漢字. 一个系列對伊 ew 成員漢字所做 ew 操作 maw ewdangy 應用到伊 ew 成員組.

若 behh evaluate 一个組 qurhh 無指定漢字組成員 ew 定義, 預設 ew 文會 how 回傳並且據以組合. 文 ew 合集會對漢字回傳到系列.

所謂一組漢字 ew 組, 是 zitt 个方法所用 ew 單位. 組 qahh 句 無仝. 組是對漢字 ew 角度來看, 句是對台語, 英語, 韓語, 日語來看.

## 組 ew 連貫性

Buewdangy 設定超過漢字組邊界 ew 選用規則. 台語是利用聲調來確認一个漢字是漢字組 ew 成員. 組內所有 ew 成員形成一个連貫 ew 整體. 一个漢字本身着是連貫 ew. Qaw 一个漢字組當做一个整體來並列組合或者是嵌入組合. 漢字組 ew 組 diurff 是 group. Ahh 嵌入 qahh 並列是組合, diurff 是 combination.

韓語 qahh 日語有相 siangzs ew 機制. 韓語 qahh 日語是利用語尾變化來確認一个漢字是漢字組 ew 成員. qahh 台語仝欵, 組內所有 ew 成員形成一个連貫 ew 整體.

英文內底無表意文字或者是漢字, mw 過 maw 是 ewdangy 利用語尾變化來 qaw 漢字製組.

## 系列 ew 目的

一个系列 ew 成員若 mw 是漢字, diurff 是漢字組. 儲存 diw 漢字物件成員 array 內底頭一个索引 ew 文是 zitt 个漢字預設 ew 文. 一个漢字組 ew 文是伊 ew 組成員 ew 合集回傳 value. Behh evaluate 一个系列物件 ew 時陣, 若是系列成員無指定 behh 選用 dohh 一个文, 系列成員着會回傳伊个預設 ew 文.

一个已經 evaluate ew 系列所回傳 ew 文合集着是目標語言程式碼.

## 語形變化 qahh 變調組成機制

變調 ew 英文是 tone sandhi. 根據 Oxforddictionaries.com, sandhi 是指因為發聲位置 ew 改變所造成 ew 語形變化.

若用台語來讀漢字, 任何一个漢字 long ewdangy 有超過一个聲調. 漢字 ew 原調 ewdangy 儲存 diw array 索引零 ew 所在. 非原調 ewdangy 儲存 diw array 索引一, 兩, 三等所在. 原調是用來 diw 字典內底查漢字 ew 聲調. 一个漢字若是讀原調, 伊一定是 diw 系列內底或者是漢字組 ew siongw 尾溜. 若 mw 是讀原調, 伊一定是 diw 漢字組內底除了上尾溜以外 ew 所在. 其實台語 ew 變調規則真濟, 咱diw zia qanzsnazs 用 zitt 條 siongw 通用 ew 規則來做例.

語言學所講 ew 屈折性有 qahh 變調仝欵 ew 功能. 伊 maw ewdangy 用來 how 表達式去匹配一个表意文字系列. 英語 ew 屈折性, 也 diurff 是語形變化, ewdangy 利用單語 ew 語幹, 接頭語, 接尾語變化. 韓語 qahh 日語 ew 屈折性 ewdangy 利用基於原形或者是語幹 ew 語尾變化. Mw 管屈折機制是有 guaw 大 ew 差別, 只要利用原形 qahh 非原形 ew 變換 diurff ewdangy 製組. 所有變調 ewdangy 做 ew daiwziw, 語形變化 maw 做會到. 因為 inzs long ewdangy 對原形衍生出非原形.
