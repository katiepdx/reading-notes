## RegExr FROM (https://regexr.com/)
Character Classes
Anchors
Escaped Characters
Groups & Lookaround
Quantifiers & Alternation

## Regex tutorial — A quick cheatsheet by examples FROM (https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285)
Regex - regular expressions (regexp): very useful for extracting info from any text searching for more than one specific search pattern like ASCII or unicode characters. 
    - Parsing/replacing strings
    - Translating data
    - Web scraping 
    - Regex is used in almost all programming languages.

**Basics**
`^The` looks for any string that starts with The.
`end$` ends with end
`^The end$` matches The end exactly
`roar` any string with the word roar in it. 

**Quantifiers**
* + ? and {} 
Checks if strings are followed by x amount of y. Ex. `abc{2}` matches a string that has ab followed by 2 c.

**OR Operator = | []**
Ex. `a(b|c)` a is followed by b or c. 

**Character classes — \d \w \s and .**
- \d - looks for single character digit
- \w - looks for a word character - alphanumeric and underscore 
- \s - looks for whitespace, tabs, and line breaks
- . - any character 

**Flags**
g: global 
m: multi-line
i: insensitive - not case sensitive (/aBc/I would match with AbC)

**Grouping, capturing ()**

**Bracket Expressions - []**
NOTE: Characters inside the brackets (incl. backslash) cannot use the "escape rule". 

**Greedy and Lazy Match**
Ex. `* + {}`

**Boundaries — \b and \B** 
Whole word search only. Ex. `\babc\b  ` matches only `abc`. `\Babc\B ` only matches if the pattern if completely surrounded by word characters a, b, or c. 

**Back-references — \1**

**Look-ahead and Look-behind — (?=) and (?<=)**
d(?=r)  - only if d if followed by r. r not included. 
(?<=r)d   - only if d is preceded by r. r not included. 
Note: Can also use `!` so it's NOT followed or preceded. 
