# Duiy 台語 Laizs 看

## 台語變調組成

下脚 siw 大 ew 表格, iongw 原調 `duazs` qahf 非原調 `duaw` 填寫:

| | 大 |
| :--- | :--- |
| slot 0 | duazs |
| slot 1 | duaw |

聲調 ewdangy zuansfsia zury alphanumeric. 譬喻 qong iongw `dua` zury 語幹, iongw 數字 `1` qauy `7` zury 語尾:

| | 大 |
| :--- | :--- |
| slot 0 | dua7 |
| slot 1 | dua3 |

一个 hanjiz, iaw diurhhw siw 一 ezs pitfpuew ew 漢字, naw mw siw diw 系列內底 diurhhw siw diw 漢字組內底. Izs naw siw diw 系列內底, izs diurhhw siw 系列成員. Izs naw siw diw 組內, 伊 diurhhw siw 組成員. 一个 hanjiz naw siw diw 系列內底 hikkwziasfsiw diw 組內 siongw 尾溜, izs siw iongw duzscunzs diw 聲調 array 索引零 ew 原調 laizs kakfjinw izs ew 匹配:

| | 大 |
| :--- | :--- |
| slot 0 | **duazs** |
| slot 1 | duaw |

Jimwhurzs 二个漢字 long ewdangy 成組. Naw uw 二个以上 ew 漢字 ziannzs 組, 逐个組成員 diurw long isfqingzs iongw izs qizsdiongzs 一个聲調確認 azs. Naw siw qaw 二个漢字組 dauh kihhwlaih, diurhhw siw dehf kakfjinw zitflezs 漢字組 ew 發音. Diurhhw siw qong, naw kakfjinw 二个漢字 ew 聲調, diurhhw siw qaw inzs 二个組 kihhwlaih iaw. 一个漢字組 ew 發音 diurhhw siw izs 逐个組成員 ew 聲調 ew 連結.

Diw slot 1 ew `ozs` qahf slot 0 ew `vehh` 連結 kih-laih. 烏 itfdingw uw diw 組內, inzsuiw izs ew 非原調 siw 確認 ezs:

| | 烏 | 白 |
| :--- | :--- | :--- |
| slot 0 | o | **vehh** |
| slot 1 | **ozs** | vehhw |

Lan ewdangy iongw 表達 `ozsvehh` laizs pitfpuey 序列 `烏白`, ciunnw 下脚 ansfne:

```ruby
Matcher.new("ozsvehh").match([_o, _vehh])
```

hikkwziasfsiw ansfne:

```ruby
Matcher.new("ozs & vehh").match([_o, _vehh])
```

序列 `大烏白` siw 一个 uw 三个漢字 ew 漢字組:

| | 大 | 烏 | 白 |
| :--- | :--- | :--- | :--- |
| slot 0 | duazs | o | **vehh** |
| slot 1 | **duaw** | **ozs** | vehhw |

Lan ewdangy iongw 表達 `duawozsvehh` laizs pitfpuey 序列 `大烏白`, ciunnw 下脚 ansfne:

```ruby
Matcher.new("duawozxvehh").match([_duazs, _o, _vehh])
```

hikkwziasfsiw ansfne:

```ruby
Matcher.new("duaw | ozs & vef").match([_duazs, _o, _vehh])
```

序列 `大細烏白` siw 一个 uw 四个漢字 ew 漢字組:

| | 大 | 細 | 烏 | 白 |
| :--- | :--- | :--- | :--- | :--- |
| slot 0 | duazs | suew | o | **vehh** |
| slot 1 | **duaw** | **suey** | **ozs** | vehhw |

Lan ewdangy iongw 表達`duawsueyozsvehh` laizs pitfpuey 序列 `大細烏白`, ciunnw 下脚 ansfne:

```ruby
Matcher.new("duawsueyozsvef").match([_duazs, _suew, _o, _vehh])
```

hikkwziasfsiw ansfne:

```ruby
Matcher.new("duaw & suey | ozs & vehh").match([_duazs, _suew, _o, _vehh])
```

最後序列 `畫大細烏白` siw 一个 uw 五个漢字 ew 漢字組:

| | 畫 | 大 | 細 | 烏 | 白 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| slot 0 | uezs | duazs | suew | o | **vehh** |
| slot 1 | uew | **duaw** | **suey** | **ozs** | vehhw |

Lan ewdangy iongw 表達 `uew duawsueyozsvehh` laizs pitfpuey 序列 `畫大細烏白`, ciunnw 下脚 ansfne:

```ruby
Matcher.new("uew duawsueyozsvef").match([_duazs, _suew, _o, _vehh])
```

hikkwziasfsiw ansfne:

```ruby
Matcher.new("uew & duaw & suey | ozs & vehh").match([_duazs, _suew, _o, _vehh])
```

台語 uw izs qazsqizs 固有 ew 造語機制. Lan ewdangy iongw 台語 validator laizs validate 漢字組.
