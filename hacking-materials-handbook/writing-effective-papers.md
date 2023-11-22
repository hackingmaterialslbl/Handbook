# H: Writing effective papers

Here are some miscellaneous tips for writing papers. There also some good tips in the short article below (which echo many of the things I write below, such as the importance of a discussion section and how it is better to be short than long):&#x20;

_https://serialmentor.com/blog/2013/8/29/writing-a-scientific-pap er-in-four-easy-steps_

### Writing style&#x20;

#### Active vs. passive voice&#x20;

This is one of the unending arguments about writing style for scientific papers (active: “We conducted a DFT study...” vs. passive: “A DFT study was conducted ...”). In general, I prefer the active voice about 80% of the time, with the exception of the Methods section for which I typically use passive voice. This is in-line with most modern recommendations from multiple sources, although one can certainly find disagreements. Note that journals like Nature state that they always prefer the active voice.

#### Science is quantitative - give numbers&#x20;

Always provide numbers, not just text. \
_Bad:_ “The computations and experiments agree very well.” \
_Good:_ “The computations and experiments agree very well, with an r2 of 0.89 and a mean absolute error of 0.2 eV (Table 3).”\
\
_Bad:_ “The Seebeck coefficient for layered chalcogenides was previously found to be very high,\[3-5] making these systems interesting for thermoelectric applications.” \
_Good:_ “The Seebeck coefficient for layered chalcogenides was previously found to be very high (in the range of 300-400 microvolts/K),\[3-5] making these systems interesting for thermoelectric applications.” \
\
In particular, the abstract of the manuscript should contain all Very Important Numbers (number of materials investigated, major result numbers, number of good compositions found, etc.) as well as important compounds, techniques, etc.

#### Use specific verbs&#x20;

One of the ways to tighten and polish a manuscript is to use more specific verbs.&#x20;

For example, instead of “We study”, try one of the following:

* apply, assess, calculate, compare, compute, derive, design, determine, develop, evaluate, explore, implement, investigate, measure, model&#x20;

Instead of “Figure 1 shows”, try one of the following:&#x20;

* plots, illustrates, presents, exhibits, demonstrates, indicates, reveals, depicts&#x20;

Typically, such refinements would come at a later stage of the manuscript and is not something to worry about in the first draft - although if you write often enough, you’ll gain the ability to use more specific verbs in earlier drafts.

### Methods section&#x20;

#### DFT based&#x20;

If you are writing a DFT-based methods section, be sure to include:&#x20;

* DFT code used and version (e.g., VASP v5.2.x)
* version of software(s) used to do other things (e.g., atomate v0.9.1)
* pseudopotential type (preferably with more details if multiple variants with different # of core electrons exist)
* functional(s)
* major functional parameters (including +U values or HSE mixing parameters)
* k-point mesh (or algorithm used to determine this)
* electronic and ionic cutoff energies (or algorithm used to determine this)

It’s better if you can list all this explicitly in the text (either main or supplement) rather than refer to some other paper that has details. Not everyone has access to all our papers, plus it is just a pain for someone to track down information across many papers.

#### Machine learning based&#x20;

For machine learning papers, be sure to include:&#x20;

* size and details of full data set
* data cleaning, filtering, normalization, etc.
* strategy to do train-test split or train-validation-test split, CV, nested CV, etc.
* features/descriptors tested
* any feature normalization, feature processing, or feature selection strategy employed
* algorithm(s) chosen (e.g. random forest)
* hyperparameter selection strategy, and values of optimal hyperparameters if possible to summarize
* ideally, a link to a code repo where someone can run the same trained model on their own data set

### Discussion section&#x20;

> _“Meaning is the relationship of the foreground figure to the background”_
>
> **-- Bruce Lee**

I’ve found that many researchers, even senior ones, either skip a Discussion section or do a poor job of writing one. Note that it is certainly possible and sometimes advantageous to folding the discussion into the results, but in the majority of cases I’ve found that this strategy is advocated by those who don’t write good discussion sections. Thus, I suggest first writing a separate Discussion section to ensure that the discussion is strong on its own, then folding components into the Results section later as needed.&#x20;

Some of the things to do in the discussion section:

* Put your work in the context of past results in a way that is deeper than the introduction (i.e., now that you have presented your results, you can really show how those fit in or don’t fit in with prior results). Do your results match, modify, or disagree with prior results?&#x20;
* Explain any limitations of your work as well as whether those limitations could potentially change any conclusions or limit the range of applicability of your work.&#x20;
* Show and explain which of your results can be explained by existing theory / chemical principles / paradigms.&#x20;
* Highlight which of your results can NOT be explained by existing knowledge in the field. Provide your own thoughts on any outlier points / unexplainable results. These do not have to be correct, just plausible. If such thoughts are testable by further computations, you should test them and show the results (even negative results can be shown to rule out possibilities). As stated by Richard Feynman: “The exceptions to any rule are most interesting in themselves, for they show us that the old rule is wrong. And it is most exciting then, to find out what the right rule, if any, is.”&#x20;
* Offer any new design rules you can come up with and discuss any important tradeoffs that might need to be made.&#x20;
*   If you offer any computationally testable hypotheses, then test them, don’t just theorize. For example, let’s say you are trying to explain why compound A has a larger band gap than compound B. You hypothesize that it’s because compound A has a smaller cell volume than compound B. Many people will just leave it as that. But what you should do is to actually compute both compound A and compound B at the same cell volume (either at that of A, that of B, an intermediate volume, or all 3) and show that the discrepancy between band gaps goes away. Then you can chalk up the discrepancy to volume confidently instead of

    just theorizing.

You can see an example of a discussion in one of my earlier papers: _“Relating voltage and thermal safety in Li-ion battery cathodes: a high-throughput computational study”._

### Conclusion section&#x20;

Many researchers copy-paste and re-word the abstract for the conclusion (or vice-versa). However, this section can include more. While you should certainly summarize the paper’s main results, don’t be afraid to also use this section to speculate about the future. This includes:&#x20;

* how your results might be applied to various materials classes or analyses&#x20;
* suggestions for future study, either to be conducted by yourself or by other researchers&#x20;
* what kinds of further advancements would be most useful or needed

### Acknowledgements section

&#x20;It may not seem like it, but the acknowledgements section is one of the most important parts of the paper when it comes to research funding. In fact, funding agencies usually ask us to write out the _full acknowledgements section_ for every paper we published with that funding. This text decides the degree to which we get “credit” for the publication in the eyes of the funding agency.

For the acknowledgements section:&#x20;

* Thank anyone for help with the project that is not already an author on the paper - e.g., if someone helped introduce you to a topic or method, or contributed in some small way
* Thank any software library that you did not already cite / mention in the main paper
* Ask and confirm with Anubhav the text that should be used to acknowledge the funding agency. If this is primarily our work, we should have some text that says the project was “intellectually led by” or “primarily funded by” our funding source. There is a big difference in the way we report papers funded with those words in the acknowledgements versus missing those words.
* If you used any supercomputing resource, find the guidelines for acknowledgement and make sure to follow them. This text is often needed in order for the paper to qualify for computing time renewal grants. For example, the text for NERSC is listed here:[ _https://bit.ly/2Q5eAVV_](https://bit.ly/2Q5eAVV)
* Some guidelines on funding acknowledgements from LBNL’s MSD, which is also applicable to us for the most part, can be found here: [_https://bit.ly/2CMhhHU_](https://bit.ly/2CMhhHU)

### Paper checklist&#x20;

Here is a checklist you can use prior to having a “final” version of your paper.&#x20;

#### _Pre-”final” checks:_&#x20;

* **All the numbers in the manuscript are correct.** Most researchers double-check their text and wording multiple times before paper submission, but don’t specifically and separately check all the numbers in their text. I’ve identified many errors in “final” manuscripts simply by having a separate check for the numbers without paying attention to the text.&#x20;
* **All acronyms are defined during their first use.**
* **All important prior works and research groups are cited.** You should give credit to prior works where it’s due and give readers a broad perspective of the field and various approaches. Also note that this can often be the difference between a referee supporting your work and rejecting it.
* **The abstract and conclusion summarize all the Very Important Numbers.** For example, these sections summarize how many materials were studied, the value of any outstanding property measurements, or the number of candidates recommended for further study.
* **The figures/tables and captions alone tell the story of the paper.** A reader should understand what your paper is about and its major conclusions from the figure and figure captions alone. If you want an example of how to do this well, look at any National Geographic feature article. The articles are usually lengthy, but one gets a good feeling of the article just by looking at the pictures and captions.
* **The acknowledgements are complete.** This includes funding sources (very important for the PI), computing resources (very important for getting computer time), people that helped, and any software you found helpful. See the specific section on proper acknowledgements!

### Miscellaneous advice&#x20;

* Don’t feel like you need to start with a blank page and start typing out a manuscript, start to finish. This rarely ends well. Instead, begin by outlining sections, then gradually filling in details and polishing things over time. You can (and probably should) send Anubhav an initial outline (including planned sections, figures, and main points) prior to do any serious writing. This also works different areas of your brain and helps prevent “writer’s block”, which is usually caused by being fearful that any step you take won’t be “good enough”. Outlining and drafting helps remove this block. The best visual demonstration to see this is to view how even an accomplished artist creates a final painting: [_https://youtu.be/Lye7kK8iOR8_](https://youtu.be/Lye7kK8iOR8) . The final product is stunning, but the initial stages are unimpressive - just outlining, rough shading, etc. Thus, the key to a _**good**_ final product is to (i) start by outlining and (ii) keep polishing, keep improving, keep iterating. The key to a _**great**_ final product is simply to continue thinking about, polishing, and improving the manuscript even after the product looks very good. For example, in the video linked to above, the artist already had a very good painting at the 5:00 mark of the video (about 80% through) and could easily have stopped at that point. Yet the artist continues improving anyway to end up with something even better.&#x20;
* For sections of the paper that are meant to be conversational (i.e., the Introduction, Conclusion, and Discussion), consider speaking your written text out loud. It will help you identify portions of the writing that are best re-worded for clarity.&#x20;
* Keep it short and interesting, especially for early drafts. You want to maintain a high level of reader interest and attention throughout the paper - keep them excited! One can always add more information that really feels missing in a later stage of the draft. If there are tangents or very boring but necessary things to include, they can go in either the methods or the supplementary information where anyone can find it (usually even those without a journal subscription!) and where they won’t interfere with the narrative of the main results. The main results should be exciting!&#x20;
* Try to tell the whole story in two ways. First, a reader reading the main text (but never looking at figures or captions) should understand the whole story, just not all the details. This means that your main text should contain guided tours of your Figures (almost like an audio description) such that even someone who is too lazy to look at the figure can keep reading and know what was presented in the figure. Second, the figures and figure captions should operate independently of the main text. A reader just skimming your figure and figure captions without reading any of the main text should get a sense for all the important results, and the captions should give enough information to let the reader know what they are looking at.

### Tips/checklist for sending papers to Anubhav for review&#x20;

Here are some things you should to do to ensure a timely review of your paper:

* **Include page numbers in the manuscript.**
* **Ensure that what you are sending for review is as short as possible.** For the first review, perhaps this means just an outline with Figures and Figure captions rather than a long paper with a lot of text (that may need to be changed, reorganized, etc).
* **Ensure that the paper is as short as possible.** Ideally, this means an abstract of \~250 words (no more than 300). For the main text, aim for 4500 words and no more than 5500 words (including figure/table captions). If you have more, start putting things in the supplement. We can move things out of supplement later if really needed. If you have trouble deciding what to move to the supplement, talk to Anubhav about how to go about it. Please don’t send Anubhav papers that are >5500 words long for review unless previously agreed this length of paper was necessary - it means you haven’t yet done your job of reducing the paper down to its essence.
