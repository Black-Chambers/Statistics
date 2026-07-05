# Spanish — Letters & Frequency Statistics

*Part of the Black Chambers letter-frequency series. See [Identification.md](../Identification.md) for the unknown-sample decision tree and encoding notes.*

## Language profile

| | |
|---|---|
| Script | Latin alphabet, cased (upper/lower), left-to-right |
| Native speakers | ~485 million (~6% of world population) — 2nd most native speakers after Mandarin |
| Total speakers (L1+L2) | ~600 million |
| Share of web content | ~6% (typically 2nd–4th place) |
| Official language in | 20 countries + Puerto Rico; regulated by the Real Academia Española (RAE) |
| Easily confused with | Portuguese, Italian (shared script, similar vowel-heavy profile) |

## Alphabet

**27 letters** — the 26 of English plus **Ñ**. Since the RAE's 2010 reform, the digraphs *ch* and *ll* are no longer counted as separate letters (older references list 29).

| Char | Name | Unicode (upper/lower) | Notes |
|---|---|---|---|
| A a | a | U+0041 / U+0061 | |
| B b | be | U+0042 / U+0062 | B and V sound identical in Spanish |
| C c | ce | U+0043 / U+0063 | |
| D d | de | U+0044 / U+0064 | |
| E e | e | U+0045 / U+0065 | |
| F f | efe | U+0046 / U+0066 | |
| G g | ge | U+0047 / U+0067 | |
| H h | hache | U+0048 / U+0068 | Always silent |
| I i | i | U+0049 / U+0069 | |
| J j | jota | U+004A / U+006A | |
| K k | ka | U+004B / U+006B | Loanwords only — extremely rare |
| L l | ele | U+004C / U+006C | |
| M m | eme | U+004D / U+006D | |
| N n | ene | U+004E / U+006E | |
| Ñ ñ | eñe | U+00D1 / U+00F1 | A distinct letter, not "N with decoration"; sorts after N |
| O o | o | U+004F / U+006F | |
| P p | pe | U+0050 / U+0070 | |
| Q q | cu | U+0051 / U+0071 | Only in `que`/`qui` — Q is always followed by U |
| R r | erre | U+0052 / U+0072 | |
| S s | ese | U+0053 / U+0073 | |
| T t | te | U+0054 / U+0074 | |
| U u | u | U+0055 / U+0075 | |
| V v | uve | U+0056 / U+0076 | |
| W w | uve doble | U+0057 / U+0077 | Loanwords only — rarest letter |
| X x | equis | U+0058 / U+0078 | |
| Y y | ye / i griega | U+0059 / U+0079 | |
| Z z | zeta | U+005A / U+007A | |

**Accented vowels** — `á é í ó ú` (U+00E1, U+00E9, U+00ED, U+00F3, U+00FA) and `ü` (U+00FC, only in `güe`/`güi`). These mark stress, **not** different letters: they sort with their base vowel and are routinely stripped in ciphertext.

**Punctuation fingerprint:** inverted question and exclamation marks `¿` (U+00BF) and `¡` (U+00A1) open questions/exclamations. Nothing else in common use looks like this — if you see `¿`, you're looking at Spanish.

## Letter frequency

Diacritics folded (á→A etc.), as ciphertext almost always is. Percentages are corpus-dependent; treat ±0.5 pt as normal variation.

| # | Letter | % | # | Letter | % |
|---|---|---|---|---|---|
| 1 | E | 13.7 | 15 | P | 2.5 |
| 2 | A | 12.5 | 16 | B | 1.4 |
| 3 | O | 8.7 | 17 | G | 1.0 |
| 4 | S | 8.0 | 18 | V | 0.9 |
| 5 | R | 6.9 | 19 | Y | 0.9 |
| 6 | N | 6.7 | 20 | Q | 0.9 |
| 7 | I | 6.2 | 21 | H | 0.7 |
| 8 | D | 5.9 | 22 | F | 0.7 |
| 9 | L | 5.0 | 23 | Z | 0.5 |
| 10 | C | 4.7 | 24 | J | 0.4 |
| 11 | T | 4.6 | 25 | Ñ | 0.3 |
| 12 | U | 3.9 | 26 | X | 0.2 |
| 13 | M | 3.2 | 27 | K, W | <0.1 |
| 14 | | | | | |

Vowels (A E I O U) total **~47%** of Spanish text — among the highest of major European languages.

## Index of Coincidence

**IC ≈ 0.0770** (26/27-letter domain). Random baseline: 0.0385.

> 💡 *In plain terms: IC measures how "lumpy" the letter distribution is — pull two letters from a bag of the message and see how often they match. Spanish is lumpier than English (0.0667) because E and A together hog a quarter of all text. A monoalphabetic cipher of Spanish keeps this lumpiness; a Vigenère flattens it toward 0.0385. See [Identification.md](../Identification.md) for the full explanation.*

## N-grams and structure

| Top bigrams | Top trigrams | Frequent short words |
|---|---|---|
| DE, ES, EN, EL, LA, OS, ON, AS, ER, RA | QUE, EST, ARA, ADO, CON, ENT, DEL | de, la, que, el, en, y, a, los, se, no |

- **Q is a gift:** in native Spanish, Q appears *only* in `QUE`/`QUI`. In a monoalphabetic cipher, any letter always followed by the same second letter is a Q→U candidate, and the trigram behind it is probably `QUE` — one of the most common words in the language.
- Nearly all words end in a **vowel, N, S, R, L, D, or Z**. Word-final ciphertext letters cluster hard.
- **Double letters are rare** (mainly LL, RR, CC, and NN across morpheme boundaries) — far rarer than English's ee/oo/ss/tt crowd. A ciphertext with many doubled letters argues against Spanish plaintext.
- H is silent and low-frequency (0.7% vs. English's 6%) — the near-absence of the TH-partner pattern separates Spanish from English fast.

## Telling Spanish apart from its neighbors

| vs. | Discriminator |
|---|---|
| Portuguese | Portuguese has **A as #1** letter (~14.6%); Spanish has E. Portuguese uses `ã õ ç`; Spanish never does. Spanish `ñ` ≈ Portuguese `nh`. |
| Italian | Italian lacks Ñ and rarely uses K J W X Y at all; Italian text is full of doubled consonants, Spanish text isn't. |
| French | French E is even higher (~14.7%) and French text bristles with apostrophes (`l'`, `d'`) — Spanish barely uses the apostrophe. |

## Sources & caveats

Frequencies compiled from published Spanish corpus studies (newspaper and literary corpora); figures rounded and corpus-dependent. Speaker counts follow Ethnologue/Instituto Cervantes-style estimates, approximate as of 2025–2026.
