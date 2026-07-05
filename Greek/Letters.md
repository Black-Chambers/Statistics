# Greek — Letters & Frequency Statistics

*Part of the Black Chambers letter-frequency series. See [Identification.md](../Identification.md) for the unknown-sample decision tree and encoding notes.*

## Language profile

| | |
|---|---|
| Script | Greek alphabet, cased, left-to-right |
| Native speakers | ~13.5 million |
| Total speakers | ~13.5 million (few L2 speakers of Modern Greek; enormous scholarly readership of Ancient Greek) |
| Share of web content | ~0.7% |
| Official language in | Greece, Cyprus |
| Historical weight | The ancestor of both Latin and Cyrillic scripts; the oldest alphabet with distinct vowel letters (~800 BCE). The scytale of Sparta and Polybius's checkerboard make Greek arguably the first cipher plaintext in the Western record. |

## Alphabet

**24 letters**, plus one positional rule: sigma has two lowercase forms.

| Char | Name | Unicode (upper/lower) | Sound / notes |
|---|---|---|---|
| Α α | alpha | U+0391 / U+03B1 | "a" — ⚠ uppercase is a Latin-A homoglyph |
| Β β | beta | U+0392 / U+03B2 | Modern: "v" |
| Γ γ | gamma | U+0393 / U+03B3 | "gh/y" |
| Δ δ | delta | U+0394 / U+03B4 | Modern: "th" as in *this* |
| Ε ε | epsilon | U+0395 / U+03B5 | "e" — ⚠ uppercase homoglyph |
| Ζ ζ | zeta | U+0396 / U+03B6 | "z" |
| Η η | eta | U+0397 / U+03B7 | Modern: "ee" — ⚠ uppercase looks like Latin H |
| Θ θ | theta | U+0398 / U+03B8 | "th" as in *thin* |
| Ι ι | iota | U+0399 / U+03B9 | "ee" |
| Κ κ | kappa | U+039A / U+03BA | "k" — ⚠ uppercase homoglyph |
| Λ λ | lambda | U+039B / U+03BB | "l" |
| Μ μ | mu | U+039C / U+03BC | "m" — ⚠ uppercase homoglyph |
| Ν ν | nu | U+039D / U+03BD | "n" — ⚠ uppercase homoglyph; lowercase looks like Latin v |
| Ξ ξ | xi | U+039E / U+03BE | "ks" |
| Ο ο | omicron | U+039F / U+03BF | "o" — ⚠ homoglyph both cases |
| Π π | pi | U+03A0 / U+03C0 | "p" |
| Ρ ρ | rho | U+03A1 / U+03C1 | "r" — ⚠ uppercase looks like Latin P |
| Σ σ / ς | sigma | U+03A3 / U+03C3 / **U+03C2** | "s" — **ς only at word end** (final sigma) |
| Τ τ | tau | U+03A4 / U+03C4 | "t" — ⚠ uppercase homoglyph |
| Υ υ | upsilon | U+03A5 / U+03C5 | Modern: "ee" — ⚠ uppercase looks like Latin Y |
| Φ φ | phi | U+03A6 / U+03C6 | "f" |
| Χ χ | chi | U+03A7 / U+03C7 | "kh" — ⚠ uppercase looks like Latin X |
| Ψ ψ | psi | U+03A8 / U+03C8 | "ps" |
| Ω ω | omega | U+03A9 / U+03C9 | "o" |

**Final sigma (ς, U+03C2)** is a free gift to the cryptanalyst: if a substitution cipher preserved the σ/ς distinction, every ς marks a word boundary. (For the same reason, careful cipher clerks fold ς→σ before encrypting.)

**Diacritics:** Modern Greek (monotonic, official since 1982) uses a single accent, the tonos: `ά έ ή ί ό ύ ώ` (U+03AC, U+03AD, U+03AE, U+03AF, U+03CC, U+03CD, U+03CE) plus dialytika `ϊ ϋ`. Older *polytonic* text carries breathings and multiple accents — text bristling with `ᾶ ἐ ἥ` is pre-1982 or classical.

> 💡 *In plain terms: Greek is the grandparent — Latin and Cyrillic both grew out of it, which is why half its capitals look like ours (and betray nothing) while the lowercase gives it away instantly. If the lowercase looks like math class (α β γ λ π), it's Greek.*

## Letter frequency (Modern Greek, accents folded)

| # | Letter | % | # | Letter | % |
|---|---|---|---|---|---|
| 1 | Α | 11.4 | 13 | Λ | 3.2 |
| 2 | Ο | 9.7 | 14 | Δ | 1.9 |
| 3 | Ι | 8.8 | 15 | Γ | 1.7 |
| 4 | Ε | 8.3 | 16 | Χ | 1.4 |
| 5 | Τ | 8.0 | 17 | Θ | 1.3 |
| 6 | Σ | 7.9 | 18 | Φ | 1.1 |
| 7 | Ν | 6.5 | 19 | Β | 0.9 |
| 8 | Η | 5.1 | 20 | Ω | 0.9 |
| 9 | Υ | 4.3 | 21 | Ξ | 0.5 |
| 10 | Ρ | 4.3 | 22 | Ζ | 0.4 |
| 11 | Κ | 4.0 | 23 | Ψ | 0.2 |
| 12 | Μ | 3.6 | 24 | | |
| | Π | 3.5 | | | |

(Σ includes ς. Corpus-dependent; Modern and Ancient Greek differ noticeably — Ancient corpora run higher on Ε and Ω.)

Vowels (Α Ε Η Ι Ο Υ Ω) total **~48%** — like Italian, a heavily vocalic language, and note that *five different letters* (η ι υ + digraphs ει οι) all spell the "ee" sound in Modern Greek.

## Index of Coincidence

**IC ≈ 0.069** over the 24-letter domain. Random baseline for 24 letters: **0.0417**.

> 💡 *In plain terms: same bag-of-marbles logic as always, but Greek's bag has 24 colors, so its "pure random" floor (0.0417) is higher than the 26-letter floor (0.0385). Compare like with like — see [Identification.md](../Identification.md).*

## N-grams and structure

| Top bigrams | Top trigrams | Frequent short words |
|---|---|---|
| ΑΙ, ΤΑ, ΟΥ, ΤΟ, ΚΑ, ΕΙ, ΝΑ, ΤΗ, ΑΝ, ΣΤ | ΚΑΙ, ΤΟΥ, ΤΗΣ, ΤΩΝ, ΤΗΝ, ΕΝΑ, ΠΟΥ | και, το, η, ο, να, του, της, με, σε, που, δεν, για |

- **ΚΑΙ ("and")** is relentless — the single most useful crib in Greek plaintext.
- The definite article inflects into ~10 short forms (ο, η, το, του, της, τον, την, τα, των, τη), flooding the text with **Τ-initial two/three-letter words** — Τ at word-initial position is far above its overall rate.
- **ΟΥ digram** spells the "oo" sound and behaves like a single letter statistically.
- Word-final letters: overwhelmingly **vowels, Ν, or Σ(ς)** — Greek words essentially never end in other consonants (loanwords aside).

## Telling Greek apart

Greek script = Greek language in modern practice, so identification is really about codepoints, not neighbors:

- ⚠ **Homoglyph checklist:** Α Β Ε Ζ Η Ι Κ Μ Ν Ο Ρ Τ Υ Χ uppercase are visually identical or near-identical to Latin letters but live at U+0391–U+03A9. An "all caps English" sample could be Greek capitals — or a mixed-script trap. Frequency-check it: English caps should show T/E/A dominance; Greek caps show Α/Ο/Ι/Ε/Τ.
- Coptic and mathematical/technical notation borrow Greek letters piecemeal; full running text with spaces and ΚΑΙ everywhere is language, not math.

## Sources & caveats

Frequencies compiled from published Modern Greek corpus studies; figures rounded and corpus-dependent (Ancient Greek differs). Speaker counts follow Ethnologue-style estimates, approximate as of 2025–2026.
