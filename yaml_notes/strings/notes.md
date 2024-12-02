## Strings

In YAML, strings are a fundamental data type used to represent text and character data. Here are some key points about YAML strings

### Basic Strings

Strings can be written in plain style without quotes, or enclosed in single (') or double (") quotes

```YAML
plain_string: This is a plain string
single_quoted_string: 'This is a single-quoted string'
double_quoted_string: "This is a double-quoted string"
```

### Multi-line Strings

YAML supports multi-line strings using the | (literal block) or > (folded block) indicators

#### Literal Block (|): Preserves line breaks.

```YAML
literal: |
    This is a multi-line string.
    Line breaks are preserved.

literal_keep: |+
    This is a literal block scalar.
    Newlines are preserved.

literal_strip: |-
    This is a literal block scalar.
    Newlines are preserved.
```

#### Folded Block (>): Converts line breaks to spaces.

```YAML
folded: >
    This is a multi-line string.
    Line breaks are converted to spaces.

folded_keep: >+
    This is a folded block scalar.
    Newlines are converted to spaces.

folded_strip: >-
    This is a folded block scalar.
    Newlines are converted to spaces.
```

### Special Characters

Double-quoted strings allow the use of escape sequences for special characters

```YAML
escaped_string: "This is a string with a newline character\nand a tab character\t."
```
### Explicit Type Declaration

You can explicitly declare a string type using the !!str tag

```YAML
explicit_string: !!str 2024-12-02
# This ensures that the value is interpreted as a string, even if it looks like another data type (e.g., a date) 
```

### example yaml file 👉 [link]()