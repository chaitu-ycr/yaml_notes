# yaml_notes

## Introduction

YAML (YAML Ain't Markup Language) is a human-readable data serialization format that's commonly used for configuration files and data exchange between languages with different data structures.

official YAML [site](https://yaml.org/)

Official YAML [specifications](https://yaml.org/spec/)

* revision 1.2 [link](https://yaml.org/spec/1.2/spec.html)
* revision 1.1 [link](https://yaml.org/spec/1.1/current.html)

continue reading 👉 [yaml_notes](https://chaitu-ycr.github.io/yaml_notes/)

_NOTE_

* YAML uses indentation to represent the structure of a document.
* Only spaces are allowed, tabs are not supported.
* Indentation levels define nested structures like lists and dictionaries.

## Scalars

Scalars are single, indivisible values. They can be strings, numbers, booleans, or null.

### Strings

Strings in YAML are used to represent textual data. YAML allows you to format strings in various ways to handle simple and complex text scenarios.

* Plain Strings

  ```yaml
  # Plain strings are unquoted strings. They are the simplest and most commonly used.
  name: chaitu-ycr
  description: This is a plain string
  ```

* Quoted Strings

  ```yaml
  # Use single quotes for strings that include special characters that should be taken literally.
  text: 'It''s a sunny day'  # Escapes single quote
  emoji: '😀😃😄'
  ```

  ```yaml
  # Use double quotes for strings that include special characters or need to include escape sequences
  text: "Hello, \nWorld!"  # \n creates a newline
  emoji: "😀😃😄"
  ```

* Multiline Strings 🖋️

  ```yaml
  # YAML supports multiline strings using block (|) and folded (>) styles.
  block_scalar: |
    This is a block scalar.
    It preserves line breaks.
    Even empty lines are included.

  folded_scalar: >
    This is a folded scalar.
    It folds new lines into spaces,
    creating a single flowing paragraph.
  ```

* Special Characters and Escaping 🔍

  ```yaml
  # Double-quoted strings can contain special characters and escape sequences.
  # Use backslash (`\`) to introduce escape sequences.
  special_characters: "Newline: \n, Tab: \t, Backslash: \\, Quote: \""
  ```

* Null Strings 🌀

  ```yaml
  # Null values are represented as (null) or (~).
  null_example1: null
  null_example2: ~
  ```

### Numbers 🔢

YAML supports different types of numbers, including integers, floating-point numbers, and numbers in scientific notation.

```yaml
# An integer representing age
age: 30

# A negative integer representing temperature
temperature: -5

# A float representing height in feet
height: 5.9

# Speed of light in meters per second
speed_of_light: 3.0e8

# A hexadecimal color code
color_code: 0xFF5733

# File permission notation
file_permissions: 0755

# A binary number
binary_value: 0b101010
```

### Booleans ⚖️

Booleans in YAML are used to represent true or false values. They are essential for controlling logic and conditions within your YAML files.

* True Values: `true`, `True`, `TRUE`, `yes`, `Yes`, `YES`, `on`, `On`, `ON`
* False Values: `false`, `False`, `FALSE`, `no`, `No`, `NO`, `off`, `Off`, `OFF`

```yaml
# Standard Boolean Values
is_active: true  # Basic boolean
has_license: false  # Basic boolean

# Alternative Representations
is_enabled: yes  # Alternative for true
is_disabled: no  # Alternative for false

# Switch States
light_switch: on  # Alternative for true
dark_mode: off  # Alternative for false
```

### Null

Null values in YAML represent the absence of a value. They are useful for indicating missing, undefined, or unassigned data.

```yaml
# Explicit (null)
preferred_language: null  # Language preference not set

# Tilde (~)
shipping_address: ~  # Shipping address is missing

# Empty Value: Just leave the value empty after the colon.
phone_number:  # Phone number not provided

# Empty Quotes: Using single or double quotes.
additional_info: ''  # No additional information
middle_name: ""
```

## Sequences (Lists)

Sequences are ordered collections of items. Each item is prefixed by a dash (-).

### Basic List

```yaml
examples:
  - item1
  - item2
  - item3
```

### Nested Lists

```yaml
examples:
  - first_list:
    - item1
    - item2
  - second_list:
    - item3
    - item4
```

### Mixed Types in Lists

```yaml
examples:
  - "text"
  - 42
  - true
  - null
```

## Mappings (Dictionaries)

Mappings are collections of key-value pairs.

### Basic Mapping

```yaml
example:
  key1: value1
  key2: value2
```

### Nested Mappings

```yaml
example:
  key1:
    subkey1: value1
    subkey2: value2
  key2:
    subkey1: value3
    subkey2: value4
```

### Ordered Mappings

YAML preserves the order of mappings, but it’s not strictly guaranteed by all parsers.

## Anchor and Alias

Anchors allow you to reuse a value or set of values elsewhere in the document.

* Defining Anchors (&) and Using Aliases (*)

```yaml
default: &default
  key1: value1
  key2: value2

example:
  <<: *default
  key3: value3
```

## Merging Mappings (<<)

Allows merging one mapping into another.

```yaml
defaults: &defaults
  key1: value1
  key2: value2

custom:
  <<: *defaults
  key2: new_value2
  key3: value3
```

## Complex Keys

Complex types such as sequences can be used as keys

```yaml
? [ complex, key ]
: value
```
