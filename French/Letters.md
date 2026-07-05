# French — Letters & Frequency Statistics

*Part of the Black Chambers letter-frequency series. See [Identification.md](../Identification.md) for the unknown-sample decision tree and encoding notes.*

## Language profile

| | |
|---|---|
| Script | Latin alphabet, cased, left-to-right |
| Native speakers | ~80 million |
| Total speakers (L1+L2) | ~320 million — one of the largest L2 populations in the world |
| Share of web content | ~4.4% |
| Official language in | 29 countries (France, Canada, Belgium, Switzerland, much of Africa); regulated by the Académie Française |
| Easily confused with | Other Latin-script Romance languages; the apostrophes and accents give it away |

## Alphabet

**26 base letters** (identical inventory to English) plus a rich diacritic layer that is part of correct spelling but usually stripped in ciphertext.

Base letters: `A–Z`, U+0041–U+005A / U+0061–U+007A. Names and inventory match English; the action is in the accents:

| Char | Name | Unicode (upper/lower) | Used on |
|---|---|---|---|
| É é | e accent aigu | U+00C9 / U+00E9 | E only — by far the most common accented letter |
| È è | e accent grave | U+00C8 / U+00E8 | |
| À à | a accent grave | U+00C0 / U+00E0 | |
| Ù ù | u accent grave | U+00D9 / U+00F9 | Exactly one word: `où` ("where") |
| Ê ê | e circonflexe | U+00CA / U+00EA | |
| Â â | a circonflexe | U+00C2 / U+00E2 | |
| Î î | i circonflexe | U+00CE / U+00EE | |
| Ô ô | o circonflexe | U+00D4 / U+00F4 | |
| Û û | u circonflexe | U+00DB / U+00FB | |
| Ë ë | e tréma | U+00CB / U+00EB | |
| Ï ï | i tréma | U+00CF / U+00EF | |
| Ü ü | u tréma | U+00DC / U+00FC | Rare |
| Ç ç | c cédille | U+00C7 / U+00E7 | Marks soft C before A/O/U (`ça`, `français`) |
| Œ œ | e dans l'o (ligature) | U+0152 / U+0153 | `œuvre`, `cœur` — a true ligature letter, often typed as `oe` |
| Æ æ | ligature | U+00C6 / U+00E6 | Rare, Latin borrowings |

> 💡 *In plain terms: French has the same 26 Lego bricks as English, plus a bag of stickers (accents) that go on some bricks. The stickers matter for spelling but fall off in most ciphers — so we count both ways below.*

## Letter frequency (diacritics folded)

é→E, ç→C, etc. — the form ciphertext takes. Corpus-dependent; ±0.5 pt is normal.

| # | Letter | % | # | Letter | % |
|---|---|---|---|---|---|
| 1 | E | 14.7 | 14 | P | 3.0 |
| 2 | S | 7.9 | 15 | V | 1.6 |
| 3 | A | 7.6 | 16 | Q | 1.4 |
| 4 | I | 7.5 | 17 | F | 1.1 |
| 5 | T | 7.2 | 18 | B | 0.9 |
| 6 | N | 7.1 | 19 | G | 0.9 |
| 7 | R | 6.6 | 20 | H | 0.7 |
| 8 | U | 6.3 | 21 | J | 0.6 |
| 9 | L | 5.5 | 22 | X | 0.4 |
| 10 | O | 5.8 | 23 | Z | 0.3 |
| 11 | D | 3.7 | 24 | Y | 0.3 |
| 12 | C | 3.3 | 25 | K | 0.05 |
| 13 | M | 3.0 | 26 | W | 0.04 |

With diacritics **kept**, `é` alone runs ~1.9% — more common than half the base alphabet — and E drops to ~12.1%. If your sample retains accents, use the unfolded view; the presence of `é` at ~2% is itself a French fingerprint.

## Index of Coincidence

**IC ≈ 0.0778** — the highest of the major Latin-script languages, driven by E's dominance. Random baseline: 0.0385. English: 0.0667.

> 💡 *In plain terms: French leans on the letter E harder than any of its neighbors — nearly one letter in seven. More favoritism = more matched pairs when you draw two letters from the bag = higher IC. See [Identification.md](../Identification.md).*

## N-grams and structure

| Top bigrams | Top trigrams | Frequent short words |
|---|---|---|
| ES, LE, EN, DE, RE, NT, ON, ER, TE, ET | ENT, LES, DES, QUE, EDE, ION, EME | le, la, les, de, des, un, une, et, est, que, qui, dans |

- **The apostrophe is a structural fingerprint.** Elision (`l'homme`, `d'accord`, `qu'il`, `j'ai`, `n'est`, `c'est`) makes the apostrophe one of the most frequent "characters" in French text. If word divisions and punctuation survive in your sample, apostrophe density alone nearly settles the question.
- **-ENT endings:** third-person-plural verbs end in silent `-ent`; combined with `-ment` adverbs, ENT is the dominant trigram.
- Q behaves as in Spanish: essentially always followed by U (`que`, `qui`, `quoi`).
- **Silent final letters** (S, T, X, D) mean French *written* frequencies diverge sharply from *spoken* — a reminder that all tables in this series are written-corpus figures.
- Double letters: SS, LL, EE, TT, NN, MM all occur — noticeably more doubling than Spanish, less than Italian.

## Telling French apart from its neighbors

| vs. | Discriminator |
|---|---|
| Spanish | French: apostrophes everywhere, `ç`, circumflexes; no `ñ`, no `¿¡`. Spanish E+A together >26%; French A only ~7.6%. |
| Italian | Italian: no accents except grave/acute on *final* vowels (`città`, `perché`); French accents sit mid-word. Italian nearly lacks K J W X Y; French uses X often (`aux`, `deux`). |
| Portuguese | Portuguese `ã õ` never occur in French; French `œ ê î` never in Portuguese. Portuguese top letter is A; French is emphatically E. |

## Sources & caveats

Frequencies compiled from published French corpus studies; figures rounded and corpus-dependent (accent-folded per standard cryptanalytic practice). Speaker counts follow OIF/Ethnologue-style estimates, approximate as of 2025–2026.
