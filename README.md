# This project documents my learning about **Regular Expression** patterns.
## What are they useful for?
For extracting information from text such as code, log files, spreadsheets or just regular text documents.

## Everything is a character
**Everything**, information as we know that is represented by symbols is string of characters.

## Patterns to match strings
Our goal is to write patterns that **match** a **specific sequence of characters** in a text. These patterns use symbols from ASCII and unicode.

> ex:- Pattern `abc` will match strings which have `a` followed by `b` followed by `c`. Text's `abcdef`, `abcd`, `abc`, `defabc` all have the pattern of `a` followed by `b` followed by `c` in them. Therfore the pattern `abc` matches a string in the all text's `abcdef`, `abcd`, `abc`. `defabc`.

## Metacharacters
The regular expression patterns consist of ordinary characters and something called **meta characters**. It is either a single character or short sequence of characters that **represents a specific type of character**. 
- > `\d` represents any character from the list of `0 to 9`.

- > `.` represents any character along with period. So to pattern to only match a period is `\.`
> Meta characters are often preceded by a `\` in a pattern that tries to match instances of that meta  character itself.
## To match specific characters
`.` meta character will match any character in the text. **What if we want to match a specific characters?** For that, regular expressions include an **operator** which is **[character set]**.<br> This expression is a pattern which will match any **single** character specified inside the square brackets.
> `[cmf]an` is a regex pattern that will match the strings `can`, `man`, `fan`. Here, `[cmf]` will match the characters `c` or `m` or `f`.

## Internal monologue while thinking about the pattern...
'Write a pattern **for a string** whose first character is `this`, second character is `this`, third character is `this` ...'

## To exclude specific characters
To exclude specific characters to match in a string the carrot operator `^` along with the square bracket operator `[]` is used to write the pattern.
> `[^b]og` is a regex pattern that will match with all the strings whose first character is not `b`, second character is `o`, third character is `g` like `hog`, `dog`, `mog` etc, but not `bog`.

## Character ranges.
To match specific characters we use the `[]` operator and mention all those specific characeters inside the operator. But what if those specific characters are sequential like a-z, 0-9. We have to mention all the characters in the list inside the `[]` which can be very verbose.<br>
Fortunately, there exists a **shorthand** in regex pattern language which allows us to only mention the start and end of that character sequence. That **shorthand** is the `-` dash operator.
> `[0-9]` is regex pattern that will match any character from the list of 0 to 9.

> ### Multiple character ranges inside `[]` 
> We can have multiple character range exprs inside the `[]` like `[0-9A-Z]` will match strings whose 1st character can be anything from the list 0 to 9 and the 2nd character can be anything from the list A to Z.

## Character repetions.
Writing a pattern for strings that have a repeated sequence of a specific character can be verbose because of the number of repetitions, which can also vary from string to string.<br>
Regex language provides an operator to deal with this. It is the curly brackets operator `character{}` which is prefixed with any character.
> `a{3}bc` is regex pattern which will match strings that start with 3 `a`'s followed by `b` followed by `c` like `aaabc`.

> `a{3, 5}bc` is a regex pattern that will match with strings whose first 3 characters can be `a` or first 5 characters can be `a` and then followed by `b` and `c` like `aaabc` and `aaaaabc`