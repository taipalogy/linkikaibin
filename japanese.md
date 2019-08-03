# Duiy 日語 Laiz 看

## 日語語形變化組成

Lan ewdangy iongw 日語 chury 仝欵 ew 代志.

| | 大 | 小 |
| :--- | :--- | :--- |
| slot 0 | 大きさ/ōkisa | **小ささ/chīsasa** |
| slot 1 | **大きな/ōkīna** | 小さな/chīsana |
| slot 2 | 大きい/ōkī | 小さい/chīsai |

Lan ewdangy iongw 表達 `ōkīna & chīsai` laiz pitfpoey `大小`, ciunnw 下脚 ancfne:

```ruby
Matcher.new("ōkīna & chīsasa").match([_oki, _chisai])
```

| | 小 | 大 |
| :--- | :--- | :--- |
| slot 0 | 小ささ/chīsasa | **大きさ/ōkisa** |
| slot 1 | **小さな/chīsana** | 大きな/ōkīna |
| slot 2 | 小さい/chīsai | 大きい/ōkī |

Lan ewdangy iongw 表達 `chīsana & ōkī` laiz pitfpoey `小大`, ciunnw 下脚 ancfne:

```ruby
Matcher.new("chīsana & ōkīsa").match([_chisai, _oki])
```

| | 画 | 大 | 小 |
| :--- | :--- | :--- | :--- |
| slot 0 | 画く/egaku | 大きさ/ōkisa | **小ささ/chīsasa** |
| slot 1 | **画き/egaki** | **大きな/ōkīna** | 小さな/chīsana |
| slot 2 | | 小さい/chīsai | 大きい/ōkī |

Lan ewdangy iongw 表達 `egaki | ōkīna & chīsasa` laiz pitfpoey 序列 `画大小`, ciunnw 下脚 ancfne:

```ruby
Matcher.new("egaki | ōkīna & chīsasa").match([_egaku, _oki, _chisai])
```

日語 uw iz qazqiz 固有 ew 造語機制. Lan ewdangy iongw 日語 validator laiz validate 漢字組.
