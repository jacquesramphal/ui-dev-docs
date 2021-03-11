## 1. JS Primitives

### Tips
- Always hit 'shift' + 'enter' for new lines

## Javascript Data Types

### Number

- A number. Numbers don't have to have quotes around them

### String

- A sequence of text know as a string. To signify that the value is a string, you must enclose it in quote marks (double or single)

### Boolean

- A True/False value. The words TRUE or FALSE are special keywords.They don't need quotes

### JS Comparisons

### !==

Not equal value or not equal type

### ===

Equal value and equal type

### >=

Greater than or equal to

### <=

Less than or equal to

### >

Greater than

### <

Less than

# Examples
`3=3`

`VM43:1 Uncaught SyntaxError: Invalid left-hand side in assignment`

`3===3`

`true`

`'Jacques'`

`"Jacques"`

`2 - "Jacques'`

`VM119:1 Uncaught SyntaxError: Invalid or unexpected token`

`20 + 'Jacques'`

`"20Jacques"`

`20 - '10'`

`10`

`'FirstName ' + 'LastName ' + 'Age ' + 'Height'`

`"FirstName LastName Age Height"`

### Combining Strings 

**Accessing individual Characters**

`'Jacques' [0]`

`"J"`

**Is this word greater than 8?**

`'Jacques'.length>8`

`false`

`'Jacques'.length>7`

`false`

`'Jacques'.length>=7`

`true`

**Modules**

Ramphal goes into Jacques 1 time with extra characters = 0

`'Jacques'.length % 'Ramphal'.length`
`0`

Jake goes into Jacques 1 time with extra characters = 3

`'Jacques'.length % 'Jake'.length`
`3`
