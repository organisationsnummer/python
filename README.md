# organisationsnummer [![Build Status](https://github.com/organisationsnummer/python/workflows/test/badge.svg)](https://github.com/organisationsnummer/python/actions)

Validate Swedish personal identity numbers. Version 3+ only supports Python 3.

## Installation

```
pip install organisationsnummer
```

or

```
pip3 install organisationsnummer
```

## Examples

- All examples that uses `organisationsnummer.Organisationsnummer([params])`, can be replaced with `organisationsnummer.parse([params])`.

### Validation

```python
from organisationsnummer import organisationsnummer

organisationsnummer.valid("8507099805")
# => True

organisationsnummer.valid("198507099805")
# => True
```

### Format

```python
from organisationsnummer import organisationsnummer

# Short format
pn = organisationsnummer.Organisationsnummer(8507099805)
pn.format()
# => '8507099805'

# Long format
pn = organisationsnummer.Organisationsnummer('8507099805')
pn.format(True)
# => '850709-9805'
```

See [organisationsnummer/tests/test_organisationsnummer.py](organisationsnummer/tests/test_organisationsnummer.py) for more examples.

## License

MIT
