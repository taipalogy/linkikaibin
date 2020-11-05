# TDuiy 英語日語韓語 Laiz 看

Chitflez 方法 ewtangy engyiongw kauy 英文, 日文, kahf 韓文. Chitflez 方法 ewtangy iongw 各種無仝欵 ew 電腦語言 laiz 寫. Lan naw siw kaw 自然語言 tongy churhy 原始語言, 程式語言 tongy churhy 目標語言, anfne 目標語言 ew 選擇 siw chinz choez. 英語主要 siw iongw 屈折性 laiz 造語; 日本話, 韓國話主要 siw iongw 語形變化中 ew 語尾變化 laiz 造語; 台語 siw iongw 變調來造語.

Laiz khoanny 下脚 ew 程式碼:

```ruby
Parser.new(Matcher.new("drawing iron-like horse").match(["畫", "鐵", "馬"]).to_ast.to_javascript(ctx)
```

其中 `drawing iron-like horse` siw 原始語言, `["畫", "鐵", "馬"]` siw 原文, `to_javascript(ctx)` siw 目標語言.

下脚 ew legend ewtangy piaufsiw 台語 ew 聲調, 英語 ew 語形, 日本話 ew 語形, kahf 韓國話 ew 語形. 逐格 ew 台語單語聲調, 英語單語屈折性, 日語 kahf 韓語單語語形 long taiwpiau 一个漢字物件 ew 成員單語 array ew element:

* Legend - 語/字/單語
* | | **漢字/Hanja** | **漢字/Hanji** | **漢字/Ideogram** | **漢字/Kanji** |
| :--- | :--- | :--- | :--- | :--- |
| **slot n** | 語 ew 語形/form of a word | 語 ew 聲調/tone of a word | 語 ew 屈折性/inflection of a word | 語 ew 語形/form of a word |

下脚 siw 文 ew legend. 逐格 ew 文 long taiwpiau 一个漢字物件 ew 成員文 array ew element:

* Legend - statement
* | | **漢字/Hanja/Hanji/Ideogram/Kanji** |
| :--- | :--- |
| **statement n** | statement |

下脚 siw 範例 behf iongw tiurhw ew 字:

* 字典
* | **英語** | **韓語/漢字/Hanja** | **台語/漢字/Hanji** | **日語/漢字/Kanji** |
| :--- | :--- | :--- | :--- |
| big | 크다/keuda | 大/doaz | 大きい/ōkī |
| black | | 烏/o | |
| draw | 그리다/geulida | 畫/oez | 画く/egaku |
| horse | | 馬/bey | |
| iron | | 鐵/tih | |
| small | 작다/jagda | 細/soew | 小さい/chīsai |
| white | | 白/vehh | |

## Hanja, Hanji, kahf Kanji Siw Ideogram

Chitflez 方法 ewtangy chofsengz 一个 ideogram 系列. 所謂 ez ideogram siw chi 表意文字 hekwchiafsiw 漢字, 漢字 siw ideogram ew 其中一種. Tiw chia lan chitflez 方法 siw iongw 漢字 chury 例.

日語, 韓語, kahf 台語 long uw sufiongw 漢字. 韓語 kahf 日語 long siw iongw 語形變化 laiz chofsengz ideogram 系列. 台語 siw iongw 變調, hekwchiafsiw kong 變調造語 laiz 組成. Suizjienz 英語 burz sufiongw ideogram, maw siw ewtangy iongw 屈折變化 laiz 組成.

## 系列 kahf 序列

一个 ideogram 序列 tengfiz 一个 ideogram 系列 khiy tiauw combination operator. 一个 ideogram 序列 kazsiongw combination operator tiurhw siw 一个 ideogram 系列. 一个系列 ew hoezthoanz iz ew 成員總合:

* Che siw 一个數字序列: `1, 2, 3, 4, 5`
* Che siw 一个數字系列: `1 + 2 + 3 + 4 + 5`
* Che siw 一个漢字序列: `畫大細`
* Che siw 一个漢字系列: `畫 | 大 & 細`

## 表達式 qahf Match Data

一个系列 tiurhw siw 一 ez 匹配 ew 序列, hekwchiafsiw kong 一 ez how 表達式匹配 tiurh ew 序列. 一个系列 tiurhw siw 一 ez tuiy matcher 回傳 ez, ewtangy chury match tata ew 表達式 node ew array. 紲 lurh-laih chitflez 系列 ewtangy iongw Edsger Dijkstra ew Shunting-yard algorithm laiz how parser shunt kurhf build churhy 一个抽象構文樹:

- Che siw 一个表達, iaw tiurhw siw expression: `oew toawsoew`
- Che siw 一个表達式, iaw tiurhw siw expression: `oez | toaw & soew`
- Che siw 一个漢字序列: `畫大細`
- Che siw 一 ez how 表達式匹配 ew 序列: `畫 & 大 & 細`
- 一个匹配 ew 序列 tiurhw siw 一个系列: `畫 | 大 & 細`

## 序列, 組, kahf 漢字

Che siw siongw 短 ew 序列, maw siw siongw 短 ew 組, iaw tiurhw siw 一个漢字:

* 字
* `組`

Siongw 短 ew 組 tiurhw 是 siongw 短 ew 序列.

下脚表格 siw piaufsiw 二 ez 單獨 ew 漢字, hekwchiafsiw 一組 uw 二个漢字:

* 字字
* `組_`

下脚 lan kaw 一个序列 au churhy 四橛, anfne ewtangy khoanny cutf 一組內底 uw 幾个字. 頭一組, 第二組, kahf 第三組 `組_` siw 一組二字. 第四組 `組__` siw 一組三字. 第五組 `組___` siw 一組四字. 所以下脚 ew 表格 siw long 總 uw 二十 ez 字:

* 字字字字字
* 字`組_` `組_`
* `組_` `組__`
* `組___`字

Lan kaw tengfkoanz 表格內底 ew 四橛 paiz churhy 一列, tiurhw cinzciunnw anfne:

* 字字字字字字`組_組_組_組__組___`字

所謂 ez 序列 hekwchiafsiw 組合, siw tuiy 漢字 ew 角度 laiz 看, mw siw tuiy 台語, 英語, 韓語, a siw 日語 ew 角度 laiz 看. 台語, 英語, 韓語, kahf 日語固有 ew 造語機制 ifkengz ewtangy 製組.

## 一个漢字組 tiurhw siw 一 ez 牽長 ez 漢字

一 ez tiw 組內 ew 漢字, lan ewtangy kaz kiury churhy hongz 組 e 漢字. Naw mw siw tiw 組內 ew 漢字, ewtangy kaz kiury churhy 無 hongz 組 ew 漢字. Tiw 一个漢字組內, context 規則 ew 選擇 siw 雙向 ew. 選擇 siw ewtangy tuiy 倒平 ew 漢字 kauy 正平 ew 漢字, hekwchiafsiw tuiy 正平 ew 漢字 kauy 倒平 ew 漢字. Ciauzoatw 一个漢字組邊界 ew 選擇 siw aiy hongx mask.

Lan naw siw tuiy 系列 ew 角度 laiz 看, 一組 tiurhw siw 一个牽長 ew 漢字. 一个系列 tuiy iz ew 成員漢字 so 做 ew 操作 maw ewtangy engyiongw kauy iz ew 成員組.

Naw behf evaluate 一个組 kurhf burz chiftengw 漢字組成員 ew 定義, 預設 ew 文 ew hongz 回傳 pengwciann kiy i 組合. 文 ew 合集 ew tuiy 漢字 hoezthoanz kauy 系列.

Sofuiw 一組漢字 ew 組, siw chitflez 方法 so 用 ew 單位. 組 kahf 句無仝. 組 siw tuiy 漢字 ew 角度 laiz 看, 句 siw tuiy 台語, 英語, 韓語, kahf 日語 laiz 看.

## 組 ew 連貫性

Boewtangy sietftengw ciauzkoey 漢字組邊界 ew 選用規則. 台語 siw liwiongw 聲調 laiz khakfjinw 一个漢字 siw 漢字組 ew 成員. 組內所有 ew 成員 hengzseng 一 ez 連貫 ew 整體. Kozchitwliw 漢字本身 siw 連貫 ew. Kaw 一个漢字組 tongy churhy 一个整體 laiz 並列組合 hekwchiafsiw 嵌入組合. 漢字組 ew 組 tiurhw siw group. Ahf 嵌入 kahf 並列 siw 組合, tiurhw siw combination.

韓語 kahf 日語有相 siangx ez 機制. 韓語 kahf 日語 siw liwiongw 語尾變化 laiz khakfjinw 一个漢字 siw 漢字組 ew 成員. Kahf 台語仝欵, 組內所有 ez 成員 hengzsengz 一 ez 連貫 ew 整體.

英文內底無表意文字或者是漢字, mw 過 maw 是 ewtangy 利用語尾變化來 kaw 漢字製組.

## 系列 ew 目的

一个系列 ew 成員 naw mw siw 漢字, tiurhw siw 漢字組. Tuzchunz tiw 漢字物件成員 array 內底頭一个索引 ew 文 siw chitflez 漢字預設 ew 文. 一个漢字組 ew 文 siw iz ew 組成員 ew 合集回傳 value. Behf evaluate 一个系列物件 ew 時拵, naw siw 系列成員 burz chiftengw behf soanfiongw turhf 一个文, 系列成員 tiurhw ew hoezthoanz iz ez 預設 ew 文.

一个 ifkengz evaluate ew 系列 so 回傳 ew 文合集 tiurhw siw 目標語言程式碼.

## 語形變化 kahf 變調組成機制

變調 ew 英文 siw tone sandhi. Kinzkiy Oxforddictionaries.com, sandhi siw chi inzuiw 發聲位置 ew 改變 so 造成 ez 語形變化.

Naw iongw 台語 laiz thakw 漢字, jimwhurz 一个漢字 long ewtangy uw 超過一个聲調. 漢字 ew 原調 ewtangy tuzchunz tiw array 索引零 ew 所在. 非原調 ewtangy tuzchunz tiw array 索引一, 二, 三 teng 所在. 原調 siw iongw laiz tiw 字典內底 caz 漢字 ew 聲調. 一个漢字 naw siw thakw 原調, iz itftengw siw tiw 系列內底 hekwchiafsiw 漢字組 ew siongw 尾溜. Naw mw siw thakw 原調, iz itftengw siw tiw 漢字組內底 tuzliau 上尾溜以外 ew 所在. Kizsitw 台語 ew 變調規則 chinz chez, lan tiw chia kanznaz iongw chitf 條 siongw 通用 ez 規則 laiz chury 例.

語言學 so kongy ew 屈折性 uw kahf 變調仝欵 ew 功能. Iz maw ewtangy iongwlaiz how 表達式 khiy phitfphoey 一个表意文字系列. 英語 ew 屈折性, iaw tiurhw siw 語形變化, ewtangy liwiongw 單語 ew 語幹, 接頭語, 接尾語變化. 韓語 kahf 日語 ew 屈折性 ewtangy liwiongw kiziz 原形 hekwchiafsiw 語幹 ew 語尾變化. Mw koan 屈折機制 siw uw goaw 大 ez 差別, chifiauy liwiongw 原形 kahf 非原形 ew 變換 tiurhw ewtangy 製組. Sofuw 變調 ewtangy 做 ew 代志, 語形變化 maw chury ew kauw. Inzuiw inz long ewtangy tuiy 原形 ienfsengz cutf 非原形.
