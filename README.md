# Radical data

The character and word data used by [Radical](https://radical-tawny.vercel.app), a Chinese reading app by Upslope Labs, and the scripts that build it. It is published here because its sources are share-alike: what we derive from them is shared under the same terms.

## What's here

| Path | What it is | License |
|---|---|---|
| `scripts/fetch_data.py` | Downloads Make Me a Hanzi and CC-CEDICT into `raw/` | |
| `scripts/get_data.sh` | Runs everything below and writes `data/` | |
| `scripts/build_data.py` | Make Me a Hanzi to per-character JSON shards (strokes, components labelled meaning / sound / idea) | Arphic Public License (strokes), LGPL 3.0 (dictionary data) |
| `scripts/build_words.py` | CC-CEDICT to per-character word shards (words, pinyin with tone marks, first senses) | CC BY-SA 4.0 |
| `scripts/build_english.py` | CC-CEDICT to an English-to-Chinese index, ordered by `lists/zhfreq.txt` | CC BY-SA 4.0 |
| `lists/zhfreq.txt` | The 40,000 most common Chinese words in wordfreq that are in CC-CEDICT | CC BY-SA 4.0 |
| `lists/topwords.txt` | The 2,000 most common words whose characters have stroke data (`scripts/build_topwords.py`) | CC BY-SA 4.0 |
| `lists/common.tsv` | The 2,000 most common characters, each with a common word (`scripts/build_common.py`) | CC BY-SA 4.0 |
| `lists/prebuild.txt`, `lists/prebuild-tw.txt` | 5,000 common words, Simplified and Traditional (`scripts/build_prebuild_tw.js`) | CC BY-SA 4.0 |
| `licenses/` | Arphic Public License, LGPL 3.0, Make Me a Hanzi's notice | |
| `CREDITS.md` | Every source and what was changed | |

## Build it

```
bash scripts/get_data.sh
```

Needs Python 3 and an internet connection. The built files land in `data/` (about 50 MB, not checked in).

## Sources

- Make Me a Hanzi by Shaunak Kishore: https://github.com/skishore/makemeahanzi (stroke data from Arphic PL KaitiM GB and UKai, Arphic Public License; dictionary data from Unihan and CJKlib, LGPL 3.0)
- CC-CEDICT: https://cc-cedict.org, CC BY-SA 4.0 (https://creativecommons.org/licenses/by-sa/4.0/)
- wordfreq by Robyn Speer: https://github.com/rspeer/wordfreq, CC BY-SA 4.0

The Radical app itself (its code, design and server) is not part of this repository.
