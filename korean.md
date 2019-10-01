# Duiy 韓語 Laiz 看

## 韓語語形變化組成

Lan ewdangy iongw 韓語 chury 仝欵 ew 代志.

| | 大 | 小 |
| :--- | :--- | :--- |
| slot 0 | 크기/keugi | **작기/jaggi** |
| slot 1 | **큰/keun** | 작은/jageun |
| slot 2 | 크다/keuda | 작다/jagda |

Lan ewdangy iongw 表達 `keun & jaggi` laiz pitfpoey `大小`, ciunnw 下脚 anfne:

```ruby
Matcher.new("keun & jaggi").match([_keuda, _jagda])
```

| | 小 | 大 |
| :--- | :--- | :--- |
| slot 0 | 작기/jaggi | **크기/keugi** |
| slot 1 | **작은/jageun** | 큰/keun |
| slot 2 | 작다/jagda | 크다/keuda |

Lan ewdangy iongw 表達 `jageun & keugi` laiz pitfpoey `小大`, ciunnw 下脚 anfne:

```ruby
Matcher.new("jageun & keugi").match([_jagda, _keuda])
```

| | 畫 | 大 | 小 |
| :--- | :--- | :--- | :--- |
| slot 0 | 그리다/geulida | 크기/keugi | **작기/jaggi** |
| slot 1 | **그리는/geulineun** | **큰/keun** | 작은/jageun |
| slot 2 | | 크다/keuda | 작다/jagda |

Lan ewdangy iongw 表達 `geulineun | keun & jaggi` laiz pitfpoey 序列 `畫大小`, ciunnw 下脚 anfne:

```ruby
Matcher.new("geulineun | keun & jaggi").match([_geulida, _keuda, _jagda])
```

韓語 uw iz qazqiz 固有 ew 造語機制. Lan ewdangy iongw 韓語 validator laiz validate 漢字組.
