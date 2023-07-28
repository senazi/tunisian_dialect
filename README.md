# Arabizing Tunisian Dialect Using Query Expansion

Introduction:
Query expansion is a critical aspect of information retrieval and plays a significant role in enhancing query understanding. In this project, I focused on developing an efficient query understanding system by inferring the user's intent from their queries, thereby ensuring the retrieval of the matching words.

Methods:
Query expansion uses several processes from Natural Language Processing. In most cases when implementing query understanding systems, a simple or sometimes very complex spell checker is used. In this project; however, my first step in this project is normalization. In normalization process I used simple normalizing function that removes punctionation. Then a simple tokenizer is applied to the input so that tokens will be divided. The token gets concatenated directly to the output string if it's a number or contains only arabic letters otherwise it goes through a function that generates every combination of matching arabic letters (exemple: hk gives 4 possible combinations as 'h' could be reffering to 'ه' or 'ح' and 'k' to 'ك' or 'ق'), the matching letters are ordered from most common to less so the first combination generated should be the highest probable match. Those combinations get stemmed with a stemming algorithm I coded to match tunisian dialect then goes the research of every combination in vocab file (contains tunisian stemmed words scraped from various tunisian facebook groups) returning only existing combinations. If none was found in vocab file, I try to translate the original word with latin letters (using Translator from translate library) from French then english to arabic, if no translation is valid the algorithm returns the first combination (which is the highest probable match).


![concept](https://github.com/senazi/tunisian_dialect/assets/97397053/6e318bc8-8bdb-47ba-8369-c11ae2df4a35)
