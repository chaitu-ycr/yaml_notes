## Datatypes

### Scalars

These are single values. Scalars represent the simplest form of data.

```YAML
scalars:
    - string        # !!str
    - integer       # !!int
    - float         # !!float
    - boolean       # !!bool
    - date_time     # !!timestamp
    - null_value    # !!null
    - binary_value  # !!binary
```

### Sequences

These are ordered lists of items, similar to arrays or lists in other programming languages.

#### Lists

A list in YAML is an ordered collection of items. Each item in a list starts with a hyphen (-) followed by a space.

```YAML
fruits:
    - mango 🥭
    - green apple 🍏
    - banana 🍌

# single line representation
list_in_oneline: [🥭, 🍏, 🍌]
```

#### Sets

A set in YAML is an unordered collection of unique items. Sets are represented as mappings where each key is associated with a null value.

```YAML
colours: !!set
    ? red 🔴
    ? green 🟢
    ? blue 🔵

# single line representation
set_in_oneline: !!set {🔴, 🟢, 🔵}
```

### Mappings

These are collections of key-value pairs, similar to dictionaries or hash maps. Keys and values are separated by a colon and a space.

```YAML
person:
    name: chaitu-ycr
    age: 30
    is_professional: true

# single line representation
mappings_in_oneline: {name: chaitu-ycr, age: 30, is_professional: true}
```

### example yaml file 👉 [link](yaml_notes/data_types/data.yaml)
