# Regex Tutorial: Match URL with Regular Expressions

URL Regex: A regular or rational expression defined as characters in a pattern or a sequence that replace or find string operations which may be useful locating a string in a URL.

## Summary

A Regex proves useful in matching a URL in order to locate special text patterns. 
```
https?:\/\/(www\.)?[\d-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)
```
## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)

## Regex Components

### Anchors
Anchors are used at the beginning and end of searches to check if a string fully matches a pattern, although they themselves do not match characters. They strictly affirm a string matches a location. Anchors will create parameters.
* Use the ```^``` anchor to match the beginning of the text. 
* Use the ```$``` anchor to match the end of the text.

### Quantifiers
Quantifiers will measure and set the limit on the the number of characters that we are wanting to match in our Regex: ```+``` searches the pattern one or more times, ```?``` searches the pattern zero or one time, * searches the pattern zero or more times.
``` https? ``` for= example. The ? will make the preceeding itme optional.

### OR Operator
The purpose of an OR operator is to match the characters on the left or right of the operator, essentially serving as an or, as in and/or. Using the | as in m|M would match either m or an M from the string. If we had used ```https?:\/\/(www\.)?[\d-a|A``` it would search or a OR A.


### Character Classes
A character class is  the set of characters that could occur in a string.  
The \d character class in the above code is looking for any digits, whereas a \D looks for non-digits, \s searches for space symbols, tab and newlines, \S looks for all but \s, \. any characters with the regex 's' flag, while the included \w character is looking for an alphanumeric character. 

### Flags
Flags are used at the end of a regex, after a closing slash. They are tokens that will modify parameters of a search. Multiple flags can be set by writing one after another with NO spaces. Flags must be written in lowercase. This URL does not contain any flags. An example of a flag would be if the above expression showed: (shows global expression. See below)
```
https?:\/\/(www\.)?[\d-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)g
```
Flag Expressions:
* i: Ignores casing. Makes expression case-sensitive
* g: Global. Makes expression search for all occurences
* s: Dot All. Makes the wild characters . match newlines as well
* m: Multiline. Makes boudnary characters ^ and $ match beginning and end of every line.
* y: Sticky. Indicates that it matches only from the index indicated by the lastIndex property of this regular expression in the target string (and does not attempt to match from any later indexes)
* u: Unicode. Expression assumes individual characters are code points, not code units and will then match 32 bit characters.

### Grouping and Capturing
Capturing Group is a part of a pattern that can be enclosed in a parentheses () and is a way to treat multiple characters as one unit. The example expression has many groupings such as: 
```https?:\/\/``` which is looking for the http(s),```(www\.)?[\d-a-zA-Z0-9@:%._\+~#=]``` which will look for initial domain, ```[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]``` looks for top level domain, and ```*)``` file paths.

### Bracket Expressions
is a matching or non-matching list expression and consists of one or more expressions that will be found in square brackets []. It represents a special character class and is a quantified rule providing range construct. They adapt to a users or applications locale. 

### Greedy and Lazy Match
As expected, the definition of a greedy match, is a search that will try to find the longest possible string, whereas a lazy match is search will find the smallest possible string. 
Greedy quantifiers are:
- + = one or more revised gist
- * = Zero or more
- {2,4} = Two to four times as greedy
Lazy quantifier:
- ?
This expression : 
```(https?:\/\/)?``` uses the lazy match of ? and is looking http OR https, ```[a-zA-Z0-9()]{1,6}``` is looking for a-z, A-Z, 0-9; one to six times as greedy.

### Boundaries
Boundaries are similar to an anchor and uses the expression \b for word boundaries and \B for non-word boundaries. They are a zero-length match that marks the beginning and end of an alphanumerical sequence and will make it easier to find whole words. The beginning of this expression ```\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)``` is searching for a whole word or digit.

### Back-references
Backreferences are filters used to match the same text previously matched by a capturing group. An example would be when you desire to search for a repeated word, the first match could use a pattern that extracts a signle word, the second would be a back reference that referes to the captured group. The above example does not include any backreferences.
