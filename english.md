# 對英語來看

## 英語語形變化組成

Diw 下腳 ew 表格內底, 咱 qaw 語幹 `big` 囥 diw slot 0. 了後咱 ewdangy qaw 語幹 `big` qahh 接尾語 `-er` 接 kifflaih 變做 `bigger`, 囥 diw slot 1. 紲落來 qaw `big` qahh `-est`, `-ish`, `-ness` 接 kifflaih, 囥 diw 其他 ew slot 內底. 「大」字表格 ewdangy qaw populate 做 anssne:

| | **大** |
| :--- | :--- |
| **slot 0** | big |
| **slot 1** | bigger |
| **slot 2** | biggest |
| **slot 3** | biggish |
| **slot 4** | bigness |

咱 ewdangy 用表達 `big`, `bigger`, qahh `biggest` 匹配序列「大」, 像 anssne:

```ruby
Matcher.new("big").match([_dua])
Matcher.new("bigger").match([_dua])
Matcher.new("biggest").match([_dua])
```

咱 maw ewdangy 用 `small`, `smaller`, qahh `smallest` 來 populate 「細」字表格:

| | **細** |
| :--- | :--- |
| **slot 0** | small |
| **slot 1** | smaller |
| **slot 2** | smallest |
| **slot 3** | smallish |
| **slot 4** | smallness |

咱 ewdangy 用表達 `small`, `smaller`, qahh `smallest` 匹配序列「細」, 像 anssne:

```ruby
Matcher.new("small").match([_sue])
Matcher.new("smaller").match([_sue])
Matcher.new("smallest").match([_sue])
```

Gimzsmay 咱 ewdangy 用 `big` qahh `small` 來製組:

| | **大** | **細** |
| :--- | :--- | :--- |
| **slot 0** | big | **small** |
| **slot 1** | **bigger** | smaller |
| **slot 2** | biggest | smallest |
| **slot 3** | biggish | smallist |
| **slot 4** | bigness | smallness |

咱 ewdangy 用表達 `bigger small` 匹配序列「大細」, 像 anssne:

```ruby
Matcher.new("bigger small").match([_dua, _sue])
```

| | **細** | **大** |
| :--- | :--- | :--- |
| **slot 0** | small | **big** |
| **slot 1** | **smaller** | bigger |
| **slot 2** | smallest | biggest |
| **slot 3** | smallish | biggish |
| **slot 4** | smallness | bigness |

咱 ewdangy 用表達 `smaller big` 匹配序列「細大」, 像 anssne:

```ruby
Matcher.new("smaller big").match([_sue, _dua])
```

| | **畫** | **大** | **細** |
| :--- | :--- | :--- | :--- |
| **slot 0** | draw | big | **small** |
| **slot 1** | **draws** | **bigger** | smaller |
| **slot 2** | drew | biggest | smallest |
| **slot 3** | drawn | biggish | smallish |
| **slot 4** | drawing | bigness | smallness |

咱 ewdangy 用表達 `draws bigger small` 匹配序列「畫大細」, 像 anssne:

```ruby
Matcher.new("draws bigger small").match([_ue, _dua, _sue])
```

英語有 qazsqizs 固有 ew 製組機制. 咱 ewdangy 用英語 validator 來 validate 漢字組.
