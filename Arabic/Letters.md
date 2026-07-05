# Arabic — Letters & Frequency Statistics

*Part of the Black Chambers letter-frequency series. See [Identification.md](../Identification.md) for the unknown-sample decision tree and encoding notes. RTL characters below are wrapped in code spans to keep the tables readable left-to-right.*

## Language profile

| | |
|---|---|
| Script | Arabic **abjad**, caseless, **right-to-left**, cursive (letters connect) |
| Native speakers | ~380 million (all varieties) |
| Total speakers | ~420 million; liturgical reach across ~2 billion Muslims |
| Share of web content | ~0.6% (badly undercounted — Arabic traffic concentrates in apps and platforms web surveys can't crawl) |
| Official language in | 25+ countries (Arab League); UN official language |
| Also written in this script | Persian/Farsi, Urdu, Pashto, Kurdish (Sorani) — with extra letters |
| Historical weight | **Frequency analysis was invented for this alphabet.** Al-Kindī's 9th-century Baghdad manuscript *On Deciphering Cryptographic Messages* is the earliest known description of solving ciphers by letter counts — the founding document of the field this repo covers. |

**Abjad** — consonants written, short vowels omitted (long vowels get letters). Diacritical vowel marks (*ḥarakāt*) exist but appear only in the Qur'an, poetry, and teaching texts.

> 💡 *In plain terms: like Hebrew, Arabic writes the consonant skeleton and trusts the reader to fill in vowels. And unlike print English, it's always "cursive" — letters hold hands, and they change shape depending on which hands they're holding.*

## Alphabet

**28 letters.** Each has up to **four contextual forms** — isolated, initial, medial, final — because letters connect cursively. These are *renderings*, not separate letters: Unicode stores one codepoint per letter and the font picks the shape. (Legacy "presentation forms" at U+FB50–U+FEFF encode the shapes explicitly; treat text containing them as needing normalization.)

Six letters (`ا د ذ ر ز و`) never connect to the following letter, creating gaps inside words — so visual spacing is *not* a reliable word-boundary signal.

| Char | Name | Unicode | Sound / notes |
|---|---|---|---|
| `ا` | alif | U+0627 | Long "a"; carrier for initial vowels |
| `ب` | bāʾ | U+0628 | "b" — one dot below |
| `ت` | tāʾ | U+062A | "t" — two dots above |
| `ث` | thāʾ | U+062B | "th" (*thin*) — three dots above |
| `ج` | jīm | U+062C | "j" |
| `ح` | ḥāʾ | U+062D | Emphatic "h" |
| `خ` | khāʾ | U+062E | "kh" |
| `د` | dāl | U+062F | "d" |
| `ذ` | dhāl | U+0630 | "th" (*this*) |
| `ر` | rāʾ | U+0631 | "r" |
| `ز` | zāy | U+0632 | "z" |
| `س` | sīn | U+0633 | "s" |
| `ش` | shīn | U+0634 | "sh" |
| `ص` | ṣād | U+0635 | Emphatic "s" |
| `ض` | ḍād | U+0636 | Emphatic "d" — so distinctive Arabic calls itself "the language of ḍād" |
| `ط` | ṭāʾ | U+0637 | Emphatic "t" |
| `ظ` | ẓāʾ | U+0638 | Emphatic "th/z" — rarest letter |
| `ع` | ʿayn | U+0639 | Voiced pharyngeal — no European equivalent |
| `غ` | ghayn | U+063A | "gh" |
| `ف` | fāʾ | U+0641 | "f" |
| `ق` | qāf | U+0642 | Deep "k" |
| `ك` | kāf | U+0643 | "k" |
| `ل` | lām | U+0644 | "l" |
| `م` | mīm | U+0645 | "m" |
| `ن` | nūn | U+0646 | "n" |
| `ه` | hāʾ | U+0647 | "h" |
| `و` | wāw | U+0648 | "w"; long "u"; "and" prefix |
| `ي` | yāʾ | U+064A | "y"; long "i" |

Common extras: `ة` tāʾ marbūṭa (U+0629, feminine ending), `ء` hamza (U+0621) and its seated forms `أ إ آ ئ ؤ` (U+0623, U+0625, U+0622, U+0626, U+0624), `ى` alif maqṣūra (U+0649). Persian adds `پ چ ژ گ`; Urdu adds more — their presence means the sample is *not* Arabic.

**Dots are load-bearing:** `ب ت ث ن ي` share one base skeleton and differ only by dot count/position. Historically, undotted (*rasm*) text was ambiguous by design — an early information-hiding layer.

## Letter frequency (Modern Standard Arabic)

| # | Letter | % | # | Letter | % |
|---|---|---|---|---|---|
| 1 | `ا` alif | 12.9 | 15 | `ق` qāf | 2.2 |
| 2 | `ل` lām | 12.2 | 16 | `س` sīn | 2.1 |
| 3 | `ي` yāʾ | 7.3 | 17 | `ك` kāf | 2.0 |
| 4 | `م` mīm | 6.6 | 18 | `ح` ḥāʾ | 1.9 |
| 5 | `و` wāw | 6.1 | 19 | `ج` jīm | 1.4 |
| 6 | `ن` nūn | 6.0 | 20 | `ص` ṣād | 1.2 |
| 7 | `ر` rāʾ | 5.0 | 21 | `خ` khāʾ | 1.0 |
| 8 | `ت` tāʾ | 4.6 | 22 | `ش` shīn | 1.0 |
| 9 | `ب` bāʾ | 4.3 | 23 | `ض` ḍād | 0.9 |
| 10 | `ة/ه` hāʾ+tāʾ marbūṭa | 4.1 | 24 | `ذ` dhāl | 0.7 |
| 11 | `ع` ʿayn | 3.7 | 25 | `ز` zāy | 0.6 |
| 12 | `ف` fāʾ | 3.0 | 26 | `ث` thāʾ | 0.6 |
| 13 | `د` dāl | 2.9 | 27 | `غ` ghayn | 0.5 |
| 14 | `أ/إ/آ` hamza-alifs | (in alif) | 28 | `ط` ṭāʾ / `ظ` ẓāʾ | 0.5 / 0.1 |

(Hamza-carrier and tāʾ-marbūṭa folding conventions vary between corpora — normalize before comparing counts.)

**Why alif + lām own a quarter of the text:** the definite article **`ال` (al-)** prefixes directly onto nouns and adjectives — *al-kitāb*, *al-jabr* (→ "algebra"). The AL bigram is to Arabic what THE is to English, but fused into the word and even more frequent. Al-Kindī's method leaned on exactly this.

## Index of Coincidence

**IC ≈ 0.0759** over the 28-letter domain. Random baseline for 28 letters: **0.0357**.

> 💡 *In plain terms: alif and lām hog a quarter of all draws from the bag, so matched pairs come up constantly — Arabic is one of the "lumpiest" major languages, which is precisely why frequency analysis was discovered here first. Compare against the 28-letter random floor, not the Latin one. See [Identification.md](../Identification.md).*

## N-grams and structure

- **`ال` (al-)** dominates word-initial position; in ciphertext with word breaks, the most common two-symbol word-opening pattern is al- with high confidence.
- Fused particles: `و` (and), `ب` (in/with), `ل` (to), `ف` (so) attach to the front of words — like Hebrew, word-initial statistics are particle-driven.
- Frequent standalone words: `في` (in), `من` (from), `على` (on), `أن` (that), `إلى` (to), `هذا` (this), `لا` (no/not).
- **Triliteral roots:** most vocabulary derives from three-consonant roots (K-T-B → book, writer, office, library). As with Hebrew, skeleton-pattern attacks are productive.
- `ة` tāʾ marbūṭa appears **only word-finally** — a built-in word-boundary leak, same class as Greek ς and the Hebrew finals.
- **MSA vs. dialects:** these figures describe Modern Standard Arabic (news, books, formal writing). Dialectal chat (Egyptian, Levantine, Gulf) shifts frequencies and vocabulary; "Arabizi" — Arabic typed in Latin letters with digits standing in for missing sounds (3 = `ع`, 7 = `ح`, 2 = `ء`) — is common in informal digital traffic and needs its own tables entirely.

## Telling Arabic-script languages apart

| vs. | Discriminator |
|---|---|
| Persian/Farsi | Presence of `پ چ ژ گ` (U+067E, U+0686, U+0698, U+06AF); Persian yāʾ `ی` (U+06CC) instead of `ي`; frequent word `است`. |
| Urdu | Persian extras plus `ٹ ڈ ڑ ے ھ`; typically set in hanging Nastaʿlīq style vs. Arabic's flat Naskh. |
| Hebrew | Square, disconnected letters vs. Arabic's connected cursive — a glance suffices. |

## Sources & caveats

Frequencies compiled from published MSA corpus studies (news corpora); figures rounded, corpus-dependent, and sensitive to hamza/tāʾ-marbūṭa normalization choices. Speaker counts follow Ethnologue-style estimates, approximate as of 2025–2026.
