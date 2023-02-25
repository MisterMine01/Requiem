# Requiem

Make better readable than regex (i esper)

The idea is to make a regular expression language that is more readable than regex. The code need only to translate the requiem code to regex.

With rules below, here is exemples:

phone number in France:

`+33\d\d\d\d\d\d\d\d\d` or `+33\d{9}`

`+33|9(digit)|`

phone number in any country:

`+\d{10}`

`+|10(digit)|`


email:

`[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}`

`|or(words, under(._%+-))||+|@|or(word, under(.-))||+|.|2-4(letter)|`

or 

`|*(or(words, under(._%+-)))|@|*(word)|.|2-4(letter)|`



## Summary

- [Requiem](#requiem)
  - [Summary](#summary)
  - [RULES](#rules)
    - [One digit from 0 to 9 (\\d)](#one-digit-from-0-to-9-d)
    - [One ASCII letter (a-z) (A-Z) (0-9) (\\w)](#one-ascii-letter-a-z-a-z-0-9-w)
    - [Whitespace character (\\s)](#whitespace-character-s)
    - [Every ASCII except 0-9 (\\D)](#every-ascii-except-0-9-d)
    - [Every not word character (a-z, A-Z, 0-9) (\\W)](#every-not-word-character-a-z-a-z-0-9-w)
    - [a non-whitespace character (\\S)](#a-non-whitespace-character-s)
    - [One or more (+)](#one-or-more-)
    - [Test exactly X time a expression E](#test-exactly-x-time-a-expression-e)
    - [Test between X and Y time a expression E](#test-between-x-and-y-time-a-expression-e)
    - [Test 0 or more time a expression E](#test-0-or-more-time-a-expression-e)
    - [Test 0 or 1 time a expression E](#test-0-or-1-time-a-expression-e)
    - [Any character except line break (.)](#any-character-except-line-break-)
    - [Special character](#special-character)
    - [X or Y (|)](#xor-y-)
    - [Capture group (parentheses)](#capture-group-parentheses)
    - [Content of group X (\\1 \\2 \\3 ...)](#content-of-group-x-1-2-3-)
    - [Non capture group (?:)](#non-capture-group-)
    - [A character in the brackets](#a-character-in-the-brackets)
    - [A letter in the range of two characters X and Y](#a-letter-in-the-range-of-two-characters-x-and-y)
    - [under with expression](#under-with-expression)
    - [A letter than is not in the brackets](#a-letter-than-is-not-in-the-brackets)
    - [A letter than is not in the range of two characters X and Y](#a-letter-than-is-not-in-the-range-of-two-characters-x-and-y)
    - [notunder with expression](#notunder-with-expression)
    - [Start of the string (^)](#start-of-the-string-)
    - [End of the string ($)](#end-of-the-string-)
    - [Start of the line (\\A)](#start-of-the-line-a)
    - [End of the line (\\Z)](#end-of-the-line-z)
    - [Start of the word (\\b)](#start-of-the-word-b)
    - [End of the string (\\b)](#end-of-the-string-b)
    - [Start of the string or line (\\G)](#start-of-the-string-or-line-g)



## RULES

launch a rule with a `|rules|` for just bar it's `||`


### One digit from 0 to 9 (\d)

`digit`

### One ASCII letter (a-z) (A-Z) (0-9) (\w)

`word`

### Whitespace character (\s)

`space`

### Every ASCII except 0-9 (\D)

`letter`

### Every not word character (a-z, A-Z, 0-9) (\W)

`nonword`

### a non-whitespace character (\S)

`nonspace`

### One or more (+)

`+`

### Test exactly X time a expression E

`X(E)`


### Test between X and Y time a expression E

`X-Y(E)`

### Test 0 or more time a expression E

`*(E)`


### Test 0 or 1 time a expression E

`?(E)`

### Any character except line break (.)

`any`

### Special character

just write it except `|` that is `||`

### X or Y (|)

`or(X, Y)`

### Capture group (parentheses)

`group(*E)`

### Content of group X (\1 \2 \3 ...)

`getgroup(X)`

### Non capture group (?:)

`nogroup(*E)`

### A character in the brackets

`under(AEIOU)`

### A letter in the range of two characters X and Y

`under(X-Y)`

### under with expression

`underExp(*E)`

### A letter than is not in the brackets

`notunder(AEIOU)`

### A letter than is not in the range of two characters X and Y

`notunder(X-Y)`

### notunder with expression

`notunderExp(*E)`

### Start of the string (^)

`start`

### End of the string ($)

`end`

### Start of the line (\A)

`startline`

### End of the line (\Z)

`endline`

### Start of the word (\b)

`startword`

### End of the string (\b)

`endword(X)`

### Not the end of the string (\B)

`notendword`

### Start of the string or line (\G)

`startstring`


If you want adding a rule, just make an issue or a pull request from a fork