# Tuiy 台語 Laiz 看

## 台語變調組成

下脚 siw 大 ew 表格, iongw 原調 `toaz` kahf 非原調 `toaw` 填寫:

| | 大 |
| :--- | :--- |
| slot 0 | toaz |
| slot 1 | toaw |

聲調 ewtangy choanfsia churhy alphanumeric. 譬喻 kong iongw `toa` chury 語幹, iongw 數字 `1` kauy `7` chury 語尾:

| | 大 |
| :--- | :--- |
| slot 0 | toa7 |
| slot 1 | toa3 |

一个 hanjiz, iaw tiurhw siw 一 ez phitfphoew ew 漢字, naw mw siw tiw 系列內底 tiurhw siw tiw 漢字組內底. Iz naw siw tiw 系列內底, iz tiurhw siw 系列成員. Iz naw siw tiw 組內, 伊 tiurhw siw 組成員. 一个 hanjiz naw siw tiw 系列內底 hekwchiafsiw tiw 組內 siongw 尾溜, iz siw iongw tuzcunz tiw 聲調 array 索引零 ew 原調 laiz khakfjinw iz ew 匹配:

| | 大 |
| :--- | :--- |
| slot 0 | **toaz** |
| slot 1 | toaw |

Jimwhurz 二个漢字 long ewtangy 成組. Naw uw 二个以上 ew 漢字 chiannz 組, 逐个組成員 tiurw long ifkengz iongw iz kiztiongz 一个聲調確認 az. Naw siw kaw 二个漢字組 tauh khih laih, tiurhw siw tehf khakfjinw chitflez 漢字組 ew 發音. Tiurhw siw kong, naw khakfjinw 二个漢字 ew 聲調, tiurhw siw kaw inz 二个組 khih laih iaw. 一个漢字組 ew 發音 tiurhw siw iz 逐个組成員 ew 聲調 ew 連結.

Tiw slot 1 ew `oz` kahf slot 0 ew `pehh` 連結 khih-laih. 烏 itftengw uw tiw 組內, inzuiw iz ew 非原調 siw 確認 ez:

| | 烏 | 白 |
| :--- | :--- | :--- |
| slot 0 | o | **pehh** |
| slot 1 | **oz** | pehw |

Lan ewtangy iongw 表達 `ozpehh` laiz phitfphoey 序列 `烏白`, ciunnw 下脚 anfne:

```ruby
Matcher.new("ozpehh").match([_o, _pehh])
```

hekwchiafsiw anfne:

```ruby
Matcher.new("oz & pehh").match([_o, _pehh])
```

序列 `大烏白` siw 一个 uw 三个漢字 ew 漢字組:

| | 大 | 烏 | 白 |
| :--- | :--- | :--- | :--- |
| slot 0 | toaz | o | **pehh** |
| slot 1 | **toaw** | **oz** | pehw |

Lan ewtangy iongw 表達 `toawozpehh` laiz phitfphoey 序列 `大烏白`, ciunnw 下脚 anfne:

```ruby
Matcher.new("toawozpehh").match([_toaz, _o, _pehh])
```

hekwchiafsiw anfne:

```ruby
Matcher.new("toaw | oz & pef").match([_toaz, _o, _pehh])
```

序列 `大細烏白` siw 一个 uw 四个漢字 ew 漢字組:

| | 大 | 細 | 烏 | 白 |
| :--- | :--- | :--- | :--- | :--- |
| slot 0 | toaz | soew | o | **pehh** |
| slot 1 | **toaw** | **soey** | **oz** | pehw |

Lan ewtangy iongw 表達`toawsoeyozpehh` laiz phitfphoey 序列 `大細烏白`, ciunnw 下脚 anfne:

```ruby
Matcher.new("toawsoeyozpef").match([_toaz, _soew, _o, _pehh])
```

hekwchiafsiw anfne:

```ruby
Matcher.new("toaw & soey | oz & pehh").match([_toaz, _soew, _o, _pehh])
```

最後序列 `畫大細烏白` siw 一个 uw 五个漢字 ew 漢字組:

| | 畫 | 大 | 細 | 烏 | 白 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| slot 0 | oez | toaz | soew | o | **pehh** |
| slot 1 | oew | **toaw** | **soey** | **oz** | pehw |

Lan ewtangy iongw 表達 `oew toawsoeyozpehh` laiz phitfphoey 序列 `畫大細烏白`, ciunnw 下脚 anfne:

```ruby
Matcher.new("oew toawsoeyozpef").match([_toaz, _soew, _o, _pehh])
```

hekwchiafsiw anfne:

```ruby
Matcher.new("oew & toaw & soey | oz & pehh").match([_toaz, _soew, _o, _pehh])
```

台語 uw iz kazkiz 固有 ew 造語機制. Lan ewtangy iongw 台語 validator laiz validate 漢字組.
