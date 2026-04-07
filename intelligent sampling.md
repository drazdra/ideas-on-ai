I was thinking here about sampling, and here my suggestion :).

Intro

Samplers are the "non-ai" part of the ai, that uses pure chance and math to finish the inference, sampling literally adds rendomness to the results of any llm, making results more creative and less prone to loops, but less predictable.
However, a lot of hallucinations in models come from the samplers.

Example

Let's say we look for some quotation in text. Model starts reproducing a similar pattern. However, every produced token is still sampled from the list probable ones. 

Say, we have a token "Said" in the quote, in the probs list we also token "Asked", because it's a quite related token to the "talking". And.. due to sampler we may just randomly choose "Asked" instead of "Said". Suddenly,, the quotation it was printing starts resembling more to a different phrase, than it is to the original it was printing. And the whole inference path goes the other way.

Solution

What we need to do, is to add special tokens to llm, that would give it a way to control the samplers' behavior.
For example: a token that disables the sampler (so we take the top option) and another one that enables it back. (it's the simplest option for the example, of course we could teach it more tricks).
Then, LLM could actually *learn* to change the sampling mode and could produce much more predictable results, keeping its creativity when it's not critical. 

It's an elegant way to create *intelligent* sampling, because we literary create correlation between the processed pattern and the sampler method being used.

Of course, the training would need to be amended to support this, but it's a very minor fix.

It makes sampling be intelligent sampling, which is a keystone that current transformers lack.
