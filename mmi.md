# Duiy 程式 Qauy 人機介面

下腳是鐵 ew 英語翻譯. 頭一 ex iron diurw siw 鐵 ew 意思. 第二 ex iron-like diurw siw 像鐵 ew ew 意思:

| | **鐵** | |
| :--- | :--- | :--- |
| 1 | tih | iron |
| 2 | | iron-like |

若講 diurff 馬 ew 種類, 有一般 ew 馬 qahh 花條馬 ze 兩種. 一般 ew 馬英語號做 horse, 花條馬英語號做 zebra:

| | **馬** | |
| :--- | :--- | :--- |
| 1 | bey | horse |
| 2 | | zebra |

咱 ewtangy 創一个`horse`object:

```ruby
var horse = new Horse();
```

Qurhh 創一个`zebra`object:

```ruby
var zebra = new Zebra();
```

序列鐵馬是有二个漢字 ew 漢字組:

| | **鐵** | **馬** |
| :--- | :--- | :--- |
| **slot 0** | tih | bey |
| **slot 1** | tihy | be/bess |

鐵馬若用`Tihybey`來匹配, diurff 親像下腳 anssne:

| | **鐵** | **馬** |
| :--- | :--- | :--- |
| **slot 0** | tih | **bey** |
| **slot 1** | **tihy** | be/bess |

`Tihybey`有兩个意思: 一个是鐵做 ew 馬, 另外一个是 kongylingzs 車:

| | **鐵馬/tihybey** | |
| :--- | :--- | :--- |
| 1 | 鐵做 ew 馬 | iron horse |
| 2 | kongylingzx 車 | bicycle |

所以用變調造語 qaw`tih`qapp`bey`連結做伙變做`tihybey`, 用程式來表達 diurff 是像下腳 anssne:

```ruby
// iron horse
iron.take(horse);
```

紲落來 ewtangy qaw 使用者操作電腦所產生 ew event 交 how `iron` evaluate. 譬喻講提使用者 ew 輸入來做處理. 像`iron`伊 qaw`horse`當做 take method ew argument 了後, 咱 ew app diurff ewtangy diw 螢幕顯示兩个選項: 一 ex 是鐵做 ew 馬/iron horse, 另外一 ex 是 kongylingzs 車/bicycle. 使用者選擇一 ezs 選項了後, 譬喻講 siw 選 kongylingzs 車, `iron` diurw ewdangy qaw bicycle 當做siw context 處理, 像下腳 anssne:

```
iron.evaluate("bicycle")
```

紲落來, 咱 ewtangy diw 序列鐵馬進前加一字畫. Anssne 序列畫鐵馬是一个有三个漢字 ew 漢字組:

| | **畫** | **鐵** | **馬** |
| :--- | :--- | :--- | :--- |
| **slot 0** | uezs | tih | **bey** |
| **slot 1** | **uew** | **tihy** | be/bess |

創二个畫 ew 物件號做`draw`qahh`paint`:

```ruby
var draw = new Draw();
```

qahh:

```ruby
var paint = new Paint();
```

用變調造語 qaw`uezs`qahh`tihybey`連結起來 diurff 變做`uew tihybey`. 用程式碼 ewtangy anssne 表達:

```ruby
draw.take(iron);
```

qahh:

```ruby
paint.take(iron);
```

畫鐵馬用`uew tihybey`匹配了後, 加上使用者選擇`畫: draw, paint`eff`draw`, `鐵: iron, iron-like`eff`iron`, `馬: horse, zebra`eff`horse`, 螢幕頂 quanx diurff 會出現`draw iron horse`, `paint iron horse`, `draw bicycle`, qahh `paint bicycle` ze 四个選項 how 使用者:

| | **畫鐵馬/uew tihybey** | |
| :--- | :--- | :--- |
| 1 | 鐵做 ew 馬 | draw iron horse |
| 2 | | paint iron horse |
| 3 | kongylingzs 車 | draw bicycle |
| 4 | | paint bicycle |

## 修飾語

Dingssquanx ew drawObject 是主語, 英語單字 take 是動詞, ah ironObject 是賓語. 所以對品詞來看, 咱 ewdangy 利用各種無仝詞類 ew 修飾語來設計人機介面. 變調造語 maw ewdangy qahh 品詞綜合運用來做設計.
