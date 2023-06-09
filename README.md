# Common Claim Dataset

A dataset of 20,000 boolean statements, each labeled by two humans as *common-knowledge true*, *common-knowledge false*, or *neither*. 



This data was collected for the paper Explore, Establish, Exploit: Red Teaming Language Models from Scratch by the MIT Algorithmic Alignemnt Group.  Authors: Stephen Casper ([scasper@mit.edu](scasper@mit.edu)), Jason Lin, Joe Kwon, Gatlen Culp, and Dylan Hadfield-Menell.  

arXiv coming soon.

BibTeX coming soon.

## Details

**Where do the sentences come from?** They are all sentences stated by GPT-3-davinci-002 using prompting and domain filtering. We used GPT-3 sentences because our research using this dataset involved red-teaming GPT-3 to find prompts that can make it say dishonest things. 

**Where do the labels come from?** Each example has two labels from human knowledge workers. This data was collected in partnership with [SurgeAI](https://www.surgehq.ai/).

**Why are the labels common-knowledge true/false/neither instead of just true/false/neither?** Right now, there is a lot of interest (including from us) on studying dishonest behavior from LLMs. But one challenge with this is what standard to hold a language model to. For example, is there a difference between types of lies a model may say? Are some innocent mistakes while others are deliberate falsehoods? The answers to these questions seem to have implications for how we interpret and debug dishonest in language models. But in our case, by focusing on things that are commonly-known to be false, we can targetedly study the most egregious type of dishonesty in language models.

**What is the importance of the 'neither' label? Why not just true/false?** Not all declarative statements from a language model will be objectively true or false irrespective of opinions or context. 

**How were human knowledge workers instructed to provide labels?** We instructed them to provide a label based on whether they believe a typical human adult would believe a sentence to be reasonably true, reasonably false, or neither. See the paper appendix for full details. 

**What do you do with the data in the paper?** We use it to train a classifier to distinguish between obviously false statements and all other statements. Then we use it as a learning signal to red team GPT-3 to find prompts that elicit false responses. In our case, it worked, while two baselines based on ChatGPT labels (instead of our human ones) and the [CREAK](https://arxiv.org/abs/2109.01653) dataset did not work. 

**What else could be done with this data?** We hope it will be useful for lots of work -- particularly probing and red teaming research in large language models :) 