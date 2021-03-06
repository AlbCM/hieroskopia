# Hieroskopia
[![codecov](https://codecov.io/gh/simetrikinc/hieroskopia/branch/master/graph/badge.svg)](https://codecov.io/gh/simetrikinc/hieroskopia)


The hiereskopia package its a library to infer properties 
from dates and numeric data types like formats or separators from samples through regular patterns 
in a pandas series.

## Support 
### Date-times:
- Support to dates and datetime format
- This library receive a series as input and try to return
 a dictionary with the format found in the series Based on the 1989 C 
 Standard date time  format code

### Numeric:
- This library receive a series as input and try to return
 a dictionary with the three digit and decimal character separator

## Usage
Usage doc based on a similar library called `dateinfer` from `@jeffreystarr`

````Python
>>> import hieroskopia
>>> hierokopia.infer_datetime(['Mon Jan 13 09:52:52 MST 2014', 'Tue Jan 21 15:30:00 EST 2014'])
>>> {'format': '%a %b %d %H:%M:%S %Z %Y'}
````

The above method works with a best guess approach to detect a format in a series and try 
to return a `datetime.strftime`/`strptime` format that will cover or parse the majority
of the samples.

````Python
>>> import hieroskopia
>>> hierokopia.infer_number(['300.231,3', '200,3'])
>>> {'three_digit_separator': '.', 'decimal_separator': ',' }
````

The above method will try to detect and return certain properties in a series
like `three_digit_separator` or `deciamal_separator` character that will cover 
the majority of the samples.


## To do:
- Specify another output standard format to support java date format, snowflake date characters definition etc.
- Feed more regular expressions
- Develop multiple algorithms to get a better precision.
