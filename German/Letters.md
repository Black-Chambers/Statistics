# German — Letters & Frequency Statistics

*Part of the Black Chambers letter-frequency series. See [Identification.md](../Identification.md) for the unknown-sample decision tree and encoding notes.*

## Language profile

| | |
|---|---|
| Script | Latin alphabet, cased, left-to-right |
| Native speakers | ~76 million |
| Total speakers (L1+L2) | ~135 million |
| Share of web content | ~5.6% — consistently 2nd or 3rd place |
| Official language in | Germany, Austria, Switzerland, Liechtenstein, Luxembourg, Belgium (region) |
| Easily confused with | Dutch (shared digraphs, similar look without umlauts) |

## Alphabet

**26 base letters + 4:** umlauted vowels `Ä Ö Ü` and the eszett `ß`, for a working total of **30**.

Base letters: `A–Z`, U+0041–U+005A / U+0061–U+007A. The extras:

| Char | Name | Unicode (upper/lower) | Notes |
|---|---|---|---|
| Ä ä | A-Umlaut | U+00C4 / U+00E4 | Transliterates as `AE` when unavailable |
| Ö ö | O-Umlaut | U+00D6 / U+00F6 | Transliterates as `OE` |
| Ü ü | U-Umlaut | U+00DC / U+00FC | Transliterates as `UE` |
| ß | Eszett / scharfes S | U+1E9E / U+00DF | Transliterates as `SS`; capital ẞ (U+1E9E) only standardized in 2017 and still rare — traditionally uppercased as `SS`. Swiss German abolished ß entirely (always `ss`). |

> 💡 *In plain terms: German's four extra letters all have official "spell it without me" fallbacks (ä→ae, ß→ss). Ciphertext and telegrams almost always use the fallbacks — so `AE OE UE` bigrams in an all-caps sample are a German tell, not a typo.*

**Structural fingerprint:** German capitalizes **every noun**, not just proper names. If case survives in your sample, mid-sentence capitals in bulk mean German. It also compounds nouns freely, producing conspicuously long words (`Donaudampfschifffahrtsgesellschaft`).

## Letter frequency (ä ö ü ß folded to ae/oe/ue/ss)

| # | Letter | % | # | Letter | % |
|---|---|---|---|---|---|
| 1 | E | 17.4 | 14 | M | 2.5 |
| 2 | N | 9.8 | 15 | O | 2.5 |
| 3 | I | 7.6 | 16 | B | 1.9 |
| 4 | S | 7.3 | 17 | W | 1.9 |
| 5 | R | 7.0 | 18 | F | 1.7 |
| 6 | A | 6.5 | 19 | K | 1.2 |
| 7 | T | 6.2 | 20 | Z | 1.1 |
| 8 | D | 5.1 | 21 | P | 0.8 |
| 9 | H | 4.8 | 22 | V | 0.7 |
| 10 | U | 4.4 | 23 | J | 0.3 |
| 11 | L | 3.4 | 24 | Y | 0.04 |
| 12 | C | 3.1 | 25 | X | 0.03 |
| 13 | G | 3.0 | 26 | Q | 0.02 |

Unfolded reference: `ü` ≈ 0.65%, `ä` ≈ 0.54%, `ö` ≈ 0.30%, `ß` ≈ 0.31%.

**The headline number: E ≈ 17.4%** — the highest E-dependence of any major European language. Nearly one letter in six. In a monoalphabetic cipher of German, the top ciphertext letter is E with very high confidence, and it towers over #2.

Note also the **vowel poverty**: vowels total only ~38–40% (vs. Spanish/Italian ~47%). German text is consonant-dense — CH, SCH, and ST clusters everywhere.

## Index of Coincidence

**IC ≈ 0.0762.** Random baseline: 0.0385. English: 0.0667.

> 💡 *In plain terms: one letter (E) taking a 17% share makes matched pairs common when you sample two letters from the bag — German's IC runs well above English's for that reason alone. See [Identification.md](../Identification.md).*

## N-grams and structure

| Top bigrams | Top trigrams | Frequent short words |
|---|---|---|
| EN, ER, CH, DE, EI, TE, IN, ND, IE, GE | DER, EIN, SCH, ICH, NDE, DIE, CHE, DEN, END | der, die, das, und, ist, ich, nicht, ein, zu, mit, sich |

- **CH ≈ 2.7% of all bigrams** — C almost never appears *except* in CH/CK/SCH. In a monoalphabetic cipher, a moderately common letter that only ever appears before one specific partner is a C→H giveaway.
- **SCH** as a heavy trigram is nearly unique to German among major languages.
- **EN endings**: infinitives, plurals, and dative forms end in `-en`, making EN the dominant bigram by a wide margin.
- Q, X, Y are effectively absent from native vocabulary — a full-alphabet frequency table with three near-zero letters *and* a 17% spike is a German silhouette even at 100 characters.
- **Enigma footnote:** German military traffic's rigid formatting (`ANX` for "an:", `EINSNULL` for numerals, weather reports at fixed positions) gave Allied cryptanalysts their cribs. The lesson generalizes: stereotyped plaintext structure is as exploitable as letter frequency.

## Telling German apart from its neighbors

| vs. | Discriminator |
|---|---|
| Dutch | Dutch: `ij` pairs and doubled vowels (`aa ee oo uu`), no ß, no umlaut-heavy vocabulary. Dutch E ≈ 18.9% is even *higher* — but Dutch lacks noun capitalization. |
| English | English H ≈ 6% rides on TH; German H rides on CH. English E ≈ 12.7% vs German 17.4%. English never doubles up mid-sentence capitals. |
| French | French vowel total ~45% vs German ~39%; French has no CH/SCH dominance, German has no apostrophe elision. |

## Sources & caveats

Frequencies compiled from published German corpus studies (folded per standard practice); figures rounded and corpus-dependent. Speaker counts follow Ethnologue-style estimates, approximate as of 2025–2026.
