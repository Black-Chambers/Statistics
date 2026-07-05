# Chinese — Characters & Frequency Statistics

*Part of the Black Chambers letter-frequency series. See [Identification.md](../Identification.md) for the unknown-sample decision tree and encoding notes.*

## Language profile

| | |
|---|---|
| Script | **Hanzi** (Chinese characters) — logographic, caseless; horizontal LTR standard today, traditionally vertical RTL columns |
| Native speakers | ~940 million (Mandarin) — the most of any language |
| Total speakers | ~1.1 billion Mandarin; ~1.3 billion all Chinese varieties |
| Share of web content | ~1–2% in web surveys — a severe undercount; Chinese traffic lives inside platforms (WeChat, Weibo, Douyin) that public-web surveys can't crawl. Population is the honest prior. |
| Official language in | China, Taiwan, Singapore; one of six UN languages |
| Script variants | **Simplified** (mainland, Singapore) vs. **Traditional** (Taiwan, Hong Kong, Macau) — e.g., 国 vs. 國, 语 vs. 語 |

**Logographic** — each character represents a morpheme (a unit of meaning), usually one syllable, rather than a sound-letter.

> 💡 *In plain terms: instead of 26 letters that spell sounds, Chinese uses thousands of symbols where each one IS a word-chunk — imagine if `&`, `%`, and `#` each meant a whole word and the language had 8,000 of them. There is no alphabet to frequency-count in the European sense, which changes the whole cryptanalytic game.*

## Character inventory — the counts

There is no single "alphabet size"; the honest answer is a ladder:

| Scope | Count | Meaning |
|---|---|---|
| Table of General Standard Chinese Characters (通用规范汉字表, 2013) | **8,105** | PRC official standard set (3 tiers) |
| Tier 1 of that table | 3,500 | Full functional literacy |
| Practical reading threshold | ~2,500–3,000 | Covers ~99% of running newspaper text |
| Top 1,000 characters | — | Cover ~**90%** of running text |
| Top 100 characters | — | Cover ~**40%** of running text |
| Comprehensive dictionaries | 50,000–100,000+ | Overwhelmingly rare/historical/variant forms |

That steep coverage curve is the cryptanalytic headline: the distribution is *extremely* top-heavy — Zipf's law with a vengeance.

**Structure inside characters:** characters decompose into **radicals** (214 traditional Kangxi radicals; 201 in the PRC scheme) plus phonetic components — how dictionaries index them and how several encoding systems address them.

## Romanization: Pinyin

**Hànyǔ Pīnyīn** — the official Latin-alphabet transcription (1958). Uses 26 Latin letters (V unused, Ü added) plus four tone marks: `ā á ǎ à` (U+0101, U+00E1, U+01CE, U+00E0). Every character maps to one of only **~410 base syllables** (~1,300 with tones).

> 💡 *In plain terms: Pinyin is the "spell it in our letters" layer — and because Mandarin only has ~410 possible syllables, romanized Chinese is massively repetitive. Anyone attacking a cipher whose plaintext was romanized Chinese should work in syllable-space, not letter-space.*

## Character frequency (Simplified, modern corpora)

| # | Char | Pinyin | Meaning | ~% | # | Char | Pinyin | Meaning | ~% |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 的 | de | possessive particle | 4.1 | 11 | 大 | dà | big | 0.8 |
| 2 | 一 | yī | one | 1.6 | 12 | 中 | zhōng | middle | 0.8 |
| 3 | 是 | shì | to be | 1.5 | 13 | 上 | shàng | up/on | 0.8 |
| 4 | 不 | bù | not | 1.4 | 14 | 国 | guó | country | 0.7 |
| 5 | 了 | le | aspect particle | 1.3 | 15 | 个 | gè | measure word | 0.7 |
| 6 | 在 | zài | at/in | 1.1 | 16 | 到 | dào | arrive/to | 0.6 |
| 7 | 人 | rén | person | 1.1 | 17 | 说 | shuō | say | 0.6 |
| 8 | 有 | yǒu | have | 1.0 | 18 | 们 | men | plural marker | 0.6 |
| 9 | 我 | wǒ | I/me | 1.0 | 19 | 为 | wèi/wéi | for/as | 0.6 |
| 10 | 他 | tā | he | 0.9 | 20 | 和 | hé | and | 0.6 |

的 alone at ~4% is a crib on par with English THE — it's the possessive/attributive glue of the language.

## Index of Coincidence — why it breaks, and what to use instead

Classical letter-IC assumes a small closed alphabet. Over thousands of symbols, everything trends toward zero and the English-calibrated intuitions (0.0667 vs. 0.0385) are meaningless.

**What to use instead:**

1. **Character-level frequency matching.** With thousands of types, the *rank curve itself* is the fingerprint: if the top symbol takes ~4%, the top-100 take ~40%, and the tail is enormous, the plaintext behaves like Chinese.
2. **Work in the code domain.** Chinese has historically been transmitted as numbers — the **Chinese Telegraph Code** (标准电码, ~1880s) assigned each character a 4-digit group (e.g., 中 = 0022). Intercepts of "Chinese" ciphertext are often ciphers *on top of* 4-digit code groups: attack the group statistics, where 的's group is your E.
3. **Pinyin-domain analysis.** If the plaintext was romanized first, syllable-frequency tables (~410 symbols) restore a workable IC-style attack — compute IC over syllables, not letters. Letter-level analysis of pinyin also works but is distorted by the tiny syllable inventory (huge Q/X/Z counts relative to English).
4. **Input-method artifacts.** Modern Chinese is typed via pinyin, wubi, or cangjie input methods; leaked keystroke logs or intermediate buffers have their own statistics — a niche but real forensic angle.

> 💡 *In plain terms: you can't count letters in a language that doesn't have letters — so count something else: whole characters, the 4-digit telegraph numbers that stand for them, or the pinyin syllables. The lumpiness is still there; you just need the right-sized bucket.*

## Identification notes

| Question | Answer |
|---|---|
| Han characters mixed with curvy/angular little symbols (あ, カ)? | **Japanese**, not Chinese — kanji + kana mix. Pure Han-character running text is Chinese. |
| 国 学 语 (simpler forms) vs 國 學 語 (denser forms)? | Simplified (mainland/Singapore) vs. Traditional (Taiwan/HK/Macau) — narrows origin. |
| Unicode ranges | CJK Unified Ideographs U+4E00–U+9FFF (core), plus Extension blocks. Kana at U+3040–U+30FF means Japanese; Hangul U+AC00–U+D7AF means Korean. |
| No spaces between words? | Normal — Chinese doesn't use word spacing; segmentation is itself a computational problem. |

## Sources & caveats

Character-frequency figures compiled from published modern-corpus studies (news/web corpora, simplified forms); percentages rounded and corpus-dependent — classical Chinese and social-media text differ sharply. Character-set counts follow the 2013 PRC standard. Speaker counts follow Ethnologue-style estimates, approximate as of 2025–2026.
