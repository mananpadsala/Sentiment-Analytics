# README

## NOTE: Multiprogramming is implemented according to my device. It can be optimized on the use cases (how much computation is available)

## Functions and its roles:

Scraper: It is the main function that is scraping from the URLS. Beautiful Soup library is used for this purpose. Multiprogramming concept is used to reduce the time (approximately by 70-80%). Hence, a list is passed which contains first and last page no of that batch (Eg: [1,5] i.e. this batch will process pages 1-4. Similarly different batches will run parallely). All the results are stored with the filename of url_id as asked.

Note: Some pages were not available and hence that pages were dropped

start_end: this function is used to divide the 114 pages into mini batches that will run parallely

run_parallel: This will map our batches to the multiprocesses. Multiprocessing library is used.

get_stop_words: This will return a list that will contain all the stop words that are provided in the txt files in the stopwords folder 

Note: This will also contain all the punctuations also.

stop_words_clean: This function will fetch the blog body of al all the scraped pages and will clean it (i.e. remove stop words) and save the reult in another column of our DataFrame for future use

get_negative_words: This will return the list of all words provided in the negative words file in master dictionary

get_positive_words: This will return the list of all words provided in the positive words file in master dictionary

derived_variables: All the required analysis variables are created as a column in the dataframe. This function is used to determine the postive score, negative score and polarity and will fill the respective data

syllables: This function takes word as a input and returns no. of syllables in that word

__concat, __Capitalize_first_char, __split,split: These are some mini functions that can be used in our main functions for the tasks clear by theri names

length_all: This function will return total characters in the blog body

syllables_per_word: This wil return list containing syllables per word in ‘cleaned’ data

complexwords: This will return no of complex words present in the blog body

wordcount, sentencecount: Clear by names

pp: This will return no. of personal pronouns present in the blog body

analysis: This function calculates all the variables including gunning fog index except word count and will store the respective information

cleaned_word_ops: This will calculate the word count in cleaned blog body (i.e. without stop words)

## NOTE: All the variables are determined on the blog body. Only word count is determined on cleaned blog body (i.e. without having stop words)

run_parallel_2: The analysis process can also be multiprocessed which will reduce time by 70% but will require more memory. If avaliable we can implement using this function. For now we are performing it in a single process only.

save: This will save our output file in the desired format

script function: Contains series of function calls

## OUTPUT: Scraped data will be stored under scraped data folder and output is stored as Output.csv