# Toussaint's Regex Tutorial


Introductory paragraph (replace this with your text)


## Summary


Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

## Table of Contents


- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components
Here are the following basic components of regular expressions
1. Anchors
2. Quantifiers
3. Grouping Constructs
4. Bracket Expressions
5. Character Classes
6. Flags


### Anchors
 Anchors are a fundamental concept in regular expressions, helping determine the position of a match in a string. They don't match actual characters in the string but rather positions.

 # Two primary anchors:
- Caret (^):
This anchor matches the start of a string.
For example, ^A will match any string that starts with the letter 'A'.
In multiline mode (usually with the m flag), ^ can also match the start of a line.
- Dollar ($):
This anchor matches the end of a string.
For example, B$ will match any string that ends with the letter 'B'.
In multiline mode, $ can also match the end of a line.

Usage examples:
- `^abc`: Matches any string that starts with "abc".
- `xyz$`: Matches any string that ends with "xyz".
- `^abc$`: Matches the string "abc" in its entirety, without any characters before or after.
- `^$`: Matches an empty string.

Anchors work best when you have specific constraints on the position of a match. They are especially useful when you want to ensure that a pattern matches an entire string or line.


### Quantifiers
Quantifiers in regular expressions define how often an element can occur. They are vital for specifying the frequency of a pattern.

1. Asterisk (*):
Meaning: Matches the preceding character or group 0 or more times.
Example:
ab*c will match "ac", "abc", "abbc", "abbbc", and so on.

2. Plus (+):
Meaning: Matches the preceding character or group 1 or more times.
Example:
ab+c will match "abc", "abbc", "abbbc", and so on, but not "ac".

3. Question Mark (?):
Meaning: Matches the preceding character or group 0 or 1 time (i.e., it makes it optional).
Example:
ab?c will match both "abc" and "ac", but not "abbc".

4. Braces ({}, {n}, {n,}, and {n,m}):
{n}: Matches the preceding character or group exactly n times.
a{3} will match "aaa" but not "aa" or "aaaa".
{n,}: Matches the preceding character or group n or more times.
a{2,} will match "aa", "aaa", "aaaa", and so on, but not "a".
{n,m}: Matches the preceding character or group between n and m times inclusive.
a{2,3} will match "aa", "aaa", but not "a" or "aaaa".

5. Lazy Quantifiers:
By default, quantifiers are "greedy", meaning they match as much as possible. However, by using a lazy quantifier, you can make them match as little as possible:

*?: Matches the preceding character or group 0 or more times, but as few times as possible.
+?: Matches the preceding character or group 1 or more times, but as few times as possible.
??: Matches the preceding character or group 0 or 1 time, but prefers 0 occurrences.
{n,m}?: Matches the preceding character or group between n and m times, but as few times as possible.