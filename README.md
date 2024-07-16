### 1.1 Transformer from Scratch

I did everything except the kv cache. I learned two interesting ideas:
1. Tying embedding and unembedding weights might not be principled because the direct path cannot model bigram frequencies anymore (it would imply \( P(x|y) = P(y|x) \)).
2. When training a transformer from scratch, the initial loss would be approximately \( \log |V| \) since all tokens are equally likely. The model quickly learns token frequencies and the loss drops to the entropy of token frequencies. Then, it more slowly learns bigrams, trigrams, induction heads, etc.
