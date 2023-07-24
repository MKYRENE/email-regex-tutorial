# Regex Tutorial: Matching an Email Address

## Introduction

Regular expressions, or regex, are powerful tools used to define search patterns in strings. They play a crucial role in web development by enabling validation, search, and manipulation of text. In this tutorial, we will explore a specific regular expression designed to match a valid email address. We will break down each component of the regex and explain its purpose to understand how it functions.

## Summary

The regex we will be explaining is:

/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/


This regex is used to validate email addresses and ensure they adhere to the standard email format. It checks the local part, the @ symbol, and the domain of the email address. We will go through each component of the regex to understand how it contributes to the overall search pattern.

## Table of Contents

- [The Local Part](#the-local-part)
- [The @ Symbol](#the-symbol)
- [The Domain](#the-domain)
- [Conclusion](#conclusion)
- [About the Author](#about-the-author)

## Regex Components

### The Local Part

The first part of the regex is `([a-z0-9_\.-]+)`. This component is responsible for matching the local part of the email address, which comes before the @ symbol. It consists of the following elements:

- `(` and `)` indicate a capturing group, allowing us to remember the matched characters inside the parentheses.
- `[a-z0-9_\.-]` is a character set that matches any lowercase letter (a-z), digit (0-9), underscore (_), period (.), or hyphen (-).
- `+` is a quantifier that specifies one or more occurrences of the preceding character set, ensuring the local part has at least one or more valid characters.

**Example:**

- `john.doe` - Valid
- `user123` - Valid
- `jane.doe-foo` - Valid
- `joe..smith` - Invalid (double periods are not allowed)

### The @ Symbol

The next part of the regex is `@`, which simply matches the @ symbol in an email address. It acts as a separator between the local part and the domain.

**Example:**

- `john@example.com` - Valid
- `user@mail` - Valid
- `jane.doe@domain` - Valid
- `invalid.email` - Invalid (missing @ symbol)

### The Domain

The last part of the regex is `([\da-z\.-]+)\.([a-z\.]{2,6})`. This component is responsible for matching the domain part of the email address. It consists of the following elements:

- `([\da-z\.-]+)`: This is a capturing group that matches any digit (0-9), lowercase letter (a-z), period (.), or hyphen (-) occurring one or more times.
- `\.`: This matches a literal period (dot), separating the domain name from the top-level domain (TLD).
- `([a-z\.]{2,6})`: This is another capturing group that matches the TLD, consisting of lowercase letters (a-z) and periods. The {2,6} quantifier ensures that the TLD has a minimum length of 2 characters and a maximum of 6 characters.

**Example:**

- `example.com` - Valid
- `sub.domain.co` - Valid
- `user@my-site.org` - Valid
- `website.info` - Invalid (TLD must have at least two characters)

## Conclusion

In this tutorial, we explored a regular expression used to match a valid email address. Understanding regular expressions is essential for web developers, as they provide a powerful way to validate and manipulate text data. By breaking down each component of the regex, we can grasp its significance in defining a search pattern for email addresses.

## About the Author

[Michael Rodriguez](https://github.com/mkyrene)

