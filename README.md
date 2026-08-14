# aniquotes

A lightweight, zero dependency Python package to generate, search, and filter **14,667** anime quotes from **3,782** characters across **1,580** anime shows.

## Installation

```bash
pip install aniquotes
```

---

## Quickstart

```python
from aniquotes import getQuote

# Get a random anime quote
print(getQuote())
# {
#   'character': 'Bear',
#   'show': '.hack//SIGN',
#   'quote': 'If you want to know the truth, you must have the courage to accept it.'
# }
```

---

## Usage Guide

### 1. Get a Random Quote `getQuote`

```python
from aniquotes import getQuote

# Random quote from the entire database
quote = getQuote()

# Filter by character name
quote = getQuote(character="Luffy")

# Filter by anime show
quote = getQuote(show="Naruto")

# Filter by text within quotes
quote = getQuote(search="courage")

# Combine multiple filters
quote = getQuote(character="Luffy", show="One Piece", search="king")
```

### 2. Retrieve Multiple Quotes `getQuotes`

```python
from aniquotes import getQuotes

# Filter by anime show
death_note_quotes = getQuotes(show="Death Note")

# Filter by character name
luffy_quotes = getQuotes(character="Luffy")

# Filter by text within quotes
dream_quotes = getQuotes(search="dream")

# Limit the number of returned results
first_10_quotes = getQuotes(limit=10)

# Combine multiple filters with a limit
results = getQuotes(character="Goku", show="Dragon Ball", search="power", limit=5)
```

### 3. List Characters & Shows

```python
from aniquotes import getCharacters, getShows, getTotalCount

# Total count of quotes in database
print(getTotalCount())

# List all 1,580 unique anime shows
shows = getShows()

# List all 3,782 unique characters
all_characters = getCharacters()

# List characters from a specific show
naruto_chars = getCharacters(show="Naruto")
```

### 4. Direct Raw Data Access

```python
from aniquotes.data import QUOTES

# Direct access to the raw list
print(len(QUOTES))
first_quote = QUOTES[0]
```

---

## License

This project is licensed under [The Unlicense](LICENSE).