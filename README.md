
# DateLoop

Little script to loop between dates in bash.


## Usage

```Usage:
dateloop [OPTIONS] START [STOP]
Return array of dates ranging from START to STOP.

Boundaries dates are included.
Max dates looped over is 2000.
Requires GNU date.

  -p, --plus      STOP is redefined as a new date: START +PLUS.
                  Must consist of a number and a unit.
  -f, --format    Date format. Default to '%Y%m%d'.
  -s, --step      Step between date. Default to '1 day'.
  -d, --delimiter Delimiter between dates in output.
                  Default to a single space.
  -h, --help      Display this help and exit

```
## Examples

``` sh
dateloop 20010101 20010105
    20010101 20010102 20010103 20010104 20010105

dateloop -p '4 days' 2001-01-01
    20010101 20010102 20010103 20010104 20010105

dateloop 20010227 20010301 -f %Y-%m-%d
    2001-02-27 2001-02-28 2001-03-01
    
dateloop "20010101 06:00" "20010102" -s '6 hours' \
      -f "%F %T" -d '\n'
    2001-01-01 06:00:00
    2001-01-01 12:00:00
    2001-01-01 18:00:00
    2001-01-02 00:00:00
```


## Installation

Just link `dateloop` to a location in your path.
