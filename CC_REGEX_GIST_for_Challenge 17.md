# Title (replace with your title)

Challenge 17 is for us to provide insight into regular expressions (regex). Regular expressions are most often used to creating defined formats that text should follow 
or to validate that text provided matches a regular set of parameters that have been setout. One common place people see this is in the checkout process for a website.
Email pattern validation often used, as is credit card pattern validation, even before you are allowed to confirm the purchase and try to run the card, phone number snd account number
validation are also very common. 

## Summary

Today I will be providing a summary of credit card regex. Long before I was interested in coding I had noticed something about the credit card validation used for e-commerce.
I found it interesting that the checkout page could tell what type of card I was trying to pay with before I had entered a fully valid card number. I will provide a breakdown and the CC regex along the lines laid out in the TOC below. 

^(?:4\d{3}|5[1-5]\d{2}|6011|65\d{2}|3(?:0[0-5]|[68]\d)\d{1}|3[47]\d{2})-?\d{4}-?\d{4}-?\d{4}|3[47]\d{2}[\s-]?\d{6}[\s-]?\d{5}$

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

### Anchors
The Credit Card regex has two anchors
  1. ^ inidicates the beginning of the string.
  2. $ indicates the end of the string.

### Quantifiers
Quantifiers provide specificty around the number of times a character can be used. 

    The ? which is the third character in our expression tells us that what is to follow should occur 0 or 1 times. 

    The {3} is a quantifier that means the what proceeds it should occur 3 times

### Grouping Constructs

The Credit Card Rexex uses () and (?) for grouping

() - captures pieces in the expression together, like the first couple of digits to find out what brand the credit card is, which will allow the company to send one request, I think
it would be a get request to confirm the card can hande the transation. 

(?) This allows for the content inside of this part of the expression to be checked against the regex but not captured for further use. This def. helps in reducing the volume of data 
that needs to be secured and then unsecured to be read. For a CC regex the fact that we can use () above allows for the ? to help with efficiency the server knows where to send the info.

### Bracket Expressions

[] - these allow for a match of only what is in the brackets. For example, in the following code snippet 3[47]\d{2} the second character must be a 4 or 7, This is the AMEX identifier. 

### Character Classes

character classes are a bit limited in a Credit Card regex as it only has numbers. which is \d 

While not used it the expression above \b or \s could be used to help identify spaces in a provided CC number. 

### The OR Operator

| is used a number of times in the CC regex validation. There are 7 different options to begin a credit card. 

### Flags

There aren't any flags in this expression. Looks like flags are most often used to increase the likelihood of match, not somthing we want to do with CC validation. 

### Character Escapes

There are no character escapes used in a CC regex. Character Escapes are for the literal use of special characters. 

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
