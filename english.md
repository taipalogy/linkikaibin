# Tuiy 英語 Laiz 看

## 英語語形變化組成

Tiw 下脚 ew 表格內底, lan kaw 語幹 `big` khngy tiw slot 0. 了後 lan ewtangy kaw 語幹 `big` kahf 接尾語 `-er` 接 khih laih pieny churhy `bigger`, khngy tiw slot 1. 紲 lurhwlaih kaw `big` kahf `-est`, `-ish`, `-ness` 接 khih laih, khngy tiw 其他 ew slot 內底. 大 jih 表格 ewtangy kaz populate churhy anfne:

| | 大 |
| :--- | :--- |
| slot 0 | big |
| slot 1 | bigger |
| slot 2 | biggest |
| slot 3 | biggish |
| slot 4 | bigness |

Lan ewtangy iongw 表達 `big`, `bigger`, kahf `biggest` phitfphuey 序列 `大`, ciunnw anfne:

```ruby
Matcher.new("big").match([_big])
Matcher.new("bigger").match([_big])
Matcher.new("biggest").match([_big])
```

Lan maw ewtangy iongw `small`, `smaller`, kahf `smallest` laiz populate 細 jih 表格:

| | 細 |
| :--- | :--- |
| slot 0 | small |
| slot 1 | smaller |
| slot 2 | smallest |
| slot 3 | smallish |
| slot 4 | smallness |

Lan ewtangy iongw 表達 `small`, `smaller`, kahf `smallest` phitfphuey 序列 `細`, ciunnw anfne:

```ruby
Matcher.new("small").match([_small])
Matcher.new("smaller").match([_small])
Matcher.new("smallest").match([_small])
```

Chimfmay lan ewtangy iongw `big` kahf `small` laiz 製組:

| | 大 | 細 |
| :--- | :--- | :--- |
| slot 0 | big | **small** |
| slot 1 | **bigger** | smaller |
| slot 2 | biggest | smallest |
| slot 3 | biggish | smallist |
| slot 4 | bigness | smallness |

Lan ewtangy iongw 表達 `bigger small` phitfphuey 序列 `大細`, ciunnw anfne:

```ruby
Matcher.new("bigger & small").match([_big, _small])
```

| | 細 | 大 |
| :--- | :--- | :--- |
| slot 0 | small | **big** |
| slot 1 | **smaller** | bigger |
| slot 2 | smallest | biggest |
| slot 3 | smallish | biggish |
| slot 4 | smallness | bigness |

Lan ewtangy iongw 表達 `smaller big` phitfphuey 序列 `細大`, ciunnw anfne:

```ruby
Matcher.new("smaller & big").match([_small, _big])
```

| | 畫 | 大 | 細 |
| :--- | :--- | :--- | :--- |
| slot 0 | draw | big | **small** |
| slot 1 | **draws** | **bigger** | smaller |
| slot 2 | drew | biggest | smallest |
| slot 3 | drawn | biggish | smallish |
| slot 4 | drawing | bigness | smallness |

Lan ewtangy iongw 表達 `draws | bigger & small` phitfphuey 序列 `畫大細`, ciunnw anfne:

```ruby
Matcher.new("draws | bigger & small").match([_draw, _big, _small])
```

英語 uw kazkiz 固有 ew 製組機制. Lan ewtangy iongw 英語 validator laiz validate 漢字組.
