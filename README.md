<h1 align="center">
    Validator
</h1>

<p align="center">
     <i>A 🔋-included, supercharged & customizable,<br>string validation library for Arturo</i> 
     <br><br>
     <img src="https://img.shields.io/github/license/arturo-lang/grafito?style=for-the-badge">
    <img src="https://img.shields.io/badge/language-Arturo-orange.svg?style=for-the-badge">
</p>


--- 
 
<!--ts-->

* [What does this package do?](#what-does-this-package-do)
* [How do I use it?](#how-do-i-use-it)
* [Function Reference](#function-reference)
* [Contributing](#contributing)
* [License](#license)   

<!--te-->
 
---

### What does this package do?

This package provides a function (`valid?`) that allows to check and validate strings, based on different built-in schemes/patterns, e.g e-mails, urls, etc.

### How do I use it?

Simply `import` it and use the included `valid?` function:

```red
import "validator"!

valid?.url "https://arturo-lang.io"
; => true

valid?.email "loremIpsum@"
; => false

valid?.iban "GB82 WEST 1234 5698 7654 32"
; => true

valid?.ip "127.0.0.1"
; => true

valid?.ip.v6 "127.0.0.1"
; => false
```

And we may also check more than one strings:

```red
valid?.email ["my@email.com", "info@google.com"]
; => true
```

> [!TIP]
> Different type of checks may accept different extra params, so you'd better have a look into the reference first! 😉


### Function reference

#### `valid?`

##### Description

check if given string is valid

##### Usage

<pre>
<b>valid?</b> <ins>str</ins> <i>:string :block</i>
</pre>

##### Attributes

| Option | Related parameters | Description |
|----|----|----|
| base58 | | check base-58 encoding |
| card | | check credit card number |
| date | | test if string contains valid date |
| | .format: | specify date format (default: `'iso` or `yyyy-MM-dd`) - could also be one of `'iso8601`, `'short`, `'long` or any given string |
| email | | verify e-mail address | 
| floating | | test if string contains a parsable floating-point value |
| integer | | test if string contains a parsable integer value |
| iban | | verify IBAN (International Bank Account Number) |
| ip | | verify IP addresses |
| | .v4 | look for IPv4 addresses only |
| | .v6 | look for IPv6 addresses only |
| isbn | | verify ISBN code |
| | .10 | check for ISBN-10 codes only |
| | .13 | check for ISBN-13 codes only |
| json | | test if string contains valid JSON |
| | .strict | enforce stricter, two-way validation |
| url | | verify URL |

##### Returns

- *:logical*

### Contributing

Validator.art has been designed with flexibility and extensibility in mind.

- Have you noticed an error and want to fix sth?
- Do you want to add more tests to a given validator to make it more robust?
- Do you want to add a new one (Have a look into the [sample validator](docs/sample.art)!)

You are 100% welcome! Just make a PR and I'll be more than glad to merge it! 🚀

<hr/>

### License

MIT License

Copyright (c) 2024 Yanis Zafirópulos

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
 