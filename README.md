
# DateLoop

Executable to generate dates in bash. Useful for looping on dates.


## Usage

```Usage:
dateloop [OPTIONS] START [STOP]
Return array of dates ranging from START to STOP.

Boundaries dates are included.
Max dates looped over is 2000.
Requires GNU date. The format of START and STOP are the one supported
by its --date option. See date(1).

  -p, --plus      STOP is redefined as a new date: START +PLUS.
                  Must consist of a number and a unit.
  -f, --format    Date output format. Default to '%Y%m%d'.
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
    
dateloop "2001/01/01 06:00" "2001/01/02" -s '6 hours' \
      -f "%F %T" -d '\n'
    2001-01-01 06:00:00
    2001-01-01 12:00:00
    2001-01-01 18:00:00
    2001-01-02 00:00:00
    
for d in $(dateloop 20010101 -p '3 days'); do echo "$d"; done
```


## Installation

Simply link `dateloop` to a location in your path.
