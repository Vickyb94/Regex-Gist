# Title (RegexGist- Matching an Email)

This is tutorial on components of the regular expressions used in matching an email. A Regular Expression is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input e.g an email address.


## Summary

This tutorial is aimed at explaining the components of the regular expressions used in matching an email.
The following regular expression can be used to validate user input as a valid email address:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Each component of this regex has a unique responsibility to make sure that a user enters an email address that begins with an unspecified number of characters preceding the @ symbol, followed by a domain.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors
 Anchors declare that the engine's current position in the string matches a well-determined location. To validate user input in email address, regex uses start-of-string anchor (^) and end-of string anchor ($). Using an anchor helps to specify that you want to match digits at the end of a line, but not anywhere else. It also tells the engine when to find a compex pattern at a given location. Even when regex matches without anchors, it is recommended to still use them whenever possible.

### Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. In this regex, the quantifiers are the (+) operator and the range (2,6). The + operator prompts the regex to attempt to match everything within the capture group as many times as possible. The range quantifier also tells the regex to attempt to match the largest group possible within this range as many times as it can. 
To avoid having a very large input, infinite quantifiers can be replaced by finite ones. For example,

^[A-Z0-9._%+-]{1,64}@(?:[A-Z0-9-]{1,63}\.){1,125}[A-Z]{2,63}$ 

the regex above takes into account the local part before the domain name and sets a limit to the length and number of sub-domains.


### Character Classes

A character class allows you to match any symbol from a certain character set. The character class in this regex is  \d which is used to match any digit character. The backlash / is used to separate the digit class from the letter d.

### Grouping and Capturing

There are three capturing groups in this expression and they are captured within a Captured Group using parenthesis (). Take a look at this regular expression below;

/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

([a-z0-9_.-]+) - matches the user email name,

([\da-z.-]+) - matches the email service,

([a-z\.]{2,6}) - matches/captures the domain name.

### Bracket Expressions

A bracket expression are usually enclosed in square brackets, "[]". A bracket expression represents a single character within the brackets/string. The set of characters include anything from the numbers 0-9, letters a-z, underscore or hyphen. Hence, [a-z0-9_.-], [\da-z.-], and [a-z.].

### Greedy and Lazy Match

This expression only has the greedy match and they are the quantifiers - the (+) operator and the range (2,6). They both prompt the regex to match as many times as possible.


## Author

My name is Victoria and I am a full stack developer. You can find more of my projects on https://github.com/Vickyb94
