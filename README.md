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

Scalars are single, indivisible values. They can be `strings`, `numbers`, `booleans`, or `null`.

### Strings (`!!str`) 📜

Strings in YAML are used to represent textual data. YAML allows you to format strings in various ways to handle simple and complex text scenarios.

* Plain Strings

  Plain strings are unquoted strings. They are the simplest and most commonly used.

  ```yaml
  name: chaitu-ycr
  description: This is a plain string
  ```

* Quoted Strings

  Use single quotes for strings that include special characters that should be taken literally.

  ```yaml
  text: 'It''s a sunny day'  # Escapes single quote
  emoji: '😀😃😄'
  ```

  Use double quotes for strings that include special characters or need to include escape sequences

  ```yaml
  #
  text: "Hello, \nWorld!"  # \n creates a newline
  emoji: "😀😃😄"
  ```

* Multiline Strings 🖋️

  YAML supports multiline strings using block (`|`) and folded (`>`) styles.

  ```yaml
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

  Double-quoted strings can contain special characters and escape sequences.

  Use backslash (`\`) to introduce escape sequences.

  ```yaml
  special_characters: "Newline: \n, Tab: \t, Backslash: \\, Quote: \""
  ```

* Null Strings 🌀

  Null values are represented as (`null`) or `(~)`.

  ```yaml
  null_example1: null
  null_example2: ~
  ```

### Numbers (`!!int`, `!!float`) 🔢

YAML supports different types of numbers, including integers, floating-point numbers, and numbers in scientific notation.

* example

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

### Booleans (`!!bool`) ⚖️

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

### Null (`!!null`) 🌀

Null values in YAML represent the absence of a value. They are useful for indicating missing, undefined, or unassigned data.

* example

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

## Sequences (Lists) 📋

YAML sequences (also known as lists) are ordered collections of values. They are used to represent data structures like arrays and lists in a simple and readable format.

* Basic List

  Sequences are defined using a dash (`-`) followed by a space for each item in the list.

  ```yaml
  fruits:
    - 🍎 Apple
    - 🍌 Banana
    - 🍒 Cherry
  ```

  * Each item in the list starts with a `-`
  * Items are indented for clarity (optional but recommended).

* Nested Lists

  You can nest lists within lists to represent more complex data structures.

  ```yaml
  favorites:
    - colors:
        - 🔴 Red
        - 🟢 Green
        - 🔵 Blue
    - numbers:
        - 1️⃣ One
        - 2️⃣ Two
        - 3️⃣ Three
  ```

  * The favorites key contains a list of nested lists (colors and numbers).

* Lists of Dictionaries

  Lists can contain dictionaries (mappings), which is useful for representing structured data.

  ```yml
  employees:
    - name: chaitu-ycr
      age: 30
      department: 🛠️ Engineering
    - name: ycr dummy
      age: 25
      department: 📈 Marketing
  ```

  * Each item in the employees list is a dictionary with name, age, and department keys.

* Mixed Lists

  Lists can contain different types of items, such as strings, numbers, and booleans.

  ```yaml
  mixed_list:
    - "String" 📜
    - 42 🔢
    - true ⚖️
    - null 🌀
  ```

  * The mixed_list contains a string, an integer, a boolean, and a null value.

* Lists with Multiline Strings

  Lists can include multiline strings using block or folded scalars.

  ```yml
  notes:
    - >
      This is a folded string 📄
      in a list item.
    - |
      This is a block string 🖋️
      in a list item.
  ```

  * The first item uses a folded scalar (`>`).
  * The second item uses a block scalar (`|`).

* Combining Sequences and Mappings

  You can combine sequences and mappings to create complex structures.

  ```yml
  complex_structure:
    - name: "Item 1" 📦
      attributes:
        - attribute1: value1
        - attribute2: value2
    - name: "Item 2" 📦
      attributes:
        - attribute1: value3
        - attribute2: value4
  ```

  * Each item in complex_structure is a dictionary with a nested list of dictionaries (attributes).

## Mappings (Dictionaries) 📑

Mappings (also known as dictionaries or hash maps) in YAML are collections of key-value pairs. They are essential for representing structured data.

* Basic Mappings

  A basic mapping consists of key-value pairs separated by a colon and space.

  ```yaml
  person:
    name: chaitu-ycr
    age: 30
    city: chennai 🏙️
  ```

  * person is a key that maps to another mapping.
  * Inside the person mapping, there are keys (name, age, city) with their respective values.

* Nested Mappings

  Mappings can contain other mappings, creating a nested structure.

  ```yaml
  company:
    name: ycr Corp
    location:
      city: chennai 🏙️
      state: Tamil Nadu 🛕
    employees:
      - name: chaitu-ycr
        role: Developer 👩‍💻
      - name: ycr dummy
        role: Designer 🎨
  ```

  * company is a mapping with nested mappings for location and employees.
  * employees is a list of mappings, each representing an employee.

* Inline Mappings

  For simple structures, mappings can be written in a single line using curly braces `{}`.

  ```yml
  address: {street: 123 Main St, city: chennai, zip: 12345}
  ```

  * Inline mapping is a concise way to represent simple key-value pairs.

* Complex Keys

  YAML allows the use of complex types, such as sequences or mappings, as keys. These are enclosed in `?` and `:`.

  ```yml
  ? [first, second]
  : "Tuple as a key"
  ```

  * The key [first, second] is a sequence used as a key for the value "Tuple as a key".

* Combining Mappings and Sequences

  You can combine mappings and sequences to create complex data structures.

  ```yml
  project:
    name: Build Website
    tasks:
      - title: Design Layout 🎨
        status: Completed ✅
      - title: Implement Backend 🖥️
        status: In Progress 🔄
      - title: Test Functionality 🧪
        status: Pending ⏳
  ```

  * tasks is a list of mappings, each representing a task with title and status.

* Anchors and Aliases

  Anchors (`&`) and aliases (`*`) allow you to reuse values within a YAML document.

  ```yaml
  defaults: &defaults
    country: INDIA in
    currency: RUPEE 💵

  location1:
    <<: *defaults
    city: chennai 🏙️

  location2:
    <<: *defaults
    city: Pondicherry 🌴
  ```

  * defaults is an anchor that can be reused in other mappings using `<<:` and `*`

## Syntax and Structure 🧩

YAML (YAML Ain't Markup Language) is designed to be a human-readable data serialization format. Its syntax and structure are simple, making it easy to write and read.

* Indentation and Whitespace 📏

  Spaces Only: YAML uses spaces for indentation, not tabs. Consistent indentation is crucial.

  Levels of Indentation: Indentation levels define the hierarchy and structure of the document.

  ```yml
  key1: value1
  key2:
    nestedKey1: nestedValue1
    nestedKey2: nestedValue2
    ```

  * `key2` contains a nested mapping, which is indented.

* Comments 💬

  Single-Line Comments: Start with `#`. Used to add notes or explanations.

  ```yml
  # This is a comment
  name: chaitu-ycr  # Inline comment
  ```

* Scalars 📜
  * Basic Values: Strings, numbers, booleans, and nulls.
  * Strings
    * Plain: `name: chaitu-ycr`
    * Single-quoted: `name: 'chaitu-ycr'`
    * Double-quoted: `name: "chaitu-ycr"`
    * Multiline
      * Block Scalar (`|`): Preserves line breaks.
      * Folded Scalar (`>`): Folds line breaks into spaces.
    * In YAML, `>+`, `>-`, `|+`, and `|-` are used to control the formatting and handling of multiline strings, which are known as block scalars.

  ```yml
  block: |
    This is a literal scalar.
    Line breaks will be preserved.
    Exactly as written.

  block_keep: |+
    This is a literal scalar.
    Line breaks will be preserved.
    Exactly as written.

  block_strip: |-
    This is a literal scalar.
    Line breaks will be preserved.
    Exactly as written.

  folded: >
    This is a folded scalar.
    New lines will be folded into spaces
    when rendered.

  folded_keep: >+
    This is a folded scalar.
    New lines will be folded into spaces.

  folded_strip: >-
    This is a folded scalar.
    New lines will be folded into spaces.
  ```

* Lists (Sequences) 📋

  * Dash and Space: Use `-` followed by a space for each item.

  ```yml
  fruits:
    - 🍎 Apple
    - 🍌 Banana
    - 🍒 Cherry
  ```

  * Nested Lists: Lists can contain other lists or mappings.

  ```yml
  favorites:
    - colors:
        - 🔴 Red
        - 🟢 Green
        - 🔵 Blue
    - numbers:
        - 1️⃣ One
        - 2️⃣ Two
        - 3️⃣ Three
  ```

* Mappings (Dictionaries) 📑

  * Key-Value Pairs: Separate keys and values with a colon and space.

  ```yml
  person:
    name: chaitu-ycr
    age: 30
    city: chennai 🏙️
  ```

  * Nested Mappings: Mappings can contain other mappings.

  ```yml
  company:
    name: ycr TechCorp
    location:
      city: chennai 🏙️
      state: Tamil Nadu 🛕
  ```

* Inline Collections 📖

  * Inline Lists and Mappings: Use square brackets for lists and curly braces for mappings.

  ```yml
  inline_list: [🍎 Apple, 🍌 Banana, 🍒 Cherry]
  inline_mapping: {name: chaitu-ycr, age: 30, city: chennai 🏙️}
  ```

* Anchors and Aliases 🔗

  * Reuse Values: Use anchors (`&`) to define reusable content and aliases (`*`) to reference it.

  ```yml
  defaults: &defaults
    country: INDIA in
    currency: RUPEE 💵

  location1:
    <<: *defaults
    city: chennai 🏙️

  location2:
    <<: *defaults
      city: Pondicherry 🌴
    ```

  * `defaults` anchor is reused in `location1` and `location2` with `<<:` `*defaults`.

* Complex Keys 🧩

  * Use Complex Types: Sequences or mappings can be used as keys by enclosing them in `?` and `:`.

  ```yml
  ? [first, second]
  : "Tuple as a key"
  ```

* Multi-Document Files 📂

  * Separate Documents: Use `---` to separate multiple documents within a single YAML file.

  ```yml
  ---
  document1:
    key1: value1
  ---
  document2:
    key2: value2
  ```

## More

* Date and Time

  * example

  ```YAML
  # YAML allows you to represent dates in a standard format, typically following the ISO 8601 standard (YYYY-MM-DD).
  birth_date: 1990-12-31

  # Times can also be represented using the ISO 8601 standard (HH:MM:SS).
  meeting_time: 14:30:00

  # YAML supports full timestamps, combining date and time.
  event_timestamp: 2023-04-06T14:30:00Z

  # Including a time zone in the timestamp ensures clarity across different regions.
  local_timestamp: 2023-04-06T14:30:00+05:30

  # Specify a range of dates or times using a custom format.
  date_range: "2023-04-01 to 2023-04-07"
  time_range: "14:30:00 to 15:30:00"
  ```

* Custom Data Types 🛠️

  You can define custom data types using tags.

  ```yml
  !color
  name: Blue
  code: "#0000FF"
  ```

  * The `!color` tag is a custom type indicating that this mapping represents a color with a name and code.

* Python Program to Read a YAML File 🐍📄

  ```cmd
  pip install pyyaml
  ```

  * Create a YAML file (example.yaml)

  ```yml
  # example.yaml
  name: chaitu-ycr
  age: 30
  address:
    street: 123 Main St
    city: chennai
    zip: 12345
  hobbies:
    - Reading
    - Hiking
    - Coding
  ```

  * Python Script to read the YAML file

  ```python
  import yaml

  # Function to read a YAML file
  def read_yaml(file_path):
      with open(file_path, 'r') as file:
          data = yaml.safe_load(file)
      return data

  # Path to the YAML file
  yaml_file = 'example.yaml'

  # Reading the YAML file
  data = read_yaml(yaml_file)

  # Printing the data
  print(data)
  ```

  * python output

  ```python
  {
    'name': 'chaitu-ycr',
    'age': 30,
    'address': {
        'street': '123 Main St',
        'city': 'chennai',
        'zip': 12345
    },
    'hobbies': ['Reading', 'Hiking', 'Coding']
  }
  ```

* Python Program to Create a YAML File 🐍📄

  * Python Script to create and write to a YAML file

  ```python
  import yaml

  # Sample data to be written to the YAML file
  data = {
      'name': 'chaitu-ycr',
      'age': 30,
      'address': {
          'street': '123 Main St',
          'city': 'chennai',
          'zip': 12345
      },
      'hobbies': ['Reading', 'Hiking', 'Coding']
  }

  # Function to write data to a YAML file
  def write_yaml(file_path, data):
      with open(file_path, 'w') as file:
          yaml.dump(data, file, default_flow_style=False)

  # Path to the YAML file
  yaml_file = 'output.yaml'

  # Writing the data to the YAML file
  write_yaml(yaml_file, data)

  print(f"Data written to {yaml_file}")
  ```

  * The content of the output.yaml file will be

  ```yaml
  name: chaitu-ycr
  age: 30
  address:
    street: 123 Main St
    city: chennai
    zip: 12345
  hobbies:
  - Reading
  - Hiking
  - Coding
  ```
