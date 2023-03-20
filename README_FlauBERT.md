# cc_net for FlauBERT

If you have difficulties to download the French sub-copora of CCNET, you can follow this quick tutorial.

## Installation

As in the original README:

1. Create or simlink a `data` folder to where you want to download the corpus.

2. Run `make install`. This will download some resources and install required packages.


## Training Language Models

I advise you don't bother training them again but just download the trained ones with:

* `make lang=fr dl_lm` downloads the LM trained for the paper.

## Pipeline overview

You can use 2 of the demo configs to get the data that you want:

* `python -m cc_net --config config/test_segment.json` use this one first to get the metadata of the scrapped pages. 
* `python -m cc_net --config config/test_reproduce.json` use this one to download a JSON file (located at `test_data2/reproduce/`) with the content of web pages, its link, its perplexcity score, etc.

## Checking your obtained files 
You can peak at those files using UNIX tools `zcat` and [`jq`](https://stedolan.github.io/jq/manual/), eg:
`zcat test_data2/reproduce/2019-09/en_head_0000.json.gz | head -1 | jq .`
