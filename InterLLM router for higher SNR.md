We have transformers. To simplify it here, we see them as sequence of att+ffn blocks where every such group is 1 step. 

As we have residual connection, we have more or less stable representation after every sequence step. 

It means, we can sample a token after every step in the sequence. Of course, in the center of sequence it won't have as high probability as in the end of the sequence, but it doesn't matter for us.

The goal here is to find the model's abstractions (vectors related through function of transformer) that it has tied our input to at this step. 

Basically, it's just a list of the associations it has in its mind.

As vocabulary can be match between tokens, we have a "screen" for overlaying our projections now. We can simply compare the token lists.

That is, if we take two llms and do that, we have a very interesting space for experiments. 

We now can intersect the way of thinking of two models. 

We can infuse abstract relationship detected by one model into the second one. 

We can remove the noisy relations if they are only in one model with a weak prob or on the contrary in both. 

Or, we can just strengthen the relations found in both models, thus decreasing tie to the other "noisy" ideas but not removing them.

It's a filter using the resonance power between two models. 

What we do here, is making generation SNR higher, which is what we all need :).

How to add it? We would need to use the target model's embedding for the desired token and to mix it with last token prediction. 

How to mix it? Well, there are several options. But the simplest approach is to use model's own qkv against the token it predicted itself. And we would need to modulate distance (rope) of the infused token to simulate its probability in the source token. We could even have a special qkv or ffn build for this purpose between two specific models - for cross attention fusing and scaling of vectors.

Of course, it's not about speed by any means. But it's an interesting way to create signal resonance between two models, which can be used to reduce the noise. 

In the end after thinking about it, i believe i just suggest a new type of "router", that can work both with sub model parts and with external models. with moe and different models -- to filter our noise and enrich latent space. 

It was a fast idea, so i'm sorry if i wasn't clear in my explanation.
