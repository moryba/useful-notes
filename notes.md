# Build an environment

1 - mkdir a folder

2 - digit in the terminal ---> py -m env env

3 - cd dir to env

4 - go to ----> Scripts\activate

5 - install streamlit (or other programs) into the environment ------> pip install streamlit

6 - runnig your application ----> streamlit run app.py

# PowerBI - DAX formulas

1 - create a coumpund key -----> compund key = [ID] & "-" & [date]

2 - IF condition:

    - IF(Expression, Value if TRUE, Value if FALSE)
    
    - IF('Customer Data'[Shopping Frequency] IN {"Daily", "Monthly", "Weekly"},"Frequent Shopper","Infrequent Shopper")
    
3 - SWITCH -----> SWITCH("Customer Data"[State], "Texas", "Growth Market", "New York", "Estabilished Market", "Deprioritized Market")

4 - LOOKUPVALUE(Table2[column Interested), Table2[Key], Table1[Key])

5 - SUMX(Table, Table[Column]) ----> the output is the sum of all the values in a column

6 - Table1[Column1] * RELATED(Table2[Column2])) ----> RELATED fuction give us the product between column1 in table1 and the column2 of the table2. Keep in mind that the two tables must have a relationship 

# Data Viz
- [A Complete Guide to Bar Charts](https://chartio.com/learn/charts/bar-chart-complete-guide/)
- [A Complete Guide to Area Charts](https://chartio.com/learn/charts/area-chart-complete-guide/)
- [Change How Visuals Interact in a Report](https://docs.microsoft.com/en-us/power-bi/create-reports/service-reports-visual-interactions)
- [Battle of the Charts: Pie Chart vs. Donut Chart](https://www.beautiful.ai/blog/battle-of-the-charts-pie-chart-vs-donut-chart)
- [7 Secrets of the Matrix Visual](https://www.burningsuit.co.uk/7-secrets-of-the-matrix-visual/)
- [A Complete Guide to Scatter Plots](https://chartio.com/learn/charts/what-is-a-scatter-plot/)
- [Tips and Tricks for Power BI Map Visualizations](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-map-tips-and-tricks)
- [Create and Use Filled Maps (Choropleth Maps) in Power BI](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-filled-maps-choropleths)
- [Design guide for Power BI Slicers and filters](https://okviz.com/blog/design-guide-for-power-bi-slicers-and-filters/)

# How to create a dynamic date table on Power Query

- Create a query for the Start Date ----->Strat = Date.StartOfYear(List.Min(#"Name of the table"[Column Date]))
- Create a query for the End Date ------> End = Date.StartOfYear(List.Max(#"Name of the table"[Column Date]))
- Create a list and convert it into a table ------> ={Number.From(#"Start")..Number.From(#"End")}
- suggestions---> if you wanna put zero before the number of the month: = Text.PadStart(Text.From([Month Name]),2,"0")

# Power App - some useful links

List of useful links:

- [Text Input AutoHeight](https://www.youtube.com/watch?v=Rh20he80OLA)

# Some cmd prompt

- append multiple files------> copy *.csv combine.csv
- download this browser to run selenium edge: https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/

# Regular expression

## Shorthand character classes

\w ---> the "word character" class represents the regex range [A - Za - z0 - 9_], and it matches a single uppercase character, lowercase character, digit or underscore

\d ---> the "digit character" class represents the regex range [0-9], and it matches a single digit character

\s ---> the "whitespace character" class represents the regex range [ \t\r\n\f\v], matchinga single space, tab, carriage return, line break, from feed, or vertical tab

For example, the regex \d\s\w\w\w\w\w\w\w matches a digit character, followed by a whitespace character, followed by 7 word characters. Thus the regex completely matches the text 3 monkeys. 

In addition to the shorthand character classes \w, \d, and \s, we also have access to the negated shorthand character classes! These shorthands will match any character that is NOT in the regular shorthand classes. These negated shorthand classes include:

- \W ---> the "non-word charcater" class represts the regex range [^A-Za-z0-9_], matching any character tha is not included in the range represented by \w
- \D ---> the "non-digit character" class represents the regex range [^0-9], matching any character that is not included in the range represented by \d
- \S ---> the "non-whitespace character" class represents the regex range [^\t\r\n\f\v], matching any character that is not included in the range represented by \s

## Grouping

The regext I love (baboons|gorillas) will match the text I love and then match either baboons or gorillas, as the grouping limits the reach of the | to the text within the parentheses. 

These groups are also called capture groups, as they have the power to select, or capture, a substring from our matched text. 

## Quantifiers - Fixed

Instead of writing the regex \w\w\w\w\w\w\s\w\w\w\w\w\w, which would match 6 word charcters, followed by a whitespace charcter, and then followed by more characters, such as in the text rhesus monkey, there is a a better way to denote the quantity of characters we want to match on. 

- \w{3} will match exactly 3 word characters
- \w{4,7} will match at minimum 4 word characters and at maximum 7 word characters

The regex roa{3}r will match the characters ro followed by 3 as, and then the character r, such as in the text roaaar. The regex roa{3,7}r will match the characters ro followed by at least 3 as and at most 7 as, followed by an r, matching the strings roaaar, roaaaaar and roaaaaaaar.


## Quantifiers - Optional

Optional quantifiers, indicated by the question mark ?, allow us to indicate a character in a regex is optional, or can appear either 0 times or 1 time. For example, the regex humou?r matches the characters humo, then either 0 occurrences or 1 occurrence of the letter u, and finally the letter r. Note ? only applies to the character directly before it. 

With all quantifiers, we can take advantage of grouping to make even more  advanced regexes. The regex 'The monkey ate a (rotten )?banana' will completely match both 'The monkey ate a rotten banana' and 'The monkey ate a banana'.

Since the ? is a metacharacter, you need to use the escape character in your regex in order to match a question mark ? in a piece of text. The regex 'Aren't owl monkeys beautiful\?' will thus completely match the text 'Aren't owl monkeys beautiful\?'.


## Quantifiers - 0 or More, 1 or More

The Kleene star, denoted with the asterisk *, is also a quantifier, and matches the preceding character 0 or more times. This means that the character doesn’t need to appear, can appear once, or can appear many many times.

The regex meo*w will match the characters me, followed by 0 or more os, followed by a w. Thus the regex will match mew, meow, meooow, and meoooooooooooow.

Another useful quantifier is the Kleene plus, denoted by the plus +, which matches the preceding character 1 or more times.

The regex meo+w will match the characters me, followed by 1 or more os, followed by a w. Thus the regex will match meow, meooow, and meoooooooooooow, but not match mew.

Like all the other metacharacters, in order to match the symbols * and +, you need to use the escape character in your regex. The regex My cat is a \* will completely match the text My cat is a *.

## Anchors

The anchors hat ^ and the dollar sign $ are used to match text at the start and the end of a string, respctively.  For example, the regex ^Monkeys: my mortal enemy$ will completely match the text Monkeys: my mortal enemy but not match Spider Monkeys: my mortal enemy in the wild or Spider Monkeys: my mortal enemy in the wild. In fact, the ^ ensures that the matched text begins with Monkeys, and the $ ensures the matched text ends with enemy. 


# Text Preprocessing

<img width="383" alt="text_preprocessing" src="https://user-images.githubusercontent.com/24205674/158189735-86fb5e5e-86b6-47bd-8640-b0904a4699ac.PNG">

Text preprocessing is an approach for cleaning and preparing text data for use in a specific context. It involves the following steps:

- Using Regex & NLTK libraries
- Noise Removal - removing unnecessary characters and formatiing
- Tokenization - break multi-word strings into smaller components
- Normalization - acatch-all term for processing data; this includes stemming and lemmatization

## Noise Removal

It is possible to use the .sub() method in Python's regular epresion (re) library for most of your oise removal needs. The .sub() method has three required arguments:

- pattern - a regular expression that is searched for in the input string. There must be an r preceding the string to indicate it is a raw string, which treats backslashes as literal characters. 
- replacement_text - text that replaces all matches in the input string
- input - the input string that will be edited by the .sub() method
below an example in which we replace all tag <p> with '':
import re
text = "<p>    This is a paragraph</p>"
result = re.sub(r'<.?p>','',text)
print(result)------->    This is a paragraph

Anther example in which we want to remove the white space before the phrase:
import re
text = "    This is a paragraph"
result = re.sub(r'\s{4}','',text)

print(result)------->This is a paragraph

## Tokenization 

The method for breaking text into smaller components is called tokenization and the individual components are called tokens. A few common operations that require tokenization include:
- finding how many words or sentences appear in text
- determining how many times a specific word or phrase exists
- accounting fr which terms are likely to co-occur

To tokenize individual words, we can use nltk's word_tokenize() function. The functon accepts a string and returns a list of words:

from nltk.tokenize import word_tokeniz

text = "Tokenize this text"
tokenized = word_tokenize(text)

print(tokenized) --------------> ["Tokenize", "this", "text"]

To tokenize at the sentence level, we can use sent_tokenize() from same module.
from nltk.tokenize import sent_tokenize

text = "Tokenize this sentence. Also, tokenize this sentence."
tokenized = sent_tokenize(text)

print(tokenized) --------------> ['Tokenize this sentence.', 'Also, tokenize this sentence.']

## Normalization

Tokenization and noise removal are staples of almost all text pre-processing pipelines. However, some data may require futher processing through text normalization. Text normalization is a catch-all term for various text pre-processing tasks. Some are:
- Uper or lowercasing
- Stopword removal
- Stemming - bluntly removing prefixes and suffixes from a word
- Lemmatization - replacing a single-word token with its root

The simplest of these approaches is to change the case of a string. We can use Python's built-in String methods to make a sting all uppercase or lowercase:
my_string = 'tHiS HaS a MiX oF cAsEs'

print(my_string.upper())--------------> 'THIS HAS A MIX OF CASES'

print(my_string.lower())--------------> 'this has a mix of cases'


## Stopword Removal

Stopwords are words that we remove during preprocessing when we don't care about sentence structure. They are usually the most common words in a language and don't provide any information about the tone of statement. They include words such as "a", "an", and "the".

NLTK provides a built-in library with these words. You can import them using the following statement:

from nltk.corpus import stopwords
stop_words = set(stopwords.words('english'))

Now that we have the words saved to stop_words, we can use tokenization and a list comprehension to remove them from a sentence:
nbc_statement =  "NBC was founded in 1926 making it the oldest major broadcast network in the USA"

word_tokens = word_tokenize(nbc_statement) 

statement_no_stop = [word for word in word_tokens if word not in stop_words]

print(statement_no_stops) --------------> ['NBC', 'founded', '1926', 'making', 'oldest', 'major', 'broadcast', 'network', 'USA']

## Stemmming

In natural language processing, stemming is the text preprocessing normalization task concerned with bluntly removing word affixes (prefixes and suffixes). For example, stemming would cast the word "going" to "go". This is a common method used by search engines to improve matching between user input and website hits.

NLTK has a built-in stemmer called PorterStemmer. You can use it with a list comprehension to stem each word in a tokenized list of words.
 
from nltk.stem import PorterStemmer
stemmer = PortesStemmer()

tokenized = ['NBC', 'was', 'founded', 'in', '1926', '.', 'This', 'makes', 'NBC', 'the', 'oldest', 'major', 'broadcast', 'network', '.']

stemmed = [stemmer.stem(token) for token in tokenized]

print(stemmed) --------------> ['nbc', 'wa', 'found', 'in', '1926', '.', 'thi', 'make', 'nbc', 'the', 'oldest', 'major', 'broadcast', 'network', '.']
        
## Lemmatization

Lemmatization is a method for casting words to their root forms. This is a more involved process than stemming, because it reqires the method to know the part of speech for each word. Since lemmatization requires the part of speech, it is a less efficient approach than stemming.

We can use NLTK's WordNetLemmatizer to lemmatize text:

from nltk.stem import WordNetLemmatizer
lemmatizer = WordNetLemmatizer()

tokenized = ["NBC", "was", "founded", "in", "1926"]

lemmatized = [lemmatizer.lemmatize(token) for token in tokenized]

print(lemmatized) -------------> ["NBC", "wa", "founded", "in", "1926"]

The result saved to lemmatized contains 'wa', while the rest of the words remain the same. Not too useful. This happened because lemmatize() treats every word as a noun. To take advantage of the power of lemmatization, we need to tag each word in our text.

## Part-of-Speech Tagging

To improve the performance of lemmatization, we need to find the part of speech for each word in our string. 

- import wordnet and counter: from nltk.corpus import wordnet, from collections import Counter
- get synonyms with wordnet.synsets(word)
- create a Counter() object and set each value to the count of the number of synonyms that fall into each part of speech: pos_counts["n"] = len(  [ item for item in probable_part_of_speech if item.pos()=="n"]  )
- return the most common part of speech: now that we have a count for each part of speech, we can use the .most_common() counter method to find and return the most likely part of speech: most_likely_part_of_speech = pos_counts.most_common(1)[0][0]
- After finding the most probable part of speech for a given word, we can pass this into our lemmatizer when we find the root for each word. 

Example:

tokenized = ["How", "old", "is", "the", "country", "Indonesia"]
lemmatized = [lemmatizer.lemmatize(token, get_part_of_speech(token)) for token in tokenized]

print(lemmatized) ----------------> ['How', 'old', 'be', 'the', 'country', 'Indonesia']

Below some useful links:

- https://www.nltk.org/book/ch03.html
- https://pythonprogramming.net/tokenizing-words-sentences-nltk-tutorial/
- https://pythonprogramming.net/stop-words-nltk-tutorial/
- https://pythonprogramming.net/stemming-nltk-tutorial/
- https://pythonprogramming.net/lemmatizing-nltk-tutorial/

## Natural Language parsing with regular expressions

# Compiling and Matching

.compile() is a method that takes a regular expression pattern as an argument and compiles the pattern into a regular expression object, which you can later use to find matching text. The regular expression object below will exactly match 4 upper or lower case characters. 

regular_expression_object = re.compile("[A-Za-z]{4}")

Regular expression objects have a .match() method that takes a string of text as an argument and looks for a single match to the regular expression that starts at the beginning of the string. To see if your regular expression matches the string "Toto" you can do the following:

result = regular_expression_object.match("Toto")

If .match() finds a match that starts at the beginning of the string, it will return a match object. The match object lets you know what piece of text the regular expression matched, and at what index the match begins and ends. If there is no match, .match() will return None. 

With the match object stored in result, you can access the matvhed text by calling result.group(0). If you use a regex containing capture groups, you can access these groups by calling .group() with the appropriately numbered capture group as an argument. 

Instead of compiling the regular expression first and then looking for a match in separate lines of code, you can simplify your match to one line:

result = re.match("[A-Za-z]{4}, "Toto")

With this syntax, re'S .match() method takes a regular expression pattern as the first argument and a string as the second argument. 

## Searching and finding

You can make your regular expression matches even more dynamic with the help of the .search() method. Unlike .match() which will only find matches at the start of a string, .search() will look left to right through an entire piece of text and return a match object for the first match to the regular expression given. If no match is found, .search() will return None. For example, to search for a sequence of 8 word characters in the string:

result = re.search("\w{8}","Are you a Munchkin?")

Using .search() on the string above will find a match of "Munchkin", while using .match() on the same string would return None!

So far you have used methods that only return one piece of matching text. What if you want to find all the occurrences of a word or keyword in a piece of text to determine a frequency count?Step in the .findall() method!

.findall() will return a list of all non-overlapping matches of regular expression in the string. Consider the below piece of text:

text = "Everything is green here, while in the country of the Munchkins blue was the favorite color. But the people do not seem to be as friendly as the Munchkins, and I'm afraid we shall be unable to find a place to pass the night."

So, to find all non-overlapping sequences of 8 word characters in the sentence you can do the following:

list_of_matches = re.findalll("\w{8}", text)

.findall() will tus return the list:
['Everythi', 'Munchkin', 'favorite', 'friendly', 'Munchkin']

# Part-of-speech Tagging

The process of identifying and labeling the part of speech of wods is known as part-of-speech tagging!
- Noun: the name of a person(Moryba), place(Italy), thing or idea(NLP)
- Pronoun: a word used in place of a noun (her, she
- Determiner: a word that introduces, or "determines", a noun (the)
- Verb: expresses action (studying) or being (are, has)
- Adverb: modifies or describes a verb, an adjective, or another adverb (happily)
- Preposition: a wod placed before a noun or pronoun to form a phase modifying another word in the sentence (on)
- Conjunction: a word that joins words, phrases, o clauses (and)
- Interjection: a word used to express emotion (Wow)

It is possible to automate the part-of-speech tagging process with nltk's pos_tag() function. The function takes one argument, a list of words in the order they appear in a sentence, and returns a list of tuples, where the first entry in the tuple is a word and the second is the part-of-speech tag. 

word_sentence = ['do', 'you', 'suppose', 'oz', 'could', 'give', 'me', 'a', 'heart', '?']

you can tag the parts of speech as follows:
part_of_speech_tagged_sentence = pos_tag(word_sentence)

The call to pos_tag() will return the following:

[('do', 'VB'), ('you', 'PRP'), ('suppose', 'VB'), ('oz', 'NNS'), ('could', 'MD'), ('give', 'VB'), ('me', 'PRP'), ('a', 'DT'), ('heart', 'NN'), ('?', '.')]

Abbreviations are given instead of the full part of speech name. Some common abbreviations include: NN for nouns, VB for verbs, RB for adverbs, JJ for adjectives, and DT for determiners. 

![image](https://user-images.githubusercontent.com/24205674/158617330-fbf938a7-3ecb-4cd3-8b24-0449741d26a3.png)

## Intoduction to Chunking

It is possible to use regular expressions to find patterns in sentence structure that give insight into the meaning of a text. This technique of grouping words by their part-of-speech tag is called **chunking**.

With chunking in nltk, you can define a pattern of parts-of-speech tags using a modified notation of regular expressions. You can then find non-overlapping matches, or chunks of words, in the part-of-speech tagged sentences of a text.

The regular expression you build to find chunks is called chunk grammar. A piece of chunk grammar can be written as follows:

chunk_grammar = "AN: {<JJ><NN>}"

- **AN** is a user-defined name for the kind of chunnk you are searching for. You can use whatever name makes sense given your chunk grammar. In this case AN stands for adjective-noun
- A pair of curly braces **{}** sorround the actual chunk grammar
- **<JJ>** operates similarly to a regex character class, matching any adjective
- **<NN>** matches any noun, singular or plural
    
The chunk grammar above will thus match any adjective that is followed by a noun.To use the chunk grammar defined, you must create a nltk RegexParser object and give it a piece of chunk grammar as an argument.
    
    chunk_parser = RegexParser(chunk_grammar)
    
You can then use the **RegexpParser** object's **.parse()** method, which takes a list of part-of-speech tagged words as an argument, and identifies where such chunks occur in the sentence.
    
Consider the part-of-speech tagged sentence below:
    
    pos_tagged_sentence = [('where', 'WRB'), ('is', 'VBZ'), ('the', 'DT'), ('emerald', 'JJ'), ('city', 'NN'), ('?', '.')]
    
You can chunk the sentence to find any adjectives followed by a noun with the following:

chunked = chunk_parser.parse(pos_tagged_sentence)
    
## Chunking Noun Phrases

While you are able to chunk any sequence of parts of speech that you like, there are certain types of chunking that are linguistically helpful for determining meaning and bias in a piece of text. One such type of chunking is NP-chunking, or **noun phrase chunking**. A noun phrase is a phrase that contains a noun and operates, as a unit, as a noun. 

A popular form of noun phrase begins with a determiner DT, which specifies the noun being referenced, followed by any number of adjectives JJ, which describe the noun, and ends with a noun **NN**.

Consider the part-of-speech tagged sentenc below:

 [('we', 'PRP'), ('are', 'VBP'), ('so', 'RB'), ('grateful', 'JJ'), ('to', 'TO'), ('you', 'PRP'), ('for', 'IN'), ('having', 'VBG'), ('killed', 'VBN'), ('the', 'DT'), ('wicked', 'JJ'), ('witch', 'NN'), ('of', 'IN'), ('the', 'DT'), ('east', 'NN'), (',', ','), ('and', 'CC'), ('for', 'IN'), ('setting', 'VBG'), ('our', 'PRP$'), ('people', 'NNS'), ('free', 'VBP'), ('from', 'IN'), ('bondage', 'NN'), ('.', '.')]
    
Can you spot the three noun phrases of the form described above? They are:
    
    - (('the', 'DT'), ('wicked', 'JJ'), ('witch', 'NN'))
    - (('the', 'DT'), ('east', 'NN'))
    - (('bondage', 'NN'))

With the help of a regular expression defined chunk grammar, you can easily find all the non-overlapping noun phrases in a piece of text. Just like in normal regular expressions, you can use quantifiers to indicate how many of each part of speech you want to match. The chunk grammar for a noun phrase can be written as follows:
    
    chunk_grammar = "NP: {<DT>?<JJ>*<NN>}"
    
    - **NP** is the user-defined name of the chunk you are searching for. In this case NP stands for noun phrase
    - **<DT>** matches any determiner
    - **?** is an optional quantifier, matching either **0** or **1** determiners
    - **<JJ>** matches any adjective
    - * is the Kleene star quantifier, matching **0** or more occurances of an adjective
    - **<NN>** matches any noun, singular or plural
    
By finding all the NP-chunks in a text, you can perform a frequency analysis and identify important, recurring noun phrases. You can also use these NP-chunks as pseudo-topics and tag articles and documents by their highest count NP-chunks! Or perhaps your analysis has you looking at the adjective choices an author makes for different nouns. 

It is ultimately up to you, with your knowledge of the text you are working with, to inerpret the meaning and use-case of the NP-chunks and their frequency of occurrence. 

## Chunking Verb Phrases
    
Another type of chunking is VP-chunking, or verb phrase chunking. A verb chunking is a phrase that contains a verb and its complements , objects, or modifiers.

Verb phrases can take a variety of structures, and here you will consider two. The first structure begins with a verb VB of any tense, followed by a noun phrase, and ends with an optional adverb RB of any frm. The second structure switches the order of the verb and the noun phrase, but also ends with an optional adverb. 
    
Both structures are considered because verb phrases of each form are essentially the same in meaning. For example, consider the part-of-speech tagged verb phrases given below:
    - (('said', 'VBD'), ('the', 'DT'), ('cowardly', 'JJ'), ('lion', 'NN'))
    - ('the', 'DT'), ('cowardly', 'JJ'), ('lion', 'NN')), (('said', 'VBD'),
 
 The chunk grammar to find the first form of verb phrase is given below:
    
    chunk_grammar = "VP: {<VB.*><DT>?<JJ>*<NN><RB.?>?}"
    
  
    


    


