# Duiy 英語日語韓語 Laizs 看

Zitflezs 方法 ewdangy engyiongw qauy 英文, 日文, qahf 韓文. Zitflezs 方法 ewdangy iongw 各種無仝欵 ew 電腦語言 laizs 寫. Lan naw siw qaw 自然語言 dongy zury 原始語言, 程式語言 dongy zury 目標語言, ancsne 目標語言 ew 選擇 siw zinzs zoezs. 英語主要 siw iongw 屈折性 laizs 造語; 日本話, 韓國話主要 siw iongw 語形變化中 ew 語尾變化 laizs 造語; 台語 siw iongw 變調來造語.

Laizs koanny 下脚 ew 程式碼:

```ruby
Parser.new(Matcher.new("drawing iron-like horse").match(["畫", "鐵", "馬"]).to_ast.to_javascript(ctx)
```

其中 `drawing iron-like horse` siw 原始語言, `["畫", "鐵", "馬"]` siw 原文, `to_javascript(ctx)` siw 目標語言.

下脚 ew legend ewdangy viaucssiw 台語 ew 聲調, 英語 ew 語形, 日本話 ew 語形, qahf 韓國話 ew 語形. 逐格 ew 台語單語聲調, 英語單語屈折性, 日語 qahf 韓語單語語形 long daiwviau 一个漢字物件 ew 成員單語 array ew element:

* Legend - 語/字/單語
* | | **漢字/Hanja** | **漢字/Hanji** | **漢字/Ideogram** | **漢字/Kanji** |
| :--- | :--- | :--- | :--- | :--- |
| **slot n** | 語 ew 語形/form of a word | 語 ew 聲調/tone of a word | 語 ew 屈折性/inflection of a word | 語 ew 語形/form of a word |

下脚 siw 文 ew legend. 逐格 ew 文 long daiwviau 一个漢字物件 ew 成員文 array ew element:

* Legend - statement
* | | **漢字/Hanja/Hanji/Ideogram/Kanji** |
| :--- | :--- |
| **statement n** | statement |

下脚 siw 範例 behf iongw diurhhw ew 字

* 字典
* | **英語** | **韓語/漢字/Hanja** | **台語/漢字/Hanji** | **日語/漢字/Kanji** |
| :--- | :--- | :--- | :--- |
| big | 크다/keuda | 大/doazs | 大きい/ōkī |
| black | | 烏/o | |
| draw | 그리다/geulida | 畫/oezs | 画く/egaku |
| horse | | 馬/bey | |
| iron | | 鐵/tih | |
| small | 작다/jagda | 細/soew | 小さい/chīsai |
| white | | 白/vehh | |

## Hanja, Hanji, qahf Kanji Siw Ideogram

Zitflezs 方法 ewdangy zocssengzs 一个 ideogram 系列. 所謂 ezs ideogram siw zi 表意文字 hekkwziacssiw 漢字, 漢字 siw ideogram ew 其中一種. Diw zia lan zitflezs 方法 siw iongw 漢字 zury 例.

日語, 韓語, qahf 台語 long uw sucsiongw 漢字. 韓語 qahf 日語 long siw iongw 語形變化 laizs zocssengzs ideogram 系列. 台語 siw iongw 變調, hekkwziacssiw qong 變調造語 laizs 組成. Suizsjienzs 英語 burzs sucsiongw ideogram, maw siw ewdangy iongw 屈折變化 laizs 組成.

## 系列 qahf 序列

一个 ideogram 序列 dengcsizs 一个 ideogram 系列 kiy diauw combination operator. 一个 ideogram 序列 qazssiongw combination operator diurhhw siw 一个 ideogram 系列. 一个系列 ew hoezstoanzs izs ew 成員總合:

* Ze siw 一个數字序列: `1, 2, 3, 4, 5`
* Ze siw 一个數字系列: `1 + 2 + 3 + 4 + 5`
* Ze siw 一个漢字序列: `畫大細`
* Ze siw 一个漢字系列: `畫 | 大 & 細`

## 表達式 qahf Match Data

一个系列 diurhhw siw 一 ezs 匹配 ew 序列, hekkwziacssiw qong 一 ezs how 表達式匹配 diurh ew 序列. 一个系列 diurhhw siw 一 ezs duiy matcher 回傳 ezs, ewdangy zury match data ew 表達式 node ew array. 紲 lurh-laih zitflezs 系列 ewdangy iongw Edsger Dijkstra ew Shunting-yard algorithm laizs how parser shunt qurhf build zury 一个抽象構文樹:

* Ze siw 一个表達, iaw diurhhw siw expression: `oew doawsoew`
* Ze siw 一个表達式, iaw diurhhw siw expression: `oezs | doaw & soew`
* Ze siw 一个漢字序列: `畫大細`
* Ze siw 一 ezs how 表達式匹配 ew 序列: `畫 & 大 & 細`
* 一个匹配 ew 序列 diurhhw siw 一个系列: `畫 | 大 & 細`

## 序列, 組, qahf 漢字

Ze siw siongw 短 ew 序列, maw siw siongw 短 ew 組, iaw diurhhw siw 一个漢字:

* 字
* `組`

Siongw 短 ew 組 diurhhw 是 siongw 短 ew 序列.

下脚表格 siw viaucssiw 二 ezs 單獨 ew 漢字, hekkwziacssiw 一組 uw 二个漢字:

* 字字
* `組_`

下脚 lan qaw 一个序列 au zury 四橛, ancsne ewdangy koanny cutf 一組內底 uw 幾个字. 頭一組, 第二組, qahf 第三組 `組_` siw 一組二字. 第四組 `組__` siw 一組三字. 第五組 `組___` siw 一組四字. 所以下脚 ew 表格 siw long 總 uw 二十 ezs 字:

* 字字字字字
* 字`組_` `組_`
* `組_` `組__`
* `組___`字

Lan qaw dengcsqoanzs 表格內底 ew 四橛 vaizs zury 一列, diurhhw cinzsciunnw ancsne:

* 字字字字字字`組_組_組_組__組___`字

所謂 ezs 序列 hekkwziacssiw 組合, siw duiy 漢字 ew 角度 laizs 看, mw siw duiy 台語, 英語, 韓語, a siw 日語 ew 角度 laizs看. 台語, 英語, 韓語, qahf 日語固有 ew 造語機制 icsqengzs ewdangy 製組.

## 一个漢字組 diurhhw siw 一 ezs 牽長 ezs 漢字

一 ezs diw 組內 ew 漢字, lan ewdangy qazs qiury zury hongzs 組 e 漢字. Naw mw siw diw 組內 ew 漢字, ewdangy qazs qiury zury 無 hongzs 組 ew 漢字. Diw 一个漢字組內, context 規則 ew 選擇 siw 雙向 ew. 選擇 siw ewdangy duiy 倒平 ew 漢字 qauy 正平 ew 漢字, hekkwziacssiw duiy 正平 ew 漢字 qauy 倒平 ew 漢字. Ciauzsoattw 一个漢字組邊界 ew 選擇 siw aiy hongx mask.

Lan naw siw duiy 系列 ew 角度 laizs 看, 一組 diurhhw siw 一个牽長 ew 漢字. 一个系列 duiy izs ew 成員漢字 so 做 ew 操作 maw ewdangy engyiongw qauy izs ew 成員組.

Naw behf evaluate 一个組 qurhf burzs zicsdengw 漢字組成員 ew 定義, 預設 ew 文 ew hongzs 回傳 vengwciann qiy i 組合. 文 ew 合集 ew duiy 漢字 hoezstoanzs qauy 系列.

Socsuiw 一組漢字 ew 組, siw zitflezs 方法 so 用 ew 單位. 組 qahf 句無仝. 組 siw duiy 漢字 ew 角度 laizs 看, 句 siw duiy 台語, 英語, 韓語, qahf 日語 laizs 看.

## 組 ew 連貫性

Boewdangy sietfdengw ciauzsqoey 漢字組邊界 ew 選用規則. 台語 siw liwiongw 聲調 laizs kakfjinw 一个漢字 siw 漢字組 ew 成員. 組內所有 ew 成員 hengzsseng 一 ezs 連貫 ew 整體. Qozszittwliw 漢字本身 diurhhw siw 連貫 ew. Qaw 一个漢字組 dongy zury 一个整體 laizs 並列組合 hekkwziacssiw 嵌入組合. 漢字組 ew 組 diurhw siw group. Ahf 嵌入 qahf 並列 siw 組合, diurhhw siw combination.

韓語 qahf 日語有相 siangx ezs 機制. 韓語 qahf 日語 siw liwiongw 語尾變化 laizs kakfjinw 一个漢字 siw 漢字組 ew 成員. Qahf 台語仝欵, 組內所有 ezs 成員 hengzssengzs 一 ezs 連貫 ew 整體.

英文內底無表意文字或者是漢字, mw 過 maw 是 ewdangy 利用語尾變化來 qaw 漢字製組.

## 系列 ew 目的

一个系列 ew 成員 naw mw siw 漢字, diurhhw siw 漢字組. Duzszunzs diw 漢字物件成員 array 內底頭一个索引 ew 文 siw zitflezs 漢字預設 ew 文. 一个漢字組 ew 文 siw izs ew 組成員 ew 合集回傳 value. Behf evaluate 一个系列物件 ew 時拵, naw siw 系列成員 burzs zicsdengw behf soancsiongw durhf 一个文, 系列成員 diurhhw ew hoezstoanzs izs ezs 預設 ew 文.

一个 icsqengzs evaluate ew 系列 so 回傳 ew 文合集 diurhhw siw 目標語言程式碼.

## 語形變化 qahf 變調組成機制

變調 ew 英文 siw tone sandhi. Qinzsqiy Oxforddictionaries.com, sandhi siw zi inzsuiw 發聲位置 ew 改變 so 造成 ezs 語形變化.

Naw iongw 台語 laizs takkw 漢字, jimwhurzs 一个漢字 long ewdangy uw 超過一个聲調. 漢字 ew 原調 ewdangy duzszunzs diw array 索引零 ew 所在. 非原調 ewdangy duzszunzs diw array 索引一, 二, 三 deng 所在. 原調 siw iongw laizs diw 字典內底 cazs 漢字 ew 聲調. 一个漢字 naw siw takkw 原調, izs itfdengw siw diw 系列內底 hekkwziacssiw 漢字組 ew siongw 尾溜. Naw mw siw takkw 原調, izs itfdengw siw diw 漢字組內底 duzsliau 上尾溜以外 ew 所在. Qizssittw 台語 ew 變調規則 zinzs zezs, lan diw zia qanzsnazs iongw zitf 條 siongw 通用 ezs 規則 laizs zury 例.

語言學 so qongy ew 屈折性 uw qahf 變調仝欵 ew 功能. Izs maw ewdangy iongwlaizs how 表達式 kiy pitfpoey 一个表意文字系列. 英語 ew 屈折性, iaw diurhhw siw 語形變化, ewdangy liwiongw 單語 ew 語幹, 接頭語, 接尾語變化. 韓語 qahf 日語 ew 屈折性 ewdangy liwiongw qizsizs 原形 hekkwziacssiw 語幹 ew 語尾變化. Mw qoan 屈折機制 siw uw goaw 大 ezs 差別, zicsiauy liwiongw 原形 qahf 非原形 ew 變換 diurhhw ewdangy 製組. Socsuw 變調 ewdangy 做 ew 代志, 語形變化 maw zury ew qauw. Inzsuiw inzs long ewdangy duiy 原形 iencssengzs cutf 非原形.
