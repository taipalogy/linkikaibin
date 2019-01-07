# Duiy 英語 Laizs 看

## 英語語形變化組成

Diw 下脚 ew 表格內底, lan qaw 語幹 `big` kngy diw slot 0. 了後 lan ewdangy qaw 語幹 `big` qahf 接尾語 `-er` 接 kihhwlaih vieny zury `bigger`, kngy diw slot 1. 紲 lurhhwlaih qaw `big` qahf `-est`, `-ish`, `-ness` 接 kihhwlaih, kngy diw 其他 ew slot 內底. 大 jih 表格 ewdangy qazs populate zury ansfne:

| | 大 |
| :--- | :--- |
| slot 0 | big |
| slot 1 | bigger |
| slot 2 | biggest |
| slot 3 | biggish |
| slot 4 | bigness |

Lan ewdangy iongw 表達 `big`, `bigger`, qahf `biggest` pitfpuey 序列 `大`, ciunnw ansfne:

```ruby
Matcher.new("big").match([_duazs])
Matcher.new("bigger").match([_duazs])
Matcher.new("biggest").match([_duazs])
```

Lan maw ewdangy iongw `small`, `smaller`, qahf `smallest` laizs populate 細 jih 表格:

| | 細 |
| :--- | :--- |
| slot 0 | small |
| slot 1 | smaller |
| slot 2 | smallest |
| slot 3 | smallish |
| slot 4 | smallness |

Lan ewdangy iongw 表達 `small`, `smaller`, qahf `smallest` pitfpuey 序列 `細`, ciunnw ansfne:

```ruby
Matcher.new("small").match([_suew])
Matcher.new("smaller").match([_suew])
Matcher.new("smallest").match([_suew])
```

Zimssmay lan ewdangy iongw `big` qahf `small` laizs 製組:

| | 大 | 細 |
| :--- | :--- | :--- |
| slot 0 | big | **small** |
| slot 1 | **bigger** | smaller |
| slot 2 | biggest | smallest |
| slot 3 | biggish | smallist |
| slot 4 | bigness | smallness |

Lan ewdangy iongw 表達 `bigger small` pitfpuey 序列 `大細`, ciunnw ansfne:

```ruby
Matcher.new("bigger small").match([_duazs, _suew])
```

| | 細 | 大 |
| :--- | :--- | :--- |
| slot 0 | small | **big** |
| slot 1 | **smaller** | bigger |
| slot 2 | smallest | biggest |
| slot 3 | smallish | biggish |
| slot 4 | smallness | bigness |

Lan ewdangy iongw 表達 `smaller big` pitfpuey 序列 `細大`, ciunnw ansfne:

```ruby
Matcher.new("smaller big").match([_suew, _duazs])
```

| | 畫 | 大 | 細 |
| :--- | :--- | :--- | :--- |
| slot 0 | draw | big | **small** |
| slot 1 | **draws** | **bigger** | smaller |
| slot 2 | drew | biggest | smallest |
| slot 3 | drawn | biggish | smallish |
| slot 4 | drawing | bigness | smallness |

Lan ewdangy iongw 表達 `draws bigger small` pitfpuey 序列 `畫大細`, ciunnw ansfne:

```ruby
Matcher.new("draws bigger small").match([_uezs, _duazs, _suew])
```

英語 uw qazsqizs 固有 ew 製組機制. Lan ewdangy iongw 英語 validator laizs validate 漢字組.
