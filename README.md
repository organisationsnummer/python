# organisationsnummer [![Build Status](https://github.com/organisationsnummer/python/actions/workflows/python.yml/badge.svg)](https://github.com/organisationsnummer/python/actions)

Validate Swedish organization numbers. Follows version 1.1 of the [specification](https://github.com/organisationsnummer/meta#package-specification-v11).

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
- The number must be passed as a string.

### Validation

```python
from organisationsnummer import organisationsnummer

organisationsnummer.valid("202100-5489")
# => True

organisationsnummer.valid("2021005489")
# => True

organisationsnummer.valid("202100-5480")
# => False
```

### Format

```python
from organisationsnummer import organisationsnummer

# Short format
on = organisationsnummer.Organisationsnummer("202100-5489")
on.format()
# => '2021005489'

# Long format
on = organisationsnummer.Organisationsnummer("2021005489")
on.format(True)
# => '202100-5489'
```

### Type and VAT number

```python
from organisationsnummer import organisationsnummer

on = organisationsnummer.parse("202100-5489")
on.type()
# => 'Stat, landsting, kommun eller församling'

on.vat_number()
# => 'SE202100548901'
```

### Invalid numbers

```python
from organisationsnummer import organisationsnummer

organisationsnummer.parse("202100-5480")
# => raises OrganisationsnummerInvalidException
```

See [organisationsnummer/tests/test_organisationsnummer.py](organisationsnummer/tests/test_organisationsnummer.py) for more examples.

## In memoriam

Fredrik "Frozzare" Forsmo (1991-2026) was the initiator, co-founder and a core contributor of the organisationsnummer project. This library carries his work. He is missed.

## License

MIT
