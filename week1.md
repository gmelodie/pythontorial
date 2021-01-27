# Week 1: URLs

URLs, or Uniform Resource Locators, are strings of text we use to identify a certain thing inside the web. For example, the URL for the google page is `www.google.com`, or, more completely, `http://www.google.com`. But URLs are not only for web pages, they can locate all sorts of resources in the web. For instance, here's a URL for a dog picture: `https://unsplash.com/photos/9JuzOoPcuHI`.

**Obs**: URL is a type of URI (Uniform Resource Identifier) and, although these are technically different things, we'll use URI and URL interchangeably.

**Obs 2**: Don't worry about the specific functions of each part of a URL for now, we'll dig deeper into that over the following days.

## Challenge
Here's the general schema for a URL:
```
URI = scheme:[//authority]path[?query][#fragment]
```
Read about the syntax on [the Wikipedia page](https://en.wikipedia.org/wiki/URL#Syntax) and build a parser that receives the URL string and prints `True` if the URL is valid or `False` otherwise.

**Test cases**:
```
https://google.com                                              # True
://google.com                                                   # False
ftp://gmelodie:ilovepython@mysite.com.br                        # True
http://gmelodie.me/resume.pdf                                   # True
https://en.wikipedia.org/wiki/URL#Syntax                        # True
https://en.#wikipedia.org/wiki/URL#Syntax                       # False
google.com                                                      # False
https://www.google.com/search?hl=pt&q=i%20love%20python         # True
```

*Hint*: [This syntax analyzing flow](https://en.wikipedia.org/wiki/URL#/media/File:URI_syntax_diagram.svg) is very helpful.

