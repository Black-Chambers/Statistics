# Identifying an Unknown Language Sample

*Part of the Black Chambers letter-frequency series. Each language links to a detailed `Letters.md` page with full frequency tables and cipher notes.*

Before you can attack a cipher, you usually need to know (or guess) the **plaintext language** — frequency analysis against the wrong language's tables will send you in circles. This page is a decision tree: start at Step 1 and stop as soon as you have a confident match.

> 💡 *In plain terms: this page is the field guide. You found a strange bird; flip through until the picture matches.*

---

## Step 1 — What script is it?

The script (writing system) eliminates most candidates instantly.

| Script | Looks like | Candidate languages | Direction |
|---|---|---|---|
| Latin | `A B C … Z` plus accents | Spanish, French, German, Italian, Portuguese, English, Dutch, Polish, Turkish, and most of Europe/Americas | LTR |
| Cyrillic | `А Б В Г Д Ж И Й` | [Russian](Russian/Letters.md), Ukrainian, Bulgarian, Serbian, Kazakh | LTR |
| Greek | `α β γ δ ε λ Σ Ω` | [Greek](Greek/Letters.md) only (modern use) | LTR |
| Arabic | `ا ب ت ث ج` — cursive, connected | [Arabic](Arabic/Letters.md), Persian/Farsi, Urdu, Pashto | RTL |
| Hebrew | `א ב ג ד ה` — square, disconnected | [Hebrew](Hebrew/Letters.md), Yiddish | RTL |
| Han characters (Hanzi/Kanji) | `的 是 不 了` — dense, boxy | [Chinese](Chinese/Letters.md); Japanese if mixed with kana | Mixed |
| Kana (hiragana/katakana) | `あ か さ / ア カ サ` — simple, curvy/angular | Japanese (always mixed with kanji in real text) | Mixed |
| Hangul | `한 국 어` — syllable blocks of 2–3 parts | Korean | LTR |
| Devanagari | `अ क ख ग` — letters hanging from a top bar | Hindi, Marathi, Nepali, Sanskrit | LTR |

> 💡 *In plain terms: you can tell a newspaper is Russian, Arabic, or Chinese from across the room without reading a word. Do that first.*

**Homoglyph warning:** Cyrillic `А Е О Р С Х` (U+0410, U+0415, U+041E, U+0420, U+0421, U+0425) look identical to Latin `A E O P C X` but are different codepoints. If your sample is digital, check codepoints, not just appearance. See the encoding notes at the bottom of this page.

---

## Step 2 — Latin script: check the "fingerprint" characters

If the script is Latin, distinctive letters and diacritics narrow it fast:

| You see… | Strong signal for | Details |
|---|---|---|
| `ñ`, inverted `¿ ¡` | **Spanish** | [Spanish/Letters.md](Spanish/Letters.md) |
| `ç`, `œ`, `à è ù`, `ê â î ô û`, many apostrophes (`l'`, `d'`, `qu'`) | **French** | [French/Letters.md](French/Letters.md) |
| `ä ö ü`, `ß`, very long capitalized words mid-sentence | **German** | [German/Letters.md](German/Letters.md) |
| Almost no `k j w x y`; words ending in vowels; doubled consonants (`tt`, `zz`, `ll`) | **Italian** | [Italian/Letters.md](Italian/Letters.md) |
| `ã õ` (nasal tildes on vowels), `ç`, `-ção` endings | **Portuguese** | [Portuguese/Letters.md](Portuguese/Letters.md) |
| `ł ż ź ą ę ś ć`, consonant clusters (`szcz`) | Polish (Tier 2 — no page yet) |
| Dotless `ı`, `ğ ş`, vowel harmony patterns | Turkish (Tier 2) |
| `ij` pairs, doubled vowels (`aa`, `ee`, `oo`) | Dutch (Tier 2) |
| No diacritics at all, `th` everywhere, `q` always followed by `u` | English |

**Caution:** telegraph, classical ciphers, and lazy typists strip diacritics (`é`→`E`, `ñ`→`N`). If the sample is diacritic-free uppercase, skip to Step 3 — every Latin-script `Letters.md` page includes a **folded** (diacritic-stripped) frequency table for exactly this case.

---

## Step 3 — Frequency check

Count letter frequencies in the sample (even 100–200 characters gives a usable profile) and compare against the tables in each language page. Fast discriminators:

| Signal | Suggests |
|---|---|
| One letter near **17–18%** | German (E) |
| **E ≈ 14–15%**, next letters bunched around 6–8% | French |
| **A is #1** (not E), around 14% | Portuguese |
| **E, A** both above 11%, close together | Spanish |
| **E, A, I, O** all above 9–11% (four heavy vowels) | Italian |
| Vowels total **~48%** of text | Italian or Spanish |
| Vowels total **~38–40%** | German or English |

---

## Step 4 — Index of Coincidence (IC)

**Index of Coincidence** — the probability that two characters drawn at random from the text are the same letter. Formula for a text of length *N* with letter counts *nᵢ*:

```
IC = Σ nᵢ(nᵢ − 1) / [ N(N − 1) ]
```

> 💡 *In plain terms: dump every letter of the message into a bag, pull out two, and ask "do they match?" Real language has favorite letters (lots of E's), so matches come up often. Random gibberish spreads evenly, so matches are rare. IC is a single number that tells you "this smells like language" vs. "this smells like static."*

### Reference values (26-letter Latin domain unless noted)

| Text type | IC |
|---|---|
| Uniformly random, 26 letters | 0.0385 |
| English | ~0.0667 |
| Italian | ~0.0738 |
| Portuguese | ~0.0745 |
| German | ~0.0762 |
| Spanish | ~0.0770 |
| French | ~0.0778 |
| Greek (24 letters) | ~0.069 |
| Russian (Cyrillic, 32–33 letters) | ~0.0529 |
| Uniformly random, 33 letters | 0.0303 |

**Two critical caveats:**

1. **IC depends on alphabet size.** Russian's 0.0529 is *lower* than English's 0.0667 not because Russian is "more random" but because matches are spread over 33 letters instead of 26. Don't conclude a Cyrillic ciphertext is polyalphabetic just because its IC looks low by English standards — compare against the *right* baseline (random-for-that-alphabet vs. language-for-that-alphabet).

   > 💡 *In plain terms: a bag with 33 kinds of marbles gives fewer matched pairs than a bag with 26 kinds, even if both bags play favorites equally hard. Judge each bag against its own "fair" version.*

2. **IC survives simple substitution.** Monoalphabetic ciphers (Caesar, keyword substitution, Atbash) rename the letters but keep the frequency lumps, so IC stays at the language value. Polyalphabetic ciphers (Vigenère) flatten the lumps and drag IC toward random. That makes IC your first cipher-classification test, not just a language test.

Logographic and syllabic systems (Chinese, Japanese) break letter-IC entirely — see those pages for what to use instead.

---

## Step 5 — Which languages are you most likely to encounter?

Prior probability matters. Approximate shares (figures shift yearly; treat as order-of-magnitude):

| Language | Native speakers | Total speakers (L1+L2) | Share of web content* |
|---|---|---|---|
| English | ~380 M | ~1.5 B | ~49% |
| Chinese (Mandarin) | ~940 M | ~1.1 B | ~1–2%* |
| Spanish | ~485 M | ~600 M | ~6% |
| Arabic (all varieties) | ~380 M | ~420 M | ~0.6%* |
| French | ~80 M | ~320 M | ~4.4% |
| Portuguese | ~235 M | ~265 M | ~3.8% |
| Russian | ~145 M | ~255 M | ~4–5% |
| German | ~76 M | ~135 M | ~5.6% |
| Italian | ~64 M | ~68 M | ~2.7% |
| Greek | ~13.5 M | ~13.5 M | ~0.7% |
| Hebrew | ~9 M | ~9 M | ~0.2% |

\* Web-content figures (W3Techs-style surveys of public websites) badly **undercount Chinese and Arabic**, whose traffic lives largely inside apps and platforms those surveys can't crawl. Population figures are the better prior for intercepted personal communications; web share is the better prior for scraped/public text.

---

## Encoding notes for this repo (read before copying tables into scripts)

- All character tables in this series use **literal UTF-8 characters** plus their **U+ codepoints**. If a character renders as an empty box `□` (or as U+FFFD, the "replacement character" diamond-question-mark), your font lacks the glyph — the codepoint column still identifies it.
- All files are **NFC-normalized**: accented letters are single precomposed codepoints (`ñ` = U+00F1), never base letter + combining mark (`n` + U+0303). The two render identically but are different strings — a classic source of "why doesn't my regex match" bugs.

  > 💡 *In plain terms: "ñ" can be stored as one Lego brick or as two bricks snapped together. They look the same on screen but they're different under the hood. This repo always uses the single brick.*
- Right-to-left characters (Arabic, Hebrew) inside tables are wrapped in `code spans` to stop the bidirectional-text algorithm from visually scrambling table columns. The tables read left-to-right even though the languages don't.
- Beware **homoglyphs** when analyzing digital samples: Latin `A` (U+0041) vs. Cyrillic `А` (U+0410) vs. Greek `Α` (U+0391) are three different characters that render identically in most fonts. A frequency count that treats them as one letter will be wrong; so will one that doesn't notice the sample is secretly mixed-script (a favorite phishing and steganography trick).

---

## Language pages in this series

| Tier 1 (full pages) | |
|---|---|
| [Spanish](Spanish/Letters.md) | [Russian](Russian/Letters.md) |
| [French](French/Letters.md) | [Greek](Greek/Letters.md) |
| [German](German/Letters.md) | [Hebrew](Hebrew/Letters.md) |
| [Italian](Italian/Letters.md) | [Arabic](Arabic/Letters.md) |
| [Portuguese](Portuguese/Letters.md) | [Chinese](Chinese/Letters.md) |

**Tier 2 (identification rows above only, pages may follow):** Japanese, Korean, Dutch, Turkish, Polish, Hindi.

---

## Sources & caveats

Frequency and IC figures are compiled from published corpus studies (newspaper, literary, and web corpora) and standard cryptology references; exact percentages vary by corpus, era, and genre — a legal corpus and a chat-log corpus of the same language can differ by a full percentage point on top letters. Values here are rounded and intended for cipher-solving discrimination, not linguistic research. Speaker counts follow Ethnologue-style estimates; web-content shares follow W3Techs-style surveys. All figures are approximate as of 2025–2026.
