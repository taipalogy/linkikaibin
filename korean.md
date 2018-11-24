# 對韓語來看

## 韓語語形變化組成

咱 ewdangy 用韓語做仝欵 ew 代誌.

| | **大** | **小** |
| :--- | :--- | :--- |
| **slot 0** | 크기/keugi | **작기/jaggi** |
| **slot 1** | **큰/keun** | 작은/jageun |
| **slot 2** | 크다/keuda | 작다/jagda |

咱 ewdangy 用表達 `keun & jaggi` 來匹配「大小」, 像下腳 anssne:

```ruby
Matcher.new("keun & jaggi").match([_keuda, _jagda])
```

| | **小** | **大** |
| :--- | :--- | :--- |
| **slot 0** | 작기/jaggi | **크기/keugi** |
| **slot 1** | **작은/jageun** | 큰/keun |
| **slot 2** | 작다/jagda | 크다/keuda |

咱 ewdangy 用表達 `jageun & keugi` 來匹配「小大」, 像下腳 anssne:

```
Matcher.new("jageun & keugi").match([_jagda, _keuda])
```

| | **畫** | **大** | **小** |
| :--- | :--- | :--- | :--- |
| **slot 0** | 그리다/geulida | 크기/keugi | **작기/jaggi** |
| **slot 1** | **그리는/geulineun** | **큰/keun** | 작은/jageun |
| **slot 2** | | 크다/keuda | 작다/jagda |

咱 ewdangy 用表達 `geulineun | keun & jaggi` 來匹配序列「畫大小」, 像下腳 anssne:

```ruby
Matcher.new("geulineun | keun & jaggi").match([_geulida, _keuda, _jagda])
```

韓語有伊 qazsqizs 固有 ew 造語機制. 咱 ewdangy 用韓語 validator 來 validate 漢字組.
