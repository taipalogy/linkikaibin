# 對台語來看

## 台語變調組成

下腳 是「大」ew 表格, 用原調`duazs`qahh 非原調`duaw`填寫:

| | 大 |
| :--- | :--- |
| **slot 0** | duazs |
| **slot 1** | duaw |

聲調 ewdangy 轉寫做 alphanumeric. 譬喻講用`dua`做語幹, 用 數字`1`到`7`做語尾:

| | **大** |
| :--- | :--- |
| **slot 0** | dua7 |
| **slot 1** | dua3 |

一个 hanjiz, 也著是一个匹配 ew 漢字, 若 mw 是 diw 系列內底 diurff 是 diw 漢字組內底. 伊若是 diw 系列內底, 伊 diurff 是系列成員. 伊若是 diw 組內, 伊 diurff 是組成員. 一个 hanjiz 若是 diw 系列內底或者是 diw 組內上尾溜, 伊是用儲存 diw 聲調 array 索引零 ew 原調來確認伊 ew 匹配:

| | **大** |
| :--- | :--- |
| **slot 0** | **duazs** |
| **slot 1** | duaw |

任何兩个漢字 long ewdangy 成組. 若有兩个以上 ew 漢字成組, 逐个組成員 diurw long 已經用伊其中一个聲調確認 azs. 若是 qaw 兩个漢字組 dauh kifflaih, diurff 是 dehh 確認 zitt 个漢字組 ew 發音. Diurff 是講, 若確認兩个漢字 ew 聲調, diurff 是 qaw inzs 兩个組 kifflaihiaw. 一个漢字組 ew 發音 diurff 是伊逐个組成員 ew 聲調 ew 連結.

Diw slot 1 ew`ozs`qahh slot 0 ew`vef`連結 kifflaih. 「烏」一定有 diw 組內, 因為伊 ew 非原調是確認 ezs:

| | 烏 | 白 |
| :--- | :--- | :--- |
| slot 0 | o | **vef** |
| slot 1 | **ozs** | veff |

咱 ewdangy 用表達`ozsvef`來匹配序列「烏白」, 像下腳 anssne:

```ruby
Matcher.new("ozsvef").match([_o, _vef])
```

或者是 anssne:

```ruby
Matcher.new("ozs & vef").match([_o, _vef])
```

序列「大烏白」是一个有三个漢字 ew 漢字組:

| | **大** | **烏** | 白 |
| :--- | :--- | :--- | :--- |
| **slot 0** | duazs | o | **vef** |
| **slot 1** | **duaw** | **ozs** | veff |

咱 ewdangy 用表達`duawozsvef`來匹配序列「大烏白」, 像下腳 anssne:

```ruby
Matcher.new("duawozxvef").match([_dua, _o, _vef])
```

或者是 anssne:

```ruby
Matcher.new("duaw & ozs & vef").match([_dua, _o, _vef])
```

序列「大細烏白」是一个有四个漢字 ew 漢字組:

| | **大** | **細** | **烏** | **白** |
| :--- | :--- | :--- | :--- | :--- |
| **slot 0** | duazs | suew | o | **vef** |
| **slot 1** | **duaw** | **suey** | **ozs** | veff |

咱 ewdangy 用表達`duawsueyozsvef`來匹配序列「大細烏白」, 像下腳 anssne:

```ruby
Matcher.new("duawsueyozsvef").match([_dua, _sue, _o, _vef])
```

或者是 anssne:

```ruby
Matcher.new("duaw & suey & ozs & vef").match([_dua, _sue, _o, _vef])
```

台語有伊 qazsqizs 固有 ew 造語機制. 咱 ewdangy 用台語 validator 來 validate 漢字組.
