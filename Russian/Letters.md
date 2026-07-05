# Russian — Letters & Frequency Statistics

*Part of the Black Chambers letter-frequency series. See [Identification.md](../Identification.md) for the unknown-sample decision tree and encoding notes.*

## Language profile

| | |
|---|---|
| Script | **Cyrillic** alphabet, cased, left-to-right |
| Native speakers | ~145 million |
| Total speakers (L1+L2) | ~255 million |
| Share of web content | ~4–5% — consistently top 5 |
| Official language in | Russia, Belarus, Kazakhstan, Kyrgyzstan; widely used across the former USSR |
| Easily confused with | Ukrainian, Bulgarian, Serbian (shared Cyrillic — see discriminators below) |

## Alphabet

**33 letters.** Cyrillic, developed from Greek in the 9th–10th centuries; the modern Russian set was fixed by the 1918 reform.

| Char | Name | Unicode (upper/lower) | Sound / notes |
|---|---|---|---|
| А а | a | U+0410 / U+0430 | "a" — ⚠ homoglyph of Latin A |
| Б б | be | U+0411 / U+0431 | "b" |
| В в | ve | U+0412 / U+0432 | "v" — ⚠ looks like Latin B, sounds like V |
| Г г | ge | U+0413 / U+0433 | "g" |
| Д д | de | U+0414 / U+0434 | "d" |
| Е е | ye | U+0415 / U+0435 | "ye" — ⚠ homoglyph of Latin E |
| Ё ё | yo | U+0401 / U+0451 | "yo" — routinely written as Е in print |
| Ж ж | zhe | U+0416 / U+0436 | "zh" (like *measure*) |
| З з | ze | U+0417 / U+0437 | "z" — ⚠ resembles digit 3 |
| И и | i | U+0418 / U+0438 | "ee" — ⚠ mirrored Latin N |
| Й й | i kratkoye | U+0419 / U+0439 | "y" glide |
| К к | ka | U+041A / U+043A | "k" — ⚠ homoglyph of Latin K |
| Л л | el | U+041B / U+043B | "l" |
| М м | em | U+041C / U+043C | "m" — ⚠ homoglyph of Latin M |
| Н н | en | U+041D / U+043D | "n" — ⚠ looks like Latin H, sounds like N |
| О о | o | U+041E / U+043E | "o" — ⚠ homoglyph of Latin O |
| П п | pe | U+041F / U+043F | "p" (Greek Π) |
| Р р | er | U+0420 / U+0440 | "r" — ⚠ looks like Latin P, sounds like R |
| С с | es | U+0421 / U+0441 | "s" — ⚠ looks like Latin C, sounds like S |
| Т т | te | U+0422 / U+0442 | "t" — ⚠ homoglyph of Latin T |
| У у | u | U+0423 / U+0443 | "oo" — ⚠ resembles Latin Y |
| Ф ф | ef | U+0424 / U+0444 | "f" (Greek Φ) |
| Х х | kha | U+0425 / U+0445 | "kh" — ⚠ looks like Latin X |
| Ц ц | tse | U+0426 / U+0446 | "ts" |
| Ч ч | che | U+0427 / U+0447 | "ch" — resembles digit 4 |
| Ш ш | sha | U+0428 / U+0448 | "sh" |
| Щ щ | shcha | U+0429 / U+0449 | "shch" |
| Ъ ъ | hard sign | U+042A / U+044A | No sound — separator; rarest letter |
| Ы ы | y | U+042B / U+044B | Deep "i" — **never word-initial** |
| Ь ь | soft sign | U+042C / U+044C | No sound — palatalizes the previous consonant |
| Э э | e | U+042D / U+044D | Plain "e" |
| Ю ю | yu | U+042E / U+044E | "yu" |
| Я я | ya | U+042F / U+044F | "ya" — ⚠ mirrored Latin R |

> 💡 *In plain terms: about a third of Cyrillic letters are visual traps — they look exactly like Latin letters but mean something else (Р=R, Н=N, С=S, В=V) or are entirely different codepoints that render identically (А, Е, О, К, М, Т). Never eyeball a digital sample; check the codepoints. Phishers exploit exactly this.*

## Letter frequency

| # | Letter | % | # | Letter | % |
|---|---|---|---|---|---|
| 1 | О | 11.0 | 18 | Ь | 1.7 |
| 2 | Е | 8.5 | 19 | Г | 1.7 |
| 3 | А | 8.0 | 20 | З | 1.6 |
| 4 | И | 7.4 | 21 | Б | 1.6 |
| 5 | Н | 6.7 | 22 | Ч | 1.4 |
| 6 | Т | 6.3 | 23 | Й | 1.2 |
| 7 | С | 5.5 | 24 | Х | 1.0 |
| 8 | Р | 4.7 | 25 | Ж | 0.9 |
| 9 | В | 4.5 | 26 | Ш | 0.7 |
| 10 | Л | 4.4 | 27 | Ю | 0.6 |
| 11 | К | 3.5 | 28 | Ц | 0.5 |
| 12 | М | 3.2 | 29 | Щ | 0.4 |
| 13 | Д | 3.0 | 30 | Э | 0.3 |
| 14 | П | 2.8 | 31 | Ф | 0.3 |
| 15 | У | 2.6 | 32 | Ъ | 0.04 |
| 16 | Я | 2.0 | 33 | Ё | 0.04* |
| 17 | Ы | 1.9 | | | |

\* Ё is nearly always printed as Е, which inflates Е's count; corpora that restore Ё put it near 1%.

**Ф (F) at 0.3%** is a curiosity with cryptanalytic value: F-sound words in Russian are almost all borrowings, so technical/foreign-heavy traffic shows elevated Ф — a crude genre detector.

## Index of Coincidence

**IC ≈ 0.0529** over the 32/33-letter Cyrillic domain. Random baseline for 33 letters: **0.0303** (not 0.0385!).

> 💡 *In plain terms: Russian's IC looks "low" only if you wrongly compare it to English's 0.0667. With 33 marble colors in the bag instead of 26, even a heavily lopsided language produces fewer matched pairs. Against its own random floor (0.0303), Russian is just as lumpy as English is against 0.0385. Judge each alphabet on its own scale — see [Identification.md](../Identification.md).*

This is the single most common mistake when running IC tests on Cyrillic ciphertext: concluding "polyalphabetic" from a number that is actually normal monoalphabetic Russian.

## N-grams and structure

| Top bigrams | Top trigrams | Frequent short words |
|---|---|---|
| СТ, НО, ЕН, ТО, НА, ОВ, НИ, РА, ВО, КО | СТО, ЕНО, НОВ, ТОВ, ОВО, ОГО, ЕНИ | и, в, не, на, я, что, он, с, это, как, но, по |

- **-ОГО / -ЕГО endings** (genitive adjectives, pronounced -ovo/-evo) are extremely frequent — ОГО is a signature trigram.
- **Positional rules are exploitable:** Ы, Ь, Ъ never begin a word; Й rarely does. In ciphertext with word divisions, symbols that never open a word map to this trio.
- Single-letter words are common: `и` (and), `в` (in), `с` (with), `я` (I), `а`, `о`, `у`, `к` — richer single-letter pickings than English's a/I.
- **Ь after consonants:** the soft sign only ever follows consonants — a strong adjacency constraint for pattern-matching attacks.

## Telling Russian apart from other Cyrillic languages

| vs. | Discriminator |
|---|---|
| Ukrainian | Ukrainian uses `і ї є ґ` (U+0456, U+0457, U+0454, U+0491) — none exist in Russian. Russian `ы ё э` don't exist in Ukrainian. One line of text usually settles it. |
| Bulgarian | Bulgarian lacks `ы ё э`; uses `ъ` *constantly* as a vowel (Russian's rarest letter is Bulgarian's workhorse — `България`). High Ъ frequency = Bulgarian, near-zero = Russian. |
| Serbian | Serbian Cyrillic has `ј љ њ ћ ђ џ` (U+0458 etc.) and no `й ю я ё ы ь ъ э щ`. |

## Sources & caveats

Frequencies compiled from published Russian corpus studies (literary and news corpora); figures rounded and corpus-dependent. Speaker counts follow Ethnologue-style estimates, approximate as of 2025–2026.
