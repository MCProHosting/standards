# Javascript Conventions

MCPH follows a modified version of the jQuery Core Style Guide. It is recommended to use [jscs](https://github.com/jscs-dev/node-jscs) to verify formatting, using the following `.jscrsc` file:

```json
{
    "requireCurlyBraces": [
        "if",
        "else",
        "for",
        "while",
        "do",
        "try",
        "catch"
    ],
    "requireOperatorBeforeLineBreak": true,
    "requireParenthesesAroundIIFE": true,
    "requireCommaBeforeLineBreak": true,
    "requireCamelCaseOrUpperCaseIdentifiers": true,
    "requireDotNotation": true,
    "maximumLineLength": {
        "value": 120,
        "tabSize": 4,
        "allowUrlComments": true,
        "allowRegex": true
    },

    "disallowMixedSpacesAndTabs": "smart",
    "disallowTrailingWhitespace": true,
    "disallowMultipleLineStrings": true,
    "disallowTrailingComma": true,


    "requireSpacesInFunctionExpression": {
        "beforeOpeningCurlyBrace": true
    },
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
    ],
    "requireSpacesInConditionalExpression": true,
    "requireSpaceAfterBinaryOperators": true,
    "requireLineFeedAtFileEnd": true,
    "requireSpaceBeforeBinaryOperators": [
        "=", "+=", "-=", "*=", "/=", "%=", "<<=", ">>=", ">>>=",
        "&=", "|=", "^=", "+=",

        "+", "-", "*", "/", "%", "<<", ">>", ">>>", "&",
        "|", "^", "&&", "||", "===", "==", ">=",
        "<=", "<", ">", "!=", "!=="
    ],
    "requireSpacesInAnonymousFunctionExpression": {
        "beforeOpeningCurlyBrace": true,
        "beforeOpeningRoundBrace": true
    },
    "requireSpacesInNamedFunctionExpression": {
        "beforeOpeningCurlyBrace": true,
        "beforeOpeningRoundBrace": true
    },
    "validateLineBreaks": "LF",

    "disallowKeywords": [ "with" ],
    "disallowKeywordsOnNewLine": [ "else" ],
    "disallowSpaceAfterObjectKeys": true,
    "disallowSpaceAfterPrefixUnaryOperators": true,
    "disallowSpaceBeforePostfixUnaryOperators": true,
    "disallowSpaceBeforeBinaryOperators": [ ",", ":" ],

    "excludeFiles": [
      "spec",
      "node_modules",
      "assets/js/lib",
      "api/responses"
    ]
}
```

### Angular

The repository [johnpapa/angularjs-styleguide](https://github.com/johnpapa/angularjs-styleguide) is an excellent style guide for Angular applications, and is certainly worth following.