# Learn About Regex! 

This readme is a tutorial for character sequences in Regex code, specifically referencing to matching a Hex Value. 
## Summary

This tutorial will go over the differenct character sequences of matching a Hex Value regex code. I will be breaking down the difference components of a regular expression that is used to match Hex Values, which are usually used for color using the hexadecimal color code format. 

There are two formats of a hex color code: a standard hex triplet and a shorthand hex format, both starting with a "#" . For example, hex triplet can be used to represent colors on a web page.

Below, is a detailed explanation and break down of the hex components. 

* /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

&nbsp;


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

&nbsp;


# Regex Components


&nbsp;

## Anchors

The first thing that is part of a regular expression Regex are the anchors, which are used at the start and end of a string or expression. 

* <mark> /^ </mark> : This matches the beginning of the string or a line if the multiline flag (m) is enabled. This also matches a position instead of a character.
* <mark> $/ </mark> : This matches the end of a string or the end of a line if the multiline flag (m) is enabled. This also matces a position instead of a character


&nbsp;

## Quantifiers

Next, quantifiers tell us or specify how many characters are to be expected, or how many characters, gropus, or character classes must be present iin the input for a match to be found. By default, quantifiers are greedy and will match as many characters as possible. 

* <mark>?</mark> : Indicates the expresseion to match 0 or 1 time. making it optional since it makes the preceding quanitifier lazy. Since there are two types of formats, the or operater will be used to specify which format we will be using. 
* <mark>+</mark> : Matches 1 or more of the preceding token.
* <mark>*</mark> : Matches 0 or more of the preceding token.
* In the Hex Value regular expression, <mark>{6}</mark> (Hex Triple Format), tells us that the length of this component before these quantifiers should be 6.
* In the Hex Value regular expression, <mark>{3}</mark> (Shorthand Hex Format), tells us that th eelngth of the component of these quantifiers should be 3. Which means that the length of these quantifiers should be 6 and 3 for {6} and {3}.

* Triplet formats for Hex include but are not limited to: #000000, #FFFFFF, #0099CC

&nbsp;

## OR Operator

The OR Operator, "<mark> | </mark>" in this case, is an "or" operator within a regular expression used to specify which components of the code we are separating. In this Hex value, ([a-f0-9]{6}) is separated from [a-f0-9]{3} in <mark>([a-f0-9]{6} <strong>|</strong> [a-f0-9]{3})</mark>. 

The OR Operater matches the expression before or after the | , effectively action like a boolean. It can operate within a group or a whole expression. The patterns are tested in order and like in Java, it will match either sets of characters.

&nbsp;

## Character Classes

Now, we will be learning about character classes, which are also components of our regular expression and tell us what type of characters to expect. Here, our regular expression character classes are the highlighted section of the code:  /^#?( <mark>[a-f0-9]</mark> {6}| <mark>[a-f0-9]</mark> {3})$/ . Our character classes are within the brackets and there are two of them, both of them searching for for the same values. Below breaks down the different character classes: 

* <mark>[ABC]</mark> : character inside brackets will match any character in the set
* <mark>[^ABC]</mark> : the carat means that it will match any character that is NOT in the set
* <mark>a - f</mark> : searches for letters "a - f" ; <mark>\p</mark> : matches a character indicated in the unicode category
* <mark>0 - 9</mark> : searches for digits "0 - 9" ; <mark>\d</mark> : matches any digit character.
* <mark>[A-Z]</mark> : the dash in this case creates a range from which you can select from. In this case, you can select any capital letter from A through Z
* <mark> <strong>.</strong> </mark> : A wildcard that will match any characters expect linebreaks, accepting any input.

&nbsp;

<!-- ### Flags

&nbsp;

### Grouping and Capturing

&nbsp; -->

## Bracket Expressions

Bracket expressions, enclosed in parenthesis to define our bracket expressions in this case, is a regular expression that signifies the beginning of a character class or quantifier statement. It matches a single character or collating element. If the initial character is a circumflex "^", then this bracket expression is complemented. 

* /^#? <mark>([a-f0-9]</mark> {6}|[a-f0-9]</mark> {3})</mark> $/ 

&nbsp;

## Greedy and Lazy Match

Finally, let's discuss greedy and lazy matches. 

* Greedy: a greedy component of an expressions matches the longest string possible. The greedy quantifier tells the engine to match as many quantified tokens or subpatters as possible, thus coining the term "greedy"
* Lazy: a lazy component of an expression matches the shortest possible string. This quantifier tells the engine to match as few of the quantified tokens as possible. 

For example, in our Hex value, adding a "?" next to a component makes a regular quantifier lazy, which causes the regular expression engine to match as few of the instances as possible in /^#<mark>?</mark>

* /^<mark>#?</mark> ([a-f0-9] {6}|[a-f0-9] {3}) $/ 

&nbsp;


## Author

Winter Kanda 

Please feel free to contact me with any additional questions: 
* GITHUB: https://www.github.com/winterkanda
* EMAIL: <mailto: kirankanda06@gmail.com>
### @2021 Winter

&nbsp;
