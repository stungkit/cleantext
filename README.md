# cleantext
cleantext is a an open-source python package to clean raw text data. Source code for the library can be found [here.](https://github.com/prasanthg3/cleantext)



## Features 

cleantext has two main methods,
* **clean**: to clean raw text and return the cleaned text
* **clean_words**: to clean raw text and return a list of clean words

cleantext can apply all, or a selected combination of the following cleaning operations:
* Remove extra white spaces
* Convert the entire text into a uniform lowercase
* Remove digits from the text
* Remove punctuations from the text
* Remove stop words, and choose a language for stop words
( Stop words are generally the most common words in a language with no significant meaning such as is, am, the, this, are etc.)
* Stem the words
(Stemming is a process of converting words with similar meaning into a single word. For example, stemming of words run, runs, running will result run, run, run)

## Installation

cleantext requires [Python 3](https://www.python.org/downloads/) and [NLTK](http://www.nltk.org/install.html) to execute. 

To install using pip, use

`pip install cleantext`

## Usage

* **Import the library**:

``` python
import cleantext
```

* **Choose a method:**

 To return the text in a string format, 
 
``` python
cleantext.clean("your_raw_text_here", all= True) 
```
 
 To return a list of words from the text,
 
``` python
cleantext.clean_words("your_raw_text_here", all= True) 
```
 
 To choose a specific set of cleaning operations,

``` python
cleantext.clean_words("your_raw_text_here",
all= False # Execute all cleaning operations
extra_spaces=True ,  # Remove extra white space 
stemming=True , # Stem the words
stopwords=True ,# Remove stop words
lowercase=True ,# Convert to lowercase
numbers=True ,# Remove all digits 
punct=True ,# Remove all punctuations
stp_lang='english'  # Language for stop words
)
```

## Examples

``` python
import cleantext
cleantext.clean('This is A s$ample !!!! tExt3% to   cleaN566556+2+59*/133', extra_spaces=True, lowercase=True, numbers=True, punct=True)
```

returns,

``` Python
'this is a sample text to clean'
```

----

``` Python
import cleantext
cleantext.clean_words('This is A s$ample !!!! tExt3% to   cleaN566556+2+59*/133', all=True)
```

returns,

``` Python
['sampl', 'text', 'clean']
```

## License

##### MIT

For any questions, issues, bugs, and suggestions please visit [here](https://github.com/prasanthg3/cleantext/issues)
