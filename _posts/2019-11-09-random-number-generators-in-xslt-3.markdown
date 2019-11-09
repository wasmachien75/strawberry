---
layout: post
title:  "Random number generators in XSLT 3.0"
date:   2019-11-09 18:08:00 +0100
tags: [xslt3, xslt, xpath]
---
XPath 3.0 introduced a function `random-number-generator()` that allows generating random numbers. This makes it possible to easily generate dummy data or select a random element from a list, to name a few examples.

The function can optionally be called with a seed parameter.

As can be seen from its name, this function does not return a random number. Instead, a map is returned with 3 entries:

* number -> holds an `xs:double` between 0 and 1.
* next() -> function which returns a new random number generator.
* permute() -> function which returns a random permutation of the sequence which is passed as its parameter.

A simple example using XSLT 3.0:

```xml
<xsl:value-of select="random-number-generator()?number"/>
<!--0.14285147490078087>
```

Note the use of the look-up operator `?`, which provides a concise way of accessing a map entry.

Let's use this to create a function that generates a random string.

First, we create a helper function that takes an integer to define the lengh of the string, and a random number generator.

```xml
<xsl:function name="f:_random-string-with-generator">
  <xsl:param name="rng"/>
  <xsl:param name="length"/>
  <xsl:variable name="random-number" select="($rng?number * 26 + 97) => xs:integer()"/>
  <xsl:value-of select="codepoints-to-string($random-number)"/>
  <xsl:if test="$length > 0">
    <xsl:value-of select="f:_random-string-with-generator($rng?next(), $length - 1)"/>
  </xsl:if>
</xsl:function>
```

It creates a random number by accessing the `number` property of the random number generator, which is then multiplied by 26 and added to 97. This way, we receive a number between 97 and 122, which is the Unicode codepoint range of the basic lowercase letters in the Latin alphabet (a-z). This number then gets piped (using the pipe operator `=>`) to the xs:integer function, which transforms it from a double into an integer. This is necessary for the following line, in which the number is translated into its corresponding character. Finally, we use recursion to call the function itself until the number of necessary characters is met.

We can now write our main function, which only takes a length parameter, and returns the concatenated string.

```xml
<xsl:function name="f:random-string" as="xs:string">
  <xsl:param name="length" as="xs:integer"/>
  <xsl:variable name="rng" select="random-number-generator()"/>
  <xsl:variable name="seq">
    <xsl:value-of select="f:_random-string-with-generator($rng, $length)"/>
  </xsl:variable>
  <xsl:value-of select="string-join($seq)"/>
</xsl:function>
```

We can then easily call the function as follows:

```xml
<xsl:template name="xsl:initial-template">
  <person>
    <name>
      <xsl:value-of select="f:random-string(10)"/>
    </name>
  </person>
</xsl:template>
```

Which results in:

```xml
<person>
   <name>sdxynrkhqrg</name>
</person>
```

Another way in which the random number generator function can help is by letting us pick a random element from any kind of sequence.

```xml
<xsl:function name="f:random-element">
  <xsl:param name="sequence" as="item()+"/>
  <xsl:variable name="index" select="(random-number-generator()?number * count($sequence)) => ceiling()"/>
  <xsl:value-of select="$sequence[$index]"/>
</xsl:function>
```

We get a random number, multiply it by the number of items in the sequence and round it up (remember that in XPath, sequences start from index 1), then use it as the position selector of the sequence.

Note that in Saxon, multiple `random-number-generator()` calls will always return the same result — presumably Saxon uses the current datetime as the initial seed.

The full specification can be read in the [XPath and XQuery Functions and Operators Specification](https://www.w3.org/TR/xpath-functions-31/#func-random-number-generator).