# What is a Regex
HTML, is without a doubt the backbone of web pages; it is made up of various elements, which are often represented by tags. Web developers sometimes need to parse, sometimes extract, or validate HTML content. This is the main reason where regular expressions come in handy. This tutorial aims to dissect a specific regex that matches an HTML tag, helping you understand its components and how it works.
Here's the regex pattern that we will be looking in this tutorial:
/^<([a-z]+)(1+)(?:>(.)</\1>|\s+/>)$/
# Regex Components
## Anchors
The "^" and "$" are anchor characters: /^<([a-z]+)(1+)(?:>(.)</\1>|\s+/>)$/
^ marks the position at the start of a line. $ marks the position at the end of a line. But when they are together, they ensure that the pattern matches an entire line: from start to finish.
## Quantifiers
+: This one matches the preceding element one or more times. *: and this one matches the preceding element zero or more times.
## Grouping Constructs
There are several groups in our regex, we're going to paste it again for quick reference /^<([a-z]+)(1+)(?:>(.)</\1>|\s+/>)$/:
([a-z]+): This one matches one or more lowercase letters. In this case, it captures the tag name. (1+): This matches any sequence of characters except "<", and it's used to capture tag attributes. (?:>(.)</\1>|\s+/>): Finally, this is a non-capturing group, denoted by (?:...). Within it, we have two patterns separated by the OR operator (|):
The first pattern matches content between paired tags, and the second pattern matches self-closing tags.
## Bracket Expressions
Like we said in grouping constructs, [a-z] matches any lowercase letter from 'a' to 'z'; on the other hand, 1: matches any character that is not a <.
## Character Classes
Character classes allow for matching one out of several characters. They are denoted by square brackets []. In our regex:
[a-z]: Represents a character class that matches any lowercase letter from a to z.
## The OR Operator
The "|" character represents the OR operator, like we anticipated earlier. It allows the regex to match one of several patterns. In our regex, it differentiates between paired tags and self-closing tags.
## Flags
The given regex does not have any flags: /^<([a-z]+)(1+)(?:>(.)</\1>|\s+/>)$/.
But what are they?
Flags are usually specified after the closing / in a regex and they modify the search behavior.
Common flags include "i" for case-insensitive matching, "g" for global matching, and "m" for multi-line matching.
## Character Escapes
Character escapes are sequences that are used to represent special characters in regex. In our regex, we have a few character escapes:
<: Escapes the < character, allowing it to be matched literally. /: Escapes the / character, allowing it to be matched literally.
