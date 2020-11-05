# 多義性

多義性 ew 英文 siw ambiguity. Lengwgoaw uw 一个單語 hurw churhy polysemy siw choanzmngz chi 語言上 uw 多義性. Lengwgoaw ambiguity kurhf uw 曖昧, 含糊 ew 意思, che siw ambiguity kahf polysemy siongw 大 ez 差別.

譬喻 kong table chitf 字, iz ewtangy chi 桌仔, maw ewtangy chi 表格. Che siw table ew 多義性. Kurhf khoanny book chitf 字, naw churhy 名詞用 tiurhw siw 冊 ew 意思. Naw churhy 動詞 tiurhw uw 預訂 ew 意思. Che siw book ew 多義性.

下脚 siw 一 ez uw 曖昧性, uw ambiguity ew 文:

`Open the chest with a key or a hammer.`

Chitf 句話 ew 意思 siw iongw 鎖匙 hekwchiafsiw 摃槌仔 kaw 箱仔拍 hoz 開. Sofi kaw 箱仔拍開 uw 二種方法, 一種 siw iongw 鎖匙 kaw 鎖拍開, lengwgoaw 一種 siw iongw 摃槌仔 kaz 摃 hoz 破. 下脚 siw 單語 kahf 文 ew 對應:

| 單語 | 意思 | 文 |
| :--- | :--- | :--- |
| open | open the chest | class OpenChest end |
| with | with sth | useKey |
| | | useHammer |
| unlock | unlock it | unlockIt |
| break | break it into pieces | breakIt |

Tuiy tengfkoanx ez 表格 ewtangy 看 cut laih, 單語 open uw 二 ez 隱含 ew 意思, 一个 siw unlock, lengwgoaw 一个 siw break. Naw behf unlock siw aiy iongw 鎖匙, naw behf break siw aiy iongw 摃槌仔. Che 二 ez 隱含 ew 意思 tiurhw siw chitflez 文 ew 曖昧性.

Chimfmay tiw che 表格每一行頭前 kez 二欄 thienzsia 對應 ew 台語:

| 台語 | 漢字 | 單語 | 意思 | 文 |
| :--- | :--- | :--- | :--- | :--- |
| khui | 開 | open | open the chest | class OpenChest end |
| six | 匙 | with | with a key/with sth | def useKey end |
||||| useKey |
| thuix | 槌 | | with a hammer/with sth | def useHammer end |
||||| useHammer |
| phah | 拍 | unlock | unlock it with a key | unlockIt |
| kongw | 摃 | break | break it into pieces with a hammer | breakIt |

Kurhf 來 tiw context 內底 ewtangy kazjipw 二條規則:

```ruby
context.add([_pah, _six, 1])
context.add([_qongw, _tuix, 1])
```

頭一條規則 siw kong 拍 behf thehw 匙 ew 頭一个定義 `def useKey end` laiz 用, tiurhw siw behf iongw 鎖匙 kaw 箱仔拍 hoz 開. 第二條規則 siw kong 摃 behf thehw 槌 ew 頭一个定義 `def useHammer end` laiz 用, tiurhw siw behf iongw 摃槌仔 kaw 箱仔摃 hoz 破. Sofi lan naw siw kaw che 幾若个單語 lienzkietf churhy 下脚 che 二句話:

```
Siz phah. Thuiz qongw.
```

Inzuiw six, phah, thuix, kahf kongw che 四个單語 pieny churhy che 四句話: `Siz`, `phah`, `Thuiz`, `kongw`, sofi che 四句 `Siz`, `phah`, `Thuiz`, kahf `kongw` tiurhw siw taiwpiau `Siz phah.` kahf `Thuiz kongw.` che 二 ez 相嵌 ew 文:

```ruby
#
# Siz pah. Tuiz qongw.
#
def useKey
  unlockIt
end

def useHammer
  breakIt
end
```

Lan chimfmay kurhf thehw `Khuiz` kaw che 四句 `Siz`, `phah`, `Thuiz`, `kongw` 接 khih laih, iaw tiurhw siw kaw `def useKey unlockIt end def useHammer breakIt end` khamy lihwkhi `class OpenChest end` chitflez 文內底:

```ruby
#
# Kuiz Siz pah. Tuiz qongw..
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

Inzuiw `Khuiz` siw 變調 kurhf uw iongw 括號 kaw `Siz phah. Thuiz kongw.` 括 khih laih, kurhf kazsiongw 文尾 ew 句點, sofi kahf `Khuiz` 對應 ew `class OpenChest end` tiurhw ewtangy kaw che 四个文嵌 lih khih.
