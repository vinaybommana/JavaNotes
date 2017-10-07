# Regular Expressions
* Java Regular Expressions are very similar to perl.
* Java provides `java.util.regex` package for pattern matching for regular expressions.

## Regular expression
A regular expression is a special sequence of characters that helps to match or find other
strings or set of strings, using a specialized syntax held in a pattern.

* `java.util.regex` package consists of mainly three classes:

    * **Pattern** **Class**
        - A `Pattern` object is a compiled representation of a regular expression.
        - To create a pattern, invocation of one of the `public` `static` **compile** methods
        is required, which will return a pattern object.
        - These methods accept a Regular expression as their first object.
        $~$
    * **Matcher** **Class**
        - `Matcher` Object interprets the pattern.
        - the `matcher` object is obtained by invoking the `Matcher` method 
          on the **Pattern** object.
