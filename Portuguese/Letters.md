# Portuguese — Letters & Frequency Statistics

*Part of the Black Chambers letter-frequency series. See [Identification.md](../Identification.md) for the unknown-sample decision tree and encoding notes.*

## Language profile

| | |
|---|---|
| Script | Latin alphabet, cased, left-to-right |
| Native speakers | ~235 million — more than French and German combined |
| Total speakers (L1+L2) | ~265 million |
| Share of web content | ~3.8% |
| Official language in | Portugal, Brazil (the overwhelming majority of speakers), Angola, Mozambique, and 5 others (CPLP) |
| Easily confused with | Spanish (mutual near-intelligibility on paper), Galician |

## Alphabet

**26 letters** — K, W, Y were formally (re)admitted by the 1990 Orthographic Agreement but remain confined to loanwords, symbols, and foreign names.

Base letters: `A–Z`, U+0041–U+005A / U+0061–U+007A. The diacritic layer is the fingerprint:

| Char | Name | Unicode (upper/lower) | Notes |
|---|---|---|---|
| Ã ã | a til | U+00C3 / U+00E3 | **Nasal A** — `não`, `são`, `manhã`. Diagnostic: no other major European language puts a tilde on a vowel |
| Õ õ | o til | U+00D5 / U+00F5 | Nasal O — `ções`, `põe` |
| Ç ç | c-cedilha | U+00C7 / U+00E7 | Soft C before A/O/U — shared with French |
| Á á | | U+00C1 / U+00E1 | Acute = stressed open vowel |
| É é | | U+00C9 / U+00E9 | |
| Í í | | U+00CD / U+00ED | |
| Ó ó | | U+00D3 / U+00F3 | |
| Ú ú | | U+00DA / U+00FA | |
| Â â | | U+00C2 / U+00E2 | Circumflex = stressed closed vowel |
| Ê ê | | U+00CA / U+00EA | |
| Ô ô | | U+00D4 / U+00F4 | |
| À à | | U+00C0 / U+00E0 | Crasis (`à` = a+a) only |

> 💡 *In plain terms: Spanish puts the tilde on the N (ñ); Portuguese puts it on vowels (ã, õ). One character class settles a Spanish-vs-Portuguese question instantly.*

Digraphs `nh`, `lh`, `ch`, `ss`, `rr` are frequent (Portuguese `nh`/`lh` ≈ Spanish `ñ`/`ll`).

## Letter frequency (diacritics folded)

| # | Letter | % | # | Letter | % |
|---|---|---|---|---|---|
| 1 | **A** | 14.6 | 14 | P | 2.5 |
| 2 | E | 12.6 | 15 | V | 1.7 |
| 3 | O | 10.7 | 16 | G | 1.3 |
| 4 | S | 7.8 | 17 | H | 1.3 |
| 5 | R | 6.5 | 18 | Q | 1.2 |
| 6 | I | 6.2 | 19 | B | 1.0 |
| 7 | N | 5.0 | 20 | F | 1.0 |
| 8 | D | 5.0 | 21 | Z | 0.5 |
| 9 | M | 4.7 | 22 | J | 0.4 |
| 10 | U | 4.6 | 23 | X | 0.2 |
| 11 | T | 4.3 | 24 | K | <0.1 |
| 12 | C | 3.9 | 25 | W | <0.1 |
| 13 | L | 2.8 | 26 | Y | <0.1 |

**The headline: A is #1, not E** — the only major Romance language where this holds, and at ~14.6% it isn't close. A three-vowel summit (A, E, O totaling ~38%) with A on top is the Portuguese silhouette.

Q runs unusually high (~1.2%, vs 0.5–0.9% elsewhere) thanks to `que`, `qual`, `quando`; as in its siblings, Q is always followed by U.

## Index of Coincidence

**IC ≈ 0.0745.** Random baseline: 0.0385. English: 0.0667.

> 💡 *In plain terms: Portuguese piles onto A the way German piles onto E — heavy favoritism means frequent matched pairs when you draw two letters from the bag. See [Identification.md](../Identification.md).*

## N-grams and structure

| Top bigrams | Top trigrams | Frequent short words |
|---|---|---|
| DE, OS, RA, ES, AS, DO, AR, EN, QU, CO | QUE, ENT, COM, NTE, ADO, ÇÃO/CAO, EST, PAR | de, a, o, que, e, do, da, em, um, para, com, não, uma, os |

- **-ÇÃO / -ÇÕES endings** (≈ English "-tion/-tions"): `informação`, `nações`. Folded, these become CAO/COES — an odd-looking, highly diagnostic word-final trigram.
- **M as a word-ender:** Portuguese words routinely end in `-m` (`sim`, `bem`, `falam`, `um`) where Spanish uses `-n`. Word-final M in a European-language sample is a strong Portuguese vote.
- **NH / LH** digraphs (`senhor`, `filho`) parallel Spanish Ñ/LL — in a monoalphabetic cipher, a letter that pairs unusually often with the H-symbol suggests the Iberian digraph pattern.
- Double letters: only SS and RR are common (`nosso`, `carro`) — closer to Spanish's austerity than Italian's exuberance.
- European vs. Brazilian orthography differ slightly (the 1990 Agreement narrowed but didn't erase the gap); frequency impact is negligible at cipher-solving precision.

## Telling Portuguese apart from its neighbors

| vs. | Discriminator |
|---|---|
| Spanish | Portuguese: `ã õ ç`, word-final M, A as top letter, `nh/lh`. Spanish: `ñ`, `¿¡`, word-final N, E as top letter. |
| Italian | Italian's five dead letters (JKWXY) vs Portuguese's three near-dead (KWY); Italian doubles consonants constantly, Portuguese barely; Italian words end in vowels, Portuguese happily ends in M/S/R/L. |
| French | French `œ ê î` mid-word accents and apostrophes vs Portuguese tildes; French A ~7.6% vs Portuguese A ~14.6% — one glance at the A row settles it. |
| Galician | Genuinely hard on paper (shared ancestry); Galician uses `ñ` and `x` heavily (`Xunta`) where Portuguese uses `nh` and `j/g`. |

## Sources & caveats

Frequencies compiled from published Portuguese corpus studies (Brazilian and European corpora broadly agree at this precision); figures rounded and corpus-dependent. Speaker counts follow Ethnologue-style estimates, approximate as of 2025–2026.
