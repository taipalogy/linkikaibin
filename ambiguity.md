# 多義性

多義性 ew 英文 siw ambiguity. Lengwgoaw uw 一个單語 hurw zury polysemy siw zoanzsmngzs zi 語言上 uw 多義性. Lengwgoaw ambiguity qurhf uw 曖昧, 含糊 ew 意思, ze siw ambiguity qahf polysemy siongw 大 ezs 差別.

譬喻 qong table zitf 字, izs ewdangy zi 桌仔, maw ewdangy zi 表格. Ze siw table ew 多義性. Qurhf koanny book zitf 字, naw zury 名詞用 diurhhw siw 冊 ew 意思. Naw zury 動詞 diurhhw uw 預訂 ew 意思. Ze siw book ew 多義性.

下脚 siw 一 ezs uw 曖昧性, uw ambiguity ew 文:

`Open the chest with a key or a hammer.`

Zitf 句話 ew 意思 siw iongw 鎖匙 hekkwziacssiw 摃槌仔 qaw 箱仔拍 hozs 開. Socsi qaw 箱仔拍開 uw 二種方法, 一種 siw iongw 鎖匙 qaw 鎖拍開,  lengwgoaw 一種 siw iongw 摃槌仔 qazs 摃 hozs 破. 下脚 siw 單語 qahf 文 ew 對應:

| 單語 | 意思 | 文 |
| :--- | :--- | :--- |
| open | open the chest | class OpenChest end |
| with | with sth | useKey |
| | | useHammer |
| unlock | unlock it | unlockIt |
| break | break it into pieces | breakIt |

Duiy dengcsqoanx ezs 表格 ewdangy 看 cuttwlaih, 單語 open uw 二 ezs 隱含 ew 意思, 一个 siw unlock, lengwgoaw 一个 siw break. Naw behf unlock siw aiy iongw 鎖匙, naw behf break siw aiy iongw 摃槌仔. Ze 二 ezs 隱含 ew 意思 diurhhw siw zitflezs 文 ew 曖昧性.

Zimcsmay diw ze 表格每一行頭前 qezs 二欄 tienzssia 對應 ew 台語:

| 台語 | 漢字 | 單語 | 意思 | 文 |
| :--- | :--- | :--- | :--- | :--- |
| kui | 開 | open | open the chest | class OpenChest end |
| six | 匙 | with | with a key/with sth | def useKey end |
||||| useKey |
| tuix | 槌 | | with a hammer/with sth | def useHammer end |
||||| useHammer |
| pah | 拍 | unlock | unlock it with a key | unlockIt |
| qongw | 摃 | break | break it into pieces with a hammer | breakIt |

Qurhf 來 diw context 內底 ewdangy qazsjippw 二條規則:

```ruby
context.add([_pah, _six, 1])
context.add([_qongw, _tuix, 1])
```

頭一條規則 siw qong 拍 behf tehhw 匙 ew 頭一个定義 `def useKey end` laizs 用, diurhhw siw behf iongw 鎖匙 qaw 箱仔拍 hozs 開. 第二條規則 siw qong 摃 behf tehhw 槌 ew 頭一个定義 `def useHammer end` laizs 用, diruhhw siw behf iongw 摃槌仔 qaw 箱仔摃 hozs 破. Socsi lan naw siw qaw ze 幾若个單語 lienzsqietf zury 下脚 ze 二句話:

```
Sizs pah. Tuizs qongw.
```

Inzsuiw six, pah, tuix, qahf qongw ze 四个單語 vieny zury ze 四句話: `Sizs`, `pah`, `Tuizs`, `qongw`, socsi ze 四句 `Sizs`, `pah`, `Tuizs`, qahf `qongw` diurhhw siw daiwviau `Sizs pah.` qahf `Tuizs qongw.` ze 二 ezs 相嵌 ew 文:

```ruby
#
# Sizs pah. Tuizs qongw.
#
def useKey
  unlockIt
end

def useHammer
  breakIt
end
```

Lan zimcsmay qurhf tehhw `Kuizs` qaw ze 四句 `Sizs`, `pah`, `Tuizs`, `qongw` 接 kihhwlaih, iaw diurhhw siw qaw `def useKey unlockIt end def useHammer breakIt end` kamy lihhwki `class OpenChest end` zitflezs 文內底:

```ruby
#
# Kuizs Sizs pah. Tuizs qongw..
#
class OpenChest

  def useKey
    unlockIt
  end

  def useHammer
    breakIt
  end

end
```

Inzsuiw `Kuizs` siw 變調 qurhf uw iongw 括號 qaw `Sizs pah. Tuizs qongw.` 括 kihhwlaih, qurhf qazssiongw 文尾 ew 句點,  socsi qahf `Kuizs` 對應 ew `class OpenChest end` diurhhw ewdangy qaw ze 四个文嵌 jihhwkih.
