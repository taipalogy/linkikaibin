# 對日語來看

## 日語語形變化組成

咱 ewdangy 用日語做仝欵 ew 代誌.

| | **大** | **小** |
| :--- | :--- | :--- |
| **slot 0** | 大きさ/ōkisa | **小ささ/chīsasa** |
| **slot 1** | **大きな/ōkīna** | 小さな/chīsana |
| **slot 2** | 大きい/ōkī | 小さい/chīsai |

咱 ewdangy 用表達 `ōkīna & chīsai` 來匹配「大小」, 像下腳 anssne:

```ruby
Matcher.new("ōkīna & chīsasa").match([_oki, _chisai])
```

| | **小** | **大** |
| :--- | :--- | :--- |
| **slot 0** | 小ささ/chīsasa | **大きさ/ōkisa** |
| **slot 1** | **小さな/chīsana** | 大きな/ōkīna |
| **slot 2** | 小さい/chīsai | 大きい/ōkī |

咱 ewdangy 用表達 `chīsana & ōkī` 來匹配「小大」, 像下腳 anssne:

```ruby
Matcher.new("chīsana & ōkīsa").match([_chisai, _oki])
```

| | **画** | **大** | **小** |
| :--- | :--- | :--- | :--- |
| **slot 0** | 画く/egaku | 大きさ/ōkisa | **小ささ/chīsasa** |
| **slot 1** | **画き/egaki** | **大きな/ōkīna** | 小さな/chīsana |
| **slot 2** | | 小さい/chīsai | 大きい/ōkī |

咱 ewdangy 用表達 `egaki | ōkīna & chīsasa` 來匹配序列「画大小」, 像下 腳 anssne:

```ruby
Matcher.new("egaki | ōkīna & chīsasa").match([_egaku, _oki, _chisai])
```

日語有伊 qazsqizs 固有 ew 造語機制. 咱 ewdangy 用日語 validator 來 validate 漢字組.
