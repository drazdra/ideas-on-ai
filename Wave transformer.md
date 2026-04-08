Wave transformer.

The idea is a bit raw as i just have invented it, but the core is here. 

The main beauty of it is seeing the whole corpus of human texts as a big complex *wave* (with the both text and semantic layers).

For a start, we need to take the text and represent it as a set of frequencies. 

We can record every token as its frequency in the global datasets of training, not just as a random ID. Of course we need to ensure our token values are unique at that.

(We can further develop this idea for domain specific texts, etc, making it multi-dimensional wave (lol, polarization angle), and so on, but here it's just the concept, so we will skip it)

Then we convert every text into a list of positions and frequency amplitude values of the used tokens.

Then we represent any text as a complex wave and convert any input data into sets of decomposed frequencies with Fourier.

And then we feed transformers learning with a set of lists of decomposed waves values, instead of a single monolithic text pattern. 

This way, when we train, we significantly ease the life of transformers by giving it a way to learn to react to the decomposed pattern structure, instead of an actual single very complex pattern. 

Of course we do not get rid of the attention. we just feed attention with a set of decomposed waves, instead of a single flow of text. The benefit is that it also may use way less memory per each wave, then it does trying to process the text right now.

We basically see the whole human text function as a sum of harmonics. 

This actually makes transformer closer to an analog nature of our mind's way to represent the world data, as our brain stores it as gradients, using wave functions for processing.

But that's not the main advantage of the approach, it was actually a start and doesn't even scratch the surface. We could even totally skip doing that :).

The thing is, that the same approach could be applied already to a trained regular transformer's attention as a *second level function* refining the results.

We could think of it as the "error correction" if you wish, but in fact it's a much deeper thing.

If we tokenize the attention and then train it upon attention, it will work not as *text elements distribution* but as *meaning distribution* decomposition. 

We can finally free the space of meanings from the statistical noise of the underlying text representation that plagues modern transformers.

It's a way to create semantically *sound* picture, if you wish ;).

It can be applied to literary harmonize the result and catch anything being in dissonance.

Please, note, it doesn't mean it should sacrifice all of the dissonant notes, as sometimes dissonance is a part of a complex pattern when the wave transitions to a new shape. 

To resolve this we can just add a sliding window for harmonization and introduce the threshhold level for re-decomposition to kick in. That is, we can literally detect the change of the semantics by merely detecting the level of similarity between the existing decompomposed waves to the current window.

Sigh, well.. this is actually a dynamic adaptive system now that can reflect its own state of adequacy and rebase its approach based on it dynamically..

I'm sorry to say, but this is AGI.

To be honest, the whole thing becomes very simple, when you realize that the whole semantic field is a set of harmonics, that we can represent in a wave form.


https://discord.com/channels/1128867683291627614/1464814269479780458/1491459149266030692
i also think that this resolves one of my previous problems i was thinking about
regarding the infereced pattern refining.
