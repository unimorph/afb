# Gulf Arabic (afb)

This repo contains the inflection tables for Gulf Arabic (ISO 639-3 `afb`)

## Contents
- `afb`: entries based on lemmas that appear in the Annotated Gumar Corpus.
- `afb.gloss`: English glosses for the lemmas in `afb`.
- `README.md`: this file.

#

## `afb`

### Generation of the lemma inflections
- The inflections of most of the verb lemmas were generated through the CamelTools morphological generator component
  ([demo](https://calimastar.abudhabi.nyu.edu/generator),
  [API](https://camel-tools.readthedocs.io/en/latest/api/morphology/generator.html))
  ([Obeid et al., 2020](https://www.aclweb.org/anthology/2020.lrec-1.868v2.pdf)).
  The morphological database used is CALIMA-GLF ([Khalifa et al., 2017](https://www.aclweb.org/anthology/W17-1305.pdf)).
- The forms for the all nominal lemmas and some verbs are what appear in the Annotated
  Gumar Corpus ([Khalifa et al.,
  2018](https://www.aclweb.org/anthology/L18-1607.pdf)). Therefore, the
  paradigms for them might not be complete. Additionally, to eliminate noisy
  entries arising from possible gold errors we used Morph/POS statistics from
  the same corpus to
  eliminate incorrect forms as much as possible.
- The POS and morphological features are then mapped to UniMorph according to
  the current [schema](https://unimorph.github.io/doc/unimorph-schema.pdf)
  (Sylak-Glassman 2016).
- The core POS of the lemmas are Verbs, Nouns, and Adjectives.
- The total number of lemmas is 6,707, with the following POS distribution:
    - `V`: 2,183 (32.6%) lemmas
    - `N`: 3,003 (44.8%) lemmas
    - `ADJ`: 1,520 (22.7%) lemmas

### Source
- The Annotated Gumar Corpus
  ([Khalifa et al., 2018](https://www.aclweb.org/anthology/L18-1607.pdf)). The
  corpus can be found [here](https://camel.abudhabi.nyu.edu/annotated-gumar-corpus/).

### Notes on Tokenization and Diacritization
- Clitics were not included or marked in the inflection tables. The only clitic
  included is the determiner `Al+` in order to be consistent with the other
  Arabic varieties in UniMorph.
- All the lemmas are diacritized. However, only the verb forms coming from
  CALIMA-GLF are diacritized. Removing all the diacritics is straightforward and
  can be done through a simple regex. Alternatively, CamelTools provides a
  dediacritization utility: an
  [API](https://camel-tools.readthedocs.io/en/latest/api/utils/dediac.html)
 and a [CLI](https://camel-tools.readthedocs.io/en/latest/cli/camel_dediac.html).

### Notes on POS decisions
  - All nominals with `Al+` will be tagged with `DEF` for definiteness. All
    nominals without `Al+` will be repeated twice: once as `INDF` and once as
    `PSSD`. That is because in most cases possession marking is not
    overt due to the orthography.
  - All verbs are by default in the active voice.

## Annotators
Salam Khalifa and Nizar Habash ([CAMeL Lab](www.camel-lab.com) @ NYU Abu Dhabi)

## Paradigm Samples

The complete inflection table for the noun lemma بَركَن _'park (a vehicle)'_
```
بَركَن	بَركَنتَوا	V;PFV;PL;2
بَركَن	تبَركِن	V;IPFV;FEM;SG;3
بَركَن	بَركَنَوا	V;PFV;PL;3
بَركَن	بَركِنَوا	V;IMP;PL;2
بَركَن	بَركَن	V;PFV;MASC;SG;3
بَركَن	بَركَنت	V;PFV;MASC;SG;2
بَركَن	بَركَنت	V;PFV;SG;1
بَركَن	بَركَنَّا	V;PFV;PL;1
بَركَن	بَركَنَت	V;PFV;FEM;SG;3
بَركَن	تبَركِنُون	V;IPFV;PL;2
بَركَن	اَبَركِن	V;IPFV;SG;1
بَركَن	تبَركِنِين	V;IPFV;FEM;SG;2
بَركَن	يبَركِنُون	V;IPFV;PL;3
بَركَن	بَركَنتِي	V;PFV;FEM;SG;2
بَركَن	بَركِن	V;MASC;IMP;SG;2
بَركَن	يبَركِن	V;IPFV;MASC;SG;3
بَركَن	تبَركِن	V;IPFV;MASC;SG;2
بَركَن	نبَركِن	V;IPFV;PL;1
بَركَن	بَركِنِي	V;FEM;IMP;SG;2
```
The complete inflection table for the noun lemma سِيّارَة _'car'_
```
سِيّارَة	السيارة	N;DEF;FEM;SG
سِيّارَة	سياير	N;INDF;FEM;PL
سِيّارَة	سيار	N;INDF;FEM;SG
سِيّارَة	سيار	N;FEM;SG;PSSD
سِيّارَة	سيارتين	N;INDF;FEM;DU
سِيّارَة	السياير	N;DEF;FEM;PL
سِيّارَة	سياير	N;FEM;PL;PSSD
سِيّارَة	سيارتين	N;FEM;DU;PSSD
سِيّارَة	السيارتين	N;DEF;FEM;DU
```

## License
- [Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)](https://creativecommons.org/licenses/by-sa/3.0/)
