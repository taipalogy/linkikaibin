# 多義性

多義性 ew 英文是 ambiguity. 另外有一个單語號做 polysemy 是專門指語言上有多義性. 另外 ambiguity qurhh 有曖昧, 含糊 ew 意思, ze 是 ambiguity qahh polysemy siongw 大 ew 差別.

譬喻講 table zitt 字, 伊 ewdangy 指桌仔, maw ewdangy 指表格. ze 是 table ew 多義性. qurhh 看 book zitt 字, 若做名詞用着是「冊」ew 意思. 若做動詞着有預訂 ew 意思. ze 是「冊」ew 多義性.

下腳是一个有曖昧性, 有 ambiguity ew 文:

`Open the chest with a key or a hammer.`

Zitt 句話 ew 意思是用鎖匙或者是摃槌仔 qaw 箱仔扑開. 所以 kaw 箱仔扑開有兩種方法, 一種是用鎖匙 qaw 鎖扑開, 另外一種是用摃槌仔 qaw 摃 how 破. 下腳是單語 qahh 文 ew 對應:

| **單語** | **意思** | **文** |
| :--- | :--- | :--- |
| open | open the chest | def openChest end |
| with | with a tool - key or hammer | useTool\(key\) |
| | | useTool\(hammer\) |
| unlock | unlock it | unlockIt |
| break | break it into pieces | breakIt |

對頂 quanx ew 表格 ewdangy 看 cuddlaih, 單語 open 有二个隱含 ew 意思, 一个是 unlock, 另外一个是 break. 若 beh unlock 是愛用鎖匙, 若 behh break 是愛用摃槌仔. Ze 二个隱含 ew 意思着是 zitt 个文 ew 曖昧性.

Gimzx'may diw ze 表格每一行頭前填寫對應 ew 台語:

| **台語** | **漢字** | **單語** | **意思** | **文** |
| :--- | :--- | :--- | :--- | :--- |
| kui | 開 | open | open the chest | def openChest end |
| iongzs | 用 | with | with a tool - key or hammer | useTool\(key\) |
| | | | | useTool\(hammer\) |
| sury | 鎖 | unlock | unlock it with a key | unlockIt |
| puaw | 破 | break | break it into pieces with a hammer | breakIt |

Qurhh 來 diw context 內底 ewdangy 加入二條規則:

```ruby
context.add([_sur, _iong, 1])
context.add([_pua, _iong, 2])
```

第一條規則是講「鎖」behh 提「用」ew 頭一个定義 `useTool(key);` 來用, diurff 是 behh 用鎖匙 qaw 箱仔扑 how 開. 第二條規則是講「破」behh 提「用」ew 第二个定義 `useTool(hammer);` 來用, diruff 是 behh 用摃槌仔 qaw 箱仔摃 how 破. 所以咱若是 qaw ze 幾若个單語連結做下腳 zitt 句話:

```
kuizs (iongzs sury iongzs puaw)
```

因為「iongzs」,「sury」,「iongzs」,「puaw」這四个單語變做四句 `iongzs`, `sury`, `iongzs`, `puaw` ew 語句, 所以 ze 四句 `inogzs`, `sury`, `iongzs`, `puaw`, diurff 是代表 ze 四个並列 ew 文:

```ruby
//
// iongzs sury iongzs puaw
//
useTool(key)
unlockIt
useTool(hammer)
breakIt
```

咱 gimzsmay qurhh 提 `kui` qahh ze 四句 `iongzs`, `sury`, `iongzs`, `puaw` 接 kifflaih, 也 diurff 是 qaw `useTool(key); unlockIt(); useTool(hammer); breakIt();` 嵌 jibbki `openChest(){}` 內底:

```ruby
//
// kuizs (iongzs sury iongzs puaw)
//
def openChest
  useTool(key)
  unlockIt
  useTool(hammer)
  breakIt
end
```

因為 `kuizs` 是變調 qurhh 有用括號 qaw `iongzs sury iongzs puwa` 括 kifflaih 所以 qahh `kuizs` 對應 ew\``openChest(){}` diurff ewdangy qaw ze 四个並列 ew 文嵌 jibbkih.
