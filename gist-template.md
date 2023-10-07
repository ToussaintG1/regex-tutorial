# Toussaint's Regex Tutorial


This tutorial tries to teach you the basics of using the specific Regex Tutorial that matches a Hex Value.


## Summary


Here we will be breaking down the following Regular Expression:

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

This Regular expression Matches a Hex Value.


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
Anchors in regular expressions are used to specify a position within the string where a match is to occur. Unlike other components of regex that match characters, anchors match a position. 

In regex `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, the anchors are:

1. `^`: This is the start-of-string anchor. It asserts that the match should begin at the start of the string.
2. `$`: This is the end-of-string anchor. It asserts that the match should end at the end of the string.


### Two primary anchors:

1. `^`: This is the start-of-string anchor. It asserts that the following pattern will start at the very beginning of the string.

2. `$`: This is the end-of-string anchor. It asserts that the preceding pattern will end at the very end of the string.

By combining these two anchors (^ and $), you ensure that the entire string matches the given pattern, and there are no other characters before or after the pattern.




### Quantifiers
Quantifiers in regular expressions define how often an element can occur. They are vital for specifying the frequency of a pattern.

The Quantifiers in `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/` are:

1. `?`: This is a quantifier that matches the preceding element (in this case, the # character) zero or one time. So, the hash symbol is optional.

2. `{6}`: This is a quantifier that matches the preceding element (in this case, the character class [a-f0-9]) exactly 6 times.

3. `{3}`: This is another quantifier that matches the preceding element (again, the character class [a-f0-9]) exactly 3 times.

4. `#?` means it can match a string that starts with a # or doesn't (because of the ? quantifier).

5. `[a-f0-9]{6}` will match any string of exactly 6 characters that are in the range a-f (hexadecimal letters) or 0-9 (digits) because of the {6} quantifier.

6. `[a-f0-9]{3}` will match any string of exactly 3 characters that are in the range a-f or 0-9 because of the {3} quantifier.

### Grouping Constructs
Grouping constructs in regex are used to define subpatterns or groups within the overall pattern. They are essential for multiple purposes, such as capturing substrings, applying quantifiers to multiple characters, or setting up conditions or alternatives within a pattern.

In the regex `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, it contains "Capturing Groups".

1. Capturing Groups:
- `([a-f0-9]{6}|[a-f0-9]{3})`: This is a capturing group. Anything that matches this group can be referenced later (e.g., for backreferences or when extracting matched portions of the input string).
Within this capturing group:

    - `[a-f0-9]{6}` matches a sequence of exactly 6 characters from the range a-f or 0-9 (hexadecimal values).

    - `[a-f0-9]{3}` matches a sequence of exactly 3 characters from the same range.

The | (pipe) character acts as an "OR" operator, meaning the group will capture either a 6-character sequence or a 3-character sequence, but not both.
### Bracket Expressions
In regular expressions, bracket expressions are used to match a single character out of a set of specified characters. They are defined using square brackets 

In the regex `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, it contains the following bracket expressions: 

1. `[a-f]`: This matches any single character that is a lowercase letter from "a" to "f". It represents the hexadecimal characters.

2. `[0-9]`: This matches any single digit from "0" to "9".

Both of these bracket expressions are used to construct the pattern that matches hexadecimal values.


### Character Classes

In regular expressions, character classes are predefined shorthand notations to match specific sets of characters. They provide a more concise way to specify a group of characters than using bracket expressions.

In the Regex Expression  `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, there aren't any Character Classes. 

### The OR Operator
In regular expressions, the "OR" operator, also known as the alternation or choice operator, is represented by the pipe symbol `|`. 
It allows for matching one of several possible patterns. When used, the regex engine will attempt to match each option from left to right until one of the patterns successfully matches.

Within the capturing group `([a-f0-9]{6}|[a-f0-9]{3})`, the "OR" operator separates two alternative patterns:

1. `[a-f0-9]{6}`: This pattern matches a sequence of exactly 6 hexadecimal characters.

2. `[a-f0-9]{3}`: This pattern matches a sequence of exactly 3 hexadecimal characters.

Thus, the "OR" operator allows the regex to match either a 6-character hexadecimal value or a 3-character hexadecimal value within the given string.

### Flags
In regular expressions, flags (also called modifiers) are used to change the search behavior of the pattern. They affect how the regex matches strings.

In the regex `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, there are no flags.

### Character Escapes
In regular expressions, character escapes are used to represent special characters or to give characters special meanings. They are typically formed using a backslash \ followed by a character.

The regex `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/` contains the following Character Escapes:

1. `^`: This character is an anchor for the start of a string or line, but in some contexts (like within a bracket expression), it could be considered an escape character (to denote negation). However, in this regex, it's not used as an escape but as an anchor.

2. `#`: The hash symbol does not have special meaning in most regex flavors, so it doesn't need to be escaped to match a literal #. However, in some contexts or regex flavors, you might escape it to ensure it's treated as a literal.

3. `$`: This character is an anchor for the end of a string or line. Like ^, in this context, it's used as an anchor, not an escape.

4. `{ and }`: These are used for quantification (to specify how many times an element should be matched). In this regex, `{6}` and `{3}` denote quantifiers, so the curly braces aren't being used as escape sequences for literal characters.