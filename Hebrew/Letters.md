# Hebrew — Letters & Frequency Statistics

*Part of the Black Chambers letter-frequency series. See [Identification.md](../Identification.md) for the unknown-sample decision tree and encoding notes. RTL characters below are wrapped in code spans to keep the tables readable left-to-right.*

## Language profile

| | |
|---|---|
| Script | Hebrew **abjad**, caseless, **right-to-left** |
| Native speakers | ~9 million (Modern Hebrew / Ivrit) |
| Total speakers | ~9–10 million, plus liturgical use worldwide |
| Share of web content | ~0.2% |
| Official language in | Israel |
| Also written in this script | Yiddish, Ladino |
| Historical weight | **Atbash** — the reverse-alphabet substitution cipher appearing in the Book of Jeremiah — is one of the oldest attested ciphers, native to this alphabet. Gematria (letter-as-number) predates positional numerals. |

**Abjad** — a writing system that records consonants and leaves most vowels unwritten (reader supplies them from context). Vowel points (*niqqud*) exist but are omitted in ordinary text.

> 💡 *In plain terms: Hbrw wrts lk ths — jst th cnsnnts — nd ntv rdrs fll n th vwls wtht thnkng. You just read that sentence, which proves the system works. Consequence for cryptanalysis: no vowel/consonant split to exploit, and text is ~25% shorter per word than a full alphabet would make it.*

## Alphabet

**22 letters + 5 final forms.** Five letters change shape at the end of a word (*sofit* forms) — same letter, positional variant, separate codepoint.

| Char | Name | Unicode | Final form | Notes |
|---|---|---|---|---|
| `א` | alef | U+05D0 | | Silent consonant / glottal stop |
| `ב` | bet | U+05D1 | | "b/v" |
| `ג` | gimel | U+05D2 | | "g" |
| `ד` | dalet | U+05D3 | | "d" |
| `ה` | he | U+05D4 | | "h"; definite article prefix -`ה` |
| `ו` | vav | U+05D5 | | "v"; doubles as vowel marker o/u; "and" prefix |
| `ז` | zayin | U+05D6 | | "z" |
| `ח` | chet | U+05D7 | | "kh" |
| `ט` | tet | U+05D8 | | "t" |
| `י` | yod | U+05D9 | | "y"; doubles as vowel marker i; smallest letter |
| `כ` | kaf | U+05DB | `ך` U+05DA | "k/kh" |
| `ל` | lamed | U+05DC | | "l"; "to" prefix |
| `מ` | mem | U+05DE | `ם` U+05DD | "m"; "from" prefix |
| `נ` | nun | U+05E0 | `ן` U+05DF | "n" |
| `ס` | samekh | U+05E1 | | "s" |
| `ע` | ayin | U+05E2 | | Guttural, mostly silent in Modern Hebrew |
| `פ` | pe | U+05E4 | `ף` U+05E3 | "p/f" |
| `צ` | tsadi | U+05E6 | `ץ` U+05E5 | "ts" |
| `ק` | qof | U+05E7 | | "k" |
| `ר` | resh | U+05E8 | | "r" |
| `ש` | shin | U+05E9 | | "sh/s" |
| `ת` | tav | U+05EA | | "t" |

**The five finals (`ך ם ן ף ץ`) are word-boundary markers baked into the script** — exactly like Greek's final sigma, but five times over. A substitution cipher that preserves them leaks every word ending; classical Hebrew ciphers fold finals into base forms first. Digital text uses distinct codepoints (mem U+05DE vs. final mem U+05DD), so a codepoint-level frequency count double-books these letters unless you normalize.

**No case.** Hebrew has no capital letters — one less signal, one less leak.

## Letter frequency (Modern Hebrew, finals folded into base letters)

| # | Letter | % | # | Letter | % |
|---|---|---|---|---|---|
| 1 | `י` yod | 11.0 | 12 | `ד` dalet | 3.2 |
| 2 | `ו` vav | 10.4 | 13 | `ק` qof | 2.9 |
| 3 | `ה` he | 8.2 | 14 | `ס` samekh | 2.5 |
| 4 | `ל` lamed | 7.4 | 15 | `פ` pe | 2.5 |
| 5 | `מ` mem | 6.8 | 16 | `ע` ayin | 2.4 |
| 6 | `א` alef | 6.2 | 17 | `ח` chet | 2.4 |
| 7 | `ר` resh | 5.9 | 18 | `צ` tsadi | 1.7 |
| 8 | `ת` tav | 5.7 | 19 | `ג` gimel | 1.6 |
| 9 | `ב` bet | 4.8 | 20 | `ז` zayin | 1.3 |
| 10 | `ש` shin | 4.6 | 21 | `ט` tet | 1.2 |
| 11 | `נ` nun | 4.3 | 22 | `כ` kaf | 3.0 |

(Rank order near the middle varies by corpus more than in European languages — Modern Hebrew corpora range from news to Biblical, which differ substantially.)

**Why yod and vav dominate:** in unpointed text they moonlight as vowel markers (*matres lectionis* — "mothers of reading"), so they absorb much of the vowel workload the script officially ignores. The top of the Hebrew table is, in effect, the vowels sneaking back in.

## Index of Coincidence

**IC ≈ 0.0768** over the 22-letter domain. Random baseline for 22 letters: **0.0455**.

> 💡 *In plain terms: fewer marble colors (22) raises the random floor, and yod/vav favoritism raises the language value — Hebrew's IC looks similar to Spanish's but sits on a different scale. Always compare against the 22-letter baselines. See [Identification.md](../Identification.md).*

## N-grams and structure

- **Prefix particles are fused to the word:** `ה` (the), `ו` (and), `ל` (to), `ב` (in), `מ` (from), `ש` (that) attach directly — `והספר` = "and-the-book" as one string. Word-initial position is therefore dominated by this six-letter club, a strong positional lever.
- Frequent standalone short words: `של` (of), `את` (object marker), `על` (on), `לא` (no/not), `הוא` (he), `זה` (this).
- `את` (et, the direct-object marker) is a high-frequency two-letter crib with no European analogue.
- **Root system:** Hebrew words build on three-consonant roots (K-T-B → wrote/writer/letter/office...). Trigram statistics partially reflect the root inventory rather than spelling habits — pattern attacks on word skeletons are unusually productive.
- **Gematria:** every letter is a numeral (`א`=1 … `י`=10, `כ`=20 … `ק`=100 …). Numbers embedded in classical text are letter strings — dates and quantities hide in plain sight.

## Telling Hebrew apart

| vs. | Discriminator |
|---|---|
| Arabic script | Hebrew letters are **square and disconnected**; Arabic is **cursive and connected**. Instantly distinguishable at a glance despite both being RTL abjads. |
| Yiddish | Same script, but Yiddish spells vowels out with `א ע ו י` combinations and uses digraphs like `וו` and `ײ` heavily; vocabulary is Germanic. Codepoint giveaways: Yiddish ligatures U+05F0–U+05F2. |
| Pointed vs. unpointed | Dots and dashes under/inside letters (niqqud, U+05B0–U+05BC) = children's books, poetry, or scripture; ordinary Modern Hebrew is bare. |

## Sources & caveats

Frequencies compiled from published Modern Hebrew corpus studies (finals folded); figures rounded and notably corpus-dependent given the Biblical/Modern register gap. Speaker counts approximate as of 2025–2026.
