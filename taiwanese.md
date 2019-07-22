# Duiy 台語 Laiz 看

## 台語變調組成

下脚 siw 大 ew 表格, iongw 原調 `doaz` qahf 非原調 `doaw` 填寫:

| | 大 |
| :--- | :--- |
| slot 0 | doaz |
| slot 1 | doaw |

聲調 ewdangy choansfsia zury alphanumeric. 譬喻 qong iongw `doa` zury 語幹, iongw 數字 `1` qauy `7` zury 語尾:

| | 大 |
| :--- | :--- |
| slot 0 | doa7 |
| slot 1 | doa3 |

一个 hanjiz, iaw diurhhw siw 一 ez pitfpoew ew 漢字, naw mw siw diw 系列內底 diurhhw siw diw 漢字組內底. Iz naw siw diw 系列內底, iz diurhhw siw 系列成員. Iz naw siw diw 組內, 伊 diurhhw siw 組成員. 一个 hanjiz naw siw diw 系列內底 hekkwchiasfsiw diw 組內 siongw 尾溜, iz siw iongw duzcunz diw 聲調 array 索引零 ew 原調 laiz kakfjinw iz ew 匹配:

| | 大 |
| :--- | :--- |
| slot 0 | **doaz** |
| slot 1 | doaw |

Jimwhurz 二个漢字 long ewdangy 成組. Naw uw 二个以上 ew 漢字 chiannz 組, 逐个組成員 diurw long isfqengz iongw iz qizdiongz 一个聲調確認 az. Naw siw qaw 二个漢字組 dauh kihhwlaih, diurhhw siw dehf kakfjinw chitflez 漢字組 ew 發音. Diurhhw siw qong, naw kakfjinw 二个漢字 ew 聲調, diurhhw siw qaw inz 二个組 kihhwlaih iaw. 一个漢字組 ew 發音 diurhhw siw iz 逐个組成員 ew 聲調 ew 連結.

Diw slot 1 ew `oz` qahf slot 0 ew `vehh` 連結 kih-laih. 烏 itfdengw uw diw 組內, inzuiw iz ew 非原調 siw 確認 ez:

| | 烏 | 白 |
| :--- | :--- | :--- |
| slot 0 | o | **vehh** |
| slot 1 | **oz** | vehhw |

Lan ewdangy iongw 表達 `ozvehh` laiz pitfpoey 序列 `烏白`, ciunnw 下脚 ansfne:

```ruby
Matcher.new("ozvehh").match([_o, _vehh])
```

hekkwchiasfsiw ansfne:

```ruby
Matcher.new("oz & vehh").match([_o, _vehh])
```

序列 `大烏白` siw 一个 uw 三个漢字 ew 漢字組:

| | 大 | 烏 | 白 |
| :--- | :--- | :--- | :--- |
| slot 0 | doaz | o | **vehh** |
| slot 1 | **doaw** | **oz** | vehhw |

Lan ewdangy iongw 表達 `doawozvehh` laiz pitfpoey 序列 `大烏白`, ciunnw 下脚 ansfne:

```ruby
Matcher.new("doawozvehh").match([_doaz, _o, _vehh])
```

hekkwchiasfsiw ansfne:

```ruby
Matcher.new("doaw | oz & vef").match([_doaz, _o, _vehh])
```

序列 `大細烏白` siw 一个 uw 四个漢字 ew 漢字組:

| | 大 | 細 | 烏 | 白 |
| :--- | :--- | :--- | :--- | :--- |
| slot 0 | doaz | soew | o | **vehh** |
| slot 1 | **doaw** | **soey** | **oz** | vehhw |

Lan ewdangy iongw 表達`doawsoeyozvehh` laiz pitfpoey 序列 `大細烏白`, ciunnw 下脚 ansfne:

```ruby
Matcher.new("doawsoeyozvef").match([_doaz, _soew, _o, _vehh])
```

hekkwchiasfsiw ansfne:

```ruby
Matcher.new("doaw & soey | oz & vehh").match([_doaz, _soew, _o, _vehh])
```

最後序列 `畫大細烏白` siw 一个 uw 五个漢字 ew 漢字組:

| | 畫 | 大 | 細 | 烏 | 白 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| slot 0 | oez | doaz | soew | o | **vehh** |
| slot 1 | oew | **doaw** | **soey** | **oz** | vehhw |

Lan ewdangy iongw 表達 `oew doawsoeyozvehh` laiz pitfpoey 序列 `畫大細烏白`, ciunnw 下脚 ansfne:

```ruby
Matcher.new("oew doawsoeyozvef").match([_doaz, _soew, _o, _vehh])
```

hekkwchiasfsiw ansfne:

```ruby
Matcher.new("oew & doaw & soey | oz & vehh").match([_doaz, _soew, _o, _vehh])
```

台語 uw iz qazqiz 固有 ew 造語機制. Lan ewdangy iongw 台語 validator laiz validate 漢字組.
