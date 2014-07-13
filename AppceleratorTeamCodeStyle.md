№ |Table of Contents|
--- | --- 
1.|[requireCurlyBraces](#requireCurlyBraces)|
2.|[requireSpaceAfterKeywords](#requireSpaceAfterKeywords)
3.|[requireSpaceBeforeBlockStatements](#requireSpaceBeforeBlockStatements)
4.|[requireSpacesInConditionalExpression](#requireSpacesInConditionalExpression)
5.|[disallowMultipleVarDecl](#disallowMultipleVarDecl)
6.|[requireBlocksOnNewline](#requireBlocksOnNewline)
7.|[disallowPaddingNewlinesInBlocks](#disallowPaddingNewlinesInBlocks)
8.|[disallowEmptyBlocks](#disallowEmptyBlocks)
9.|[disallowSpacesInsideObjectBrackets](#disallowSpacesInsideObjectBrackets)
10.|[disallowSpacesInsideArrayBrackets](#disallowSpacesInsideArrayBrackets)
11.|[disallowSpacesInsideParentheses](#disallowSpacesInsideParentheses)
12.|[disallowDanglingUnderscores](#disallowDanglingUnderscores)
13.|[disallowSpaceAfterObjectKeys](#disallowSpaceAfterObjectKeys)
14.|[requireCommaBeforeLineBreak](#requireCommaBeforeLineBreak)
15.|[requireOperatorBeforeLineBreak](#requireOperatorBeforeLineBreak)
16.|[disallowSpaceAfterPrefixUnaryOperators](#disallowSpaceAfterPrefixUnaryOperators)
17.|[disallowSpaceBeforePostfixUnaryOperators](#disallowSpaceBeforePostfixUnaryOperators)
18.|[requireSpaceBeforeBinaryOperators](#requireSpaceBeforeBinaryOperators)
19.|[requireSpaceAfterBinaryOperators](#requireSpaceAfterBinaryOperators)
20.|[requireCamelCaseOrUpperCaseIdentifiers](#requireCamelCaseOrUpperCaseIdentifiers)
21.|[disallowMultipleLineBreaks](#disallowMultipleLineBreaks)
22.|[validateQuoteMarks](#validateQuoteMarks)
23.|[disallowMixedSpacesAndTabs](#disallowMixedSpacesAndTabs)
24.|[disallowTrailingWhitespace](#disallowTrailingWhitespace)
25.|[disallowTrailingComma](#disallowTrailingComma)
26.|[requireLineFeedAtFileEnd](#requireLineFeedAtFileEnd)
27.|[requireDotNotation](#requireDotNotation)
28.|[disallowYodaConditions](#disallowYodaConditions)


<a name="requireCurlyBraces"/>
### 1. requireCurlyBraces

Requires curly braces after statements.

##### Valid

```js
if (x) {
    x++;
}
```

##### Invalid

```js
if (x) x++;
```
<a name="requireSpaceAfterKeywords"/>
### 2. requireSpaceAfterKeywords

Requires space after keyword.

Type: `Array`

Values: Array of quoted keywords

#### .json setup

```js
"requireSpaceAfterKeywords": [
    "if",
    "else",
    "for",
    "while",
    "do",
    "switch",
    "return",
    "try",
    "catch"
]
```

##### Valid

```js
return true;
```

##### Invalid

```js
if(x) {
    x++;
}
```

<a name="requireSpaceBeforeBlockStatements"/>
### 3. requireSpaceBeforeBlockStatements

Requires space before block statements (for loops, control structures).

Type: `Boolean`

Values: `true`

#### .json setup

```js
"requireSpaceBeforeBlockStatements": true
```

##### Valid

```js
if (cond) {
  foo();
}

for (var e in elements) {
  bar(e);
}

while (cond) {
  foo();
}
```

##### Invalid

```js
if (cond){
  foo();
}

for (var e in elements){
  bar(e);
}

while (cond){
  foo();
}
```
<a name="requireSpacesInConditionalExpression"/>
### 4. requireSpacesInConditionalExpression

Requires space before and/or after `?` or `:` in conditional expressions.

#### .json setup

```js
"requireSpacesInConditionalExpression": {
    "afterTest": true,
    "beforeConsequent": true,
    "afterConsequent": true,
    "beforeAlternate": true
}
```

##### Valid

```js
var a = b ? c : d;
```

##### Invalid

```js
var a = b? c : d;
var a = b ?c : d;
var a = b ? c: d;
var a = b ? c :d;
```
<a name="disallowMultipleVarDecl"/>
### 5. disallowMultipleVarDecl

Disallows multiple `var` declaration (except for-loop).

#### .json setup

```js
"disallowMultipleVarDecl": true
```

##### Valid

```js
var x = 1;
var y = 2;

for (var i = 0, j = arr.length; i < j; i++) {}
```

##### Invalid

```js
var x = 1,
    y = 2;
```

<a name="requireBlocksOnNewline"/>
### 6. requireBlocksOnNewline

Requires blocks to begin and end with a newline

#### .json setup

```js
"requireBlocksOnNewline": true
```

##### Valid for mode `true`

```js
if (true) {
    doSomething();
}
var abc = function() {};
```

##### Invalid

```js
if (true) {doSomething();}
```

<a name="disallowPaddingNewlinesInBlocks"/>
### 7. disallowPaddingNewlinesInBlocks

Disallows blocks from beginning and ending with 2 newlines.

#### .json setup

```js
"disallowPaddingNewlinesInBlocks": true
```

##### Valid

```js
if (true) {
    doSomething();
}
if (true) {doSomething();}
var abc = function() {};
```

##### Invalid

```js
if (true) {

    doSomething();

}
```

<a name="disallowEmptyBlocks"/>
### 8. disallowEmptyBlocks

Disallows empty blocks (except for catch blocks).

#### .json setup

```js
"disallowEmptyBlocks": true
```

##### Valid

```js
if ( a == b ) { c = d; }
try { a = b; } catch( e ){}
```

##### Invalid

```js
if ( a == b ) { } else { c = d; }
```

<a name="disallowSpacesInsideObjectBrackets"/>
### 9. disallowSpacesInsideObjectBrackets

Disallows space after opening object curly brace and before closing.

#### .json setup

```js
"disallowSpacesInsideObjectBrackets": "all"
```

##### Valid for mode `"all"`

```js
var x = {a: {b: 1}};
```

##### Invalid

```js
var x = { a: { b: 1 } };
```

<a name="disallowSpacesInsideArrayBrackets"/>
### 10. disallowSpacesInsideArrayBrackets

Disallows space after opening array square bracket and before closing.

#### .json setup

```js
"disallowSpacesInsideArrayBrackets": "all"
```

##### Valid for mode `"all"`

```js
var x = [[1]];
```

##### Invalid

```js
var x = [ [ 1 ] ];
```
<a name="disallowSpacesInsideParentheses"/>
### 11. disallowSpacesInsideParentheses

Disallows space after opening round bracket and before closing.

#### .json setup

```js
"disallowSpacesInsideParentheses": true
```

##### Valid

```js
var x = (1 + 2) * 3;
```

##### Invalid

```js
var x = ( 1 + 2 ) * 3;
```

<a name="disallowDanglingUnderscores"/>
### 12. disallowDanglingUnderscores

Disallows identifiers that start or end in `_`, except for some popular exceptions:

 - `_` (underscore.js)
 - `__filename` (node.js global)
 - `__dirname` (node.js global)

#### .json setup

```js
"disallowDanglingUnderscores": true
```

##### Valid

```js
var x = 1;
var y = _.extend;
var z = __dirname;
var w = __filename;
var x_y = 1;
```

##### Invalid

```js
var _x = 1;
var x_ = 1;
var x_y_ = 1;
```
<a name="disallowSpaceAfterObjectKeys"/>
### 13. disallowSpaceAfterObjectKeys

Disallows space after object keys.

#### .json setup

```js
"disallowSpaceAfterObjectKeys": true
```

##### Valid
```js
var x = {a: 1};
```
##### Invalid
```js
var x = {a : 1};
```

<a name="disallowCommaBeforeLineBreak"/>
### 14. requireCommaBeforeLineBreak

Requires commas as last token on a line in lists.

#### .json setup

```js
"requireCommaBeforeLineBreak": true
```

##### Valid

```js
var x = {
    one: 1,
    two: 2
};
var y = { three: 3, four: 4};
```

##### Invalid

```js
var x = {
    one: 1
    , two: 2
};
```

<a name="requireOperatorBeforeLineBreak"/>
### 15. requireOperatorBeforeLineBreak

Requires operators to appear before line breaks and not after.

#### .json setup

```js
"requireOperatorBeforeLineBreak": [
    "?",
    "=",
    "+",
    "-",
    "/",
    "*",
    "==",
    "===",
    "!=",
    "!==",
    ">",
    ">=",
    "<",
    "<="
]
```

##### Valid

```js
x = y ? 1 : 2;
x = y ?
    1 : 2;
```

##### Invalid

```js
x = y
    ? 1 : 2;
```

<a name="disallowSpaceAfterPrefixUnaryOperators"/>
### 16. disallowSpaceAfterPrefixUnaryOperators

Requires sticking unary operators to the right.

#### .json setup

```js
"disallowSpaceAfterPrefixUnaryOperators": ["++", "--", "~", "!"],
```

##### Valid

```js
x = !y; y = ++z;
```

##### Invalid

```js
x = ! y; y = ++ z;
```

<a name="disallowSpaceBeforePostfixUnaryOperators"/>
### 17. disallowSpaceBeforePostfixUnaryOperators

Requires sticking unary operators to the left.

#### .json setup

```js
"disallowSpaceBeforePostfixUnaryOperators": ["++", "--"]
```

##### Valid

```js
x = y++; y = z--;
```

##### Invalid

```js
x = y ++; y = z --;
```

<a name="requireSpaceBeforeBinaryOperators"/>
### 18. requireSpaceBeforeBinaryOperators

Disallows sticking binary operators to the left.

#### .json setup

```js
"requireSpaceBeforeBinaryOperators": [
    "=",
    ",",
    "+",
    "-",
    "/",
    "*",
    "==",
    "===",
    "!=",
    "!=="
]
```

##### Valid

```js
x !== y;
```

##### Invalid

```js
x!== y;
```

<a name="requireSpaceAfterBinaryOperators"/>
### 19. requireSpaceAfterBinaryOperators

Disallows sticking binary operators to the right.

#### .json setup

```js
"requireSpaceAfterBinaryOperators": [
    "=",
    ",",
    "+",
    "-",
    "/",
    "*",
    "==",
    "===",
    "!=",
    "!=="
]
```

##### Valid

```js
x + y;
```

##### Invalid

```js
x +y;
```

<a name="requireCamelCaseOrUpperCaseIdentifiers"/>
### 20. requireCamelCaseOrUpperCaseIdentifiers

Requires identifiers to be camelCased or UPPERCASE_WITH_UNDERSCORES

#### .json setup

```js
"requireCamelCaseOrUpperCaseIdentifiers": "ignoreProperties",
```

##### Valid

```js
var camelCase = 0;
var CamelCase = 1;
var _camelCase = 2;
var camelCase_ = 3;
var UPPER_CASE = 4;
var obj.snake_case = 5;
var camelCase = { snake_case: 6 };
```

##### Invalid

```js
var lower_case = 1;
var Mixed_case = 2;
var mixed_Case = 3;
var snake_case = { snake_case: 6 };
```

<a name="disallowMultipleLineBreaks"/>
### 21. disallowMultipleLineBreaks

Disallows multiple blank lines in a row.

#### .json setup

```js
"disallowMultipleLineBreaks": true
```

##### Valid
```js
var x = 1;

x++;
```

##### Invalid
```js
var x = 1;


x++;
```
<a name="validateQuoteMarks"/>
### 22. validateQuoteMarks

Requires all quote marks to be either the supplied value, or consistent if `true`

Type: `String` or `Object`

Values:
 - `"\""`: all strings require double quotes

#### .json setup

```js
"validateQuoteMarks": "\""
```
##### Invalid example for mode `"\"`

```js
var x = "x";
var y = 'x';
```

##### Valid example for mode `"\""`

```js
var x = "x";
```

<a name="disallowMixedSpacesAndTabs"/>
#### 23. disallowMixedSpacesAndTabs

Requires lines to not contain both spaces and tabs consecutively,
or spaces after tabs only for alignment if "smart"

#### .json setup

```js
"disallowMixedSpacesAndTabs": "smart"
```

##### Valid example for mode `"smart"`

```js
\tvar foo = "blah blah";
\t\svar foo = "blah blah";
\s\s\s\svar foo = "blah blah";
\t/**
\t\s*
\t\s*/ //a single space to align the star in a multi-line comment is allowed
```

##### Invalid example for mode `"smart"`

```js
\s\tsvar foo = "blah blah";
```

<a name="disallowTrailingWhitespace"/>
### 24. disallowTrailingWhitespace

Requires all lines to end on a non-whitespace character

#### .json setup

```js
"disallowTrailingWhitespace": true
```

##### Valid

```js
var foo = "blah blah";
```

##### Invalid

```js
var foo = "blah blah"; //<-- whitespace character here
```

<a name="disallowTrailingComma"/>
### 25. disallowTrailingComma

Disallows an extra comma following the final element of an array or object literal.

#### .json setup

```js
"disallowTrailingComma": true
```

##### Valid

```js
var foo = [1, 2, 3];
var bar = {a: "a", b: "b"}
```

##### Invalid

```js
var foo = [1, 2, 3, ];
var bar = {a: "a", b: "b", }
```

<a name="requireLineFeedAtFileEnd"/>
### 26. requireLineFeedAtFileEnd

Requires placing line feed at file end.

#### .json setup

```js
"requireLineFeedAtFileEnd": true
```

<a name="requireDotNotation"/>
### 27. requireDotNotation

Requires member expressions to use dot notation when possible

#### .json setup

```js
"requireDotNotation": true
```

##### Valid

```js
var a = b[c];
var a = b.c;
var a = b[c.d];
var a = b[1];
var a = b['while']; //reserved word
```

##### Invalid

```js
var a = b['c'];
```

<a name="disallowYodaConditions"/>
### 28. disallowYodaConditions

Requires the variable to be the left hand operator when doing a boolean comparison

#### .json setup

```js
"disallowYodaConditions": true
```

##### Valid

```js
if (a == 1) {
  return
}
```

##### Invalid

```js
if (1 == a) {
  return
}
```
