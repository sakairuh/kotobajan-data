# ことば雀 単語データ / Kotoba-jan word data

スマホゲーム「[ことば雀 - ひらがな麻雀](https://sakairuh.github.io/kotobajan/)」で使っている単語データです。
[JMdict](https://www.edrdg.org/wiki/index.php/JMdict-EDICT_Dictionary_Project)（Electronic Dictionary Research and Development Group）を加工して作りました。

Word data used in the smartphone game ["Kotoba-jan (ことば雀) - Hiragana Mahjong"](https://sakairuh.github.io/kotobajan/),
adapted from the JMdict dictionary files.

## 出典 / Attribution

This data includes material from the JMdict dictionary files. These files are the property of the
[Electronic Dictionary Research and Development Group](https://www.edrdg.org/), and are used in conformance
with the Group's [licence](https://www.edrdg.org/edrdg/licence.html).

- 元にした JMdict の版 / JMdict version: 2026-10-30

## 加えた変更 / Changes

- 名詞（普通名詞・動作を表す名詞・時を表す名詞）のうち、ひらがな2〜3文字の読みだけを取り出した。俗語・方言・古語・固有名詞などの語義は除いた
- よく使われる語を基本に、遊びに使う語を選んだ（固有名詞・不適切な語・数詞は除いた）
- 語にカテゴリ（38の小分類）を付けた
- 表記を並べる順と、語の身近さの段を加えた
- 語を組み合わせて、並べ替えパズルの問題集を作った

Extracted 2–3 character hiragana readings of nouns, selected the words used in the game, and added
categories, spelling order and familiarity levels. Also built a set of rearrangement puzzles from the words.

## ライセンス / License

[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)（全文は [LICENSE](LICENSE)）。
使うときは、JMdict（EDRDG）とこのデータの出典を示してください。加工したものを配るときは、同じ CC BY-SA 4.0 にしてください。

Licensed under CC BY-SA 4.0. Credit both JMdict (EDRDG) and this data, and share adaptations under the same license.

## ファイル / Files

| ファイル | 内容 | 件数 |
| --- | --- | --- |
| `words.json` | 遊びで単語になる読みの一覧と、元にした JMdict の版 | 5,339語 |
| `categories.json` | カテゴリの一覧（大分類・小分類）と、語ごとの小分類（1語に3つまで） | 1,550語・38小分類 |
| `spellings.json` | 語ごとの表記（漢字・カタカナ。札に出す順）と、カテゴリごとに先に出す表記 | 5,316語 |
| `familiarity.json` | 語ごとの身近さの段（1 が最も身近、3 まで） | 5,339語 |
| `puzzles.json` | 並べ替えパズルの問題集。元の5語と、身近な語でできた答え（先頭は5語がすべて同じ小分類になる答え） | 100問 |

### words.json

```json
{"jmdict_created": "2026-10-30", "words": ["あい", "あいご", "…"]}
```

### categories.json

```json
{
  "categories": [{"big": "食べ物", "small": "果物"}, "…"],
  "words": {"いちご": ["果物"], "はし": ["台所用品", "建物"]}
}
```

### spellings.json

```json
{
  "words": {"はし": ["箸", "橋", "端"], "いちご": ["苺", "一期"]},
  "categories": {"はし": {"台所用品": ["箸"], "建物": ["橋"]}}
}
```

### familiarity.json

```json
{"words": {"いちご": 1, "あいご": 3}}
```

### puzzles.json

元の5語（2・3・3・3・3文字）の牌を並べ替えて、元の語を1つも使わない5語を作るパズル。answers は身近な語でできた答え。
answers の先頭は、5語がすべて小分類 category の語になる答え。

Rearrange the tiles of five words into five different words. `answers` lists solutions made of familiar words.
The first one uses five words from the subcategory `category`.

```json
{"jmdict_created": "2026-10-30", "puzzles": [{"words": ["あゆ", "かぶき", "しゃつ", "ひばり", "らじお"], "answers": [["ゆば", "あぶら", "かつお", "しゃり", "ひじき"]], "category": "食材"}]}
```

## 単語の報告 / Reports

足りない単語、カテゴリの誤り、単語にならないはずの語（固有名詞・不適切な語など）、表記の誤りに気づいたら、
[issue](https://github.com/sakairuh/kotobajan-data/issues/new/choose) で知らせてください。データを直して、ゲームの次の更新に入れます。
今の辞書にある語か・どの分類に入っているかは、[ことば雀の辞書を引く](https://sakairuh.github.io/kotobajan/jisho/)で確かめられます。

Found a missing word, a wrong category, or a word that should not count? Please open an [issue](https://github.com/sakairuh/kotobajan-data/issues/new/choose).
You can look up a word and its categories on the [Kotoba-jan dictionary search](https://sakairuh.github.io/kotobajan/jisho/).

## 更新 / Updates

JMdict の新しい版に合わせて、少なくとも3か月に1回更新します。

Updated from the latest JMdict at least every three months.
