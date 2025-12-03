This is a skeleton of a process to create word clouds with bigrams and trigrams

# Step 1: Create Unigrams
I used wordclouds.com to create an initial word cloud, to look at the data to know what stop words I needed to add to dictionary. I then downloaded that list of weights and words to clean(word clouds.com extracts unigrams for you). I removed duplicates and plurals and all stop words. I defined stop words as common words, like and, but, going, etc. I then upload the cleaned list to wordclouds.com, and then remove words that are not descriptive of the neighborhood. Including locations, nouns that don't make sense without context (like jeans) and also verbs (like moving). I download that final csv as the completed word cloud. 
# Step 2: Create Bigrams
For bigrams and trigrams, I needed to clean the raw text data. I removed punctuation, removed partial words, converted to lower case. I then used tweet tokenizer to get the bigrams and trigrams, as it is built for social media data. Then I computed a pmi score for every word pairing, which divides out frequency to measure the strength of association between two words. I did make sure each word paring occours at least two times before being scored. I also mimimax scaled them to have the same min and max as the frequency as the I then uploaded that csv of word pairings and pmi scores to wordclouds.com. I used the same criteria to filter out irrelevant pairings. I took out locations, duplicates, and any parings that were not descriptive of the neighborhood. I then saved that final csv to be combined with the unigrams.
# Step 3: Trigrams
Cleaning, tokenizing and scoring is the same as bigrams. There are less trigrams and also less relevant trigrams. I only kept trigrams that did not repeat ideas in the bigrams and trigrams, or that were expanding on those ideas. for example, i kept "east cobb snob" even though i discarded east cobb in the bigrams, because it was a descritpor of the people who lived there and not just the name of a place. 
# Step 4: Combining
The final step was to combine all three csvs and upload to wordcloud.com, which automatically sorts them for you.
# General Philosophy for Cleaning Word Clouds
1. If making unigrams, remove stop words.
2. Remove locations and proper nouns
3. Remove words that are not descriptive of the neighborhood
4. Remove plurals
5. Keep the highest level of word. For example, if unigrams has "improving" and bigrams has "improving neighborhood" or "improving greatly", keep the bigram and remove the unigram, because the bigram is more descriptive.
   
