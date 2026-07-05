# Italian — Letters & Frequency Statistics

*Part of the Black Chambers letter-frequency series. See [Identification.md](../Identification.md) for the unknown-sample decision tree and encoding notes.*

## Language profile

| | |
|---|---|
| Script | Latin alphabet, cased, left-to-right |
| Native speakers | ~64 million |
| Total speakers (L1+L2) | ~68 million |
| Share of web content | ~2.7% |
| Official language in | Italy, Switzerland, San Marino, Vatican City |
| Easily confused with | Spanish, Portuguese (vowel-heavy Romance profile) |

## Alphabet

**21 letters.** The standard Italian alphabet *omits* J, K, W, X, Y — they appear only in loanwords and foreign names. This is the smallest alphabet in this series and one of Italian's strongest fingerprints.

| Char | Name | Unicode (upper/lower) | Notes |
|---|---|---|---|
| A a | a | U+0041 / U+0061 | |
| B b | bi | U+0042 / U+0062 | |
| C c | ci | U+0043 / U+0063 | |
| D d | di | U+0044 / U+0064 | |
| E e | e | U+0045 / U+0065 | |
| F f | effe | U+0046 / U+0066 | |
| G g | gi | U+0047 / U+0067 | |
| H h | acca | U+0048 / U+0068 | Silent; mainly in `ho/hai/ha/hanno` and CH/GH clusters |
| I i | i | U+0049 / U+0069 | |
| L l | elle | U+004C / U+006C | |
| M m | emme | U+004D / U+006D | |
| N n | enne | U+004E / U+006E | |
| O o | o | U+004F / U+006F | |
| P p | pi | U+0050 / U+0070 | |
| Q q | cu | U+0051 / U+0071 | Always followed by U |
| R r | erre | U+0052 / U+0072 | |
| S s | esse | U+0053 / U+0073 | |
| T t | ti | U+0054 / U+0074 | |
| U u | u | U+0055 / U+0075 | |
| V v | vu / vi | U+0056 / U+0076 | |
| Z z | zeta | U+005A / U+007A | Notably more common than in Spanish/French |

Foreign guests: J (U+004A), K (U+004B), W (U+0057), X (U+0058), Y (U+0059) — each well under 0.05% in native text.

**Accents:** grave and acute on **final vowels only** — `à è ì ò ù é` (U+00E0, U+00E8, U+00EC, U+00F2, U+00F9, U+00E9), as in `città`, `perché`, `più`. Mid-word accents essentially don't occur — the mirror image of French, where accents live mid-word.

> 💡 *In plain terms: Italian plays with 21 Lego bricks instead of 26, and its only stickers go on the last brick of a word. A frequency table with five dead letters is Italian waving at you.*

## Letter frequency

| # | Letter | % | # | Letter | % |
|---|---|---|---|---|---|
| 1 | E | 11.8 | 12 | U | 3.0 |
| 2 | A | 11.7 | 13 | M | 2.5 |
| 3 | I | 11.3 | 14 | V | 2.1 |
| 4 | O | 9.8 | 15 | G | 1.6 |
| 5 | N | 6.9 | 16 | H | 1.5 |
| 6 | L | 6.5 | 17 | F | 1.0 |
| 7 | R | 6.4 | 18 | B | 0.9 |
| 8 | T | 5.6 | 19 | Q | 0.5 |
| 9 | S | 5.0 | 20 | Z | 0.5 |
| 10 | C | 4.5 | 21 | J K W X Y | ≈0 |
| 11 | D | 3.7 | | | |

**Four vowels above 9.8%** — E, A, I, O are nearly interchangeable at the top, unlike the single-peak profiles of German (E) or Portuguese (A). Vowels total **~48%**, the highest in this series. Nearly every native Italian word ends in a vowel.

## Index of Coincidence

**IC ≈ 0.0738** (26-letter domain; higher if computed over the true 21-letter domain). Random baseline: 0.0385 (26 letters) / 0.0476 (21 letters).

> 💡 *In plain terms: Italian spreads its favoritism across four vowels instead of piling onto one letter, which actually smooths the distribution a bit — its IC is high but a touch below Spanish and French. And remember: fewer marble colors in the bag (21 vs 26) raises the "random" floor, so compare against the right baseline. See [Identification.md](../Identification.md).*

## N-grams and structure

| Top bigrams | Top trigrams | Frequent short words |
|---|---|---|
| ER, ES, ON, RE, EL, EN, DE, DI, TI, SI, AL, AN | CHE, ERE, ZIO, DEL, ECO, QUE, ARI, ATO | di, che, la, il, non, per, una, con, del, si, è |

- **Doubled consonants are everywhere:** `tt ll ss zz nn mm cc pp rr gg` (`tutto`, `bello`, `pizza`, `anno`). Italian doubles consonants more than any other language in this series — in a transposition cipher (where letters keep their identities), heavy doubling screams Italian.
- **CH/GH** exist only to harden C/G before E/I (`chiesa`, `spaghetti`) — H is otherwise nearly confined to four forms of "to have."
- **-ZIONE** endings (≈ English "-tion") make ZIO a top trigram and push Z above its Spanish/French levels.
- Word-final letters are overwhelmingly **vowels** — in ciphertext with word breaks intact, final-position letters concentrate into ~4 symbols.
- **Historical note:** Renaissance Italy is where Western cryptanalysis professionalized — the papal and Venetian cipher secretaries (Alberti's polyalphabetic disk, 1467; the Argenti family) worked against exactly these statistics. This repo's namesake "black chambers" descend from that tradition.

## Telling Italian apart from its neighbors

| vs. | Discriminator |
|---|---|
| Spanish | Spanish uses all 26+Ñ letters, `¿¡`, and rarely doubles consonants. Italian: no Ñ, five dead letters, doubling everywhere. |
| Portuguese | Portuguese `ã õ ç` never occur in Italian; Portuguese top letter is A alone (~14.6%), Italian has a four-vowel plateau. |
| French | French mid-word accents and apostrophe elision vs. Italian final-vowel accents; French uses X freely (`aux`), Italian never. |

## Sources & caveats

Frequencies compiled from published Italian corpus studies; figures rounded and corpus-dependent. Speaker counts follow Ethnologue-style estimates, approximate as of 2025–2026.
