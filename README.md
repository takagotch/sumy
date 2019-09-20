### sumy
---
https://github.com/miso-belica/sumy

```py
// sumy/tests/test_summarizers/test_sum_basic.py
from __future__ import absolute_import, division, print_function, unicode_literals

import pytest

from sumy.models.dom._sentence import Sentence
from sumy.nlp.tokenizers import Tokenizer
from sumy.summarizers.sum_basic import SumBasicSummarizer
from..utils import build_document

EMPTY_STOP_WORDS = []
COMMON_STOP_WORDS = ["the", "and", "i"]

def _build_summarizer(stop_words):
  summarizer = SumBasicSummarizer()
  summarizer.stop_words = stop_words
  return summarizer
  
def test_empty_document():

def test_single_sentence():

def test_normalize_words():

def test_filter_out_stop_words():

def test_compute_word_freq():

def test_get_all_content_words_in_doc():

def test_compute_tf():

def test_compute_average_probability_of_words():
  summarizer = _build_summarizer(EMPTY_STOP_WORDS)
  word_freq = {"one": 1/6, "two": 2/6, "three": 3/6}
  s0 = []
  s1 = ["one"]
  s2 = ["two", "three"]
  s3 = ["two", "three", "three"]
  EPS = 0.0001
  
  assert summarizer._compute_average_probability_of_words(word_freq, s0) == pytest.approx(0, EPS)
  assert summarizer._compute_average_probability_of_words(word_freq, s1) == pytest.approx(1/6, EPS)
  assert summarizer._compute_average_probability_of_words(word_freq, s2) == pytest.approx(5/12, EPS)
  assert summarizer._compute_average_probability_of_words(word_freq, s3) == pytest.approx(8/18, EPS)

def test_compute_ratings():
  summarizer = bild_summarizer(EMPTY_STOP_WORDS)
  
  s0 = Sentence("Dog cat fish.", Tokenizer("english"))
  s1 = Sentence("Dog cat camel.", Tokenizer("english"))
  s2 = Sentence("Fish frog horse.", Tokenizer("english"))
  document = build_document([s0, s1, s2])
  
  ratings = summarizer._compute_ratings(document.sentences)
  assert ratings[s0] == 0
  assert ratings[s1] == -2
  assert ratings[s2] == -1
  
  s0 = Sentence("one two three", Tokenizer("english"))
  s1 = Sentence("one two four", Tokenizer("english"))
  s2 = Sentence("three five six", Tokenizer("english"))
  document = build_document([s0, s1, s2])
  
  ratings = summarizer._compute_ratings(document.sentences)
  assert ratings[s0] == 0
  assert ratings[s1] == -2
  assert ratings[s2] == -1
```

```
```

```
```

