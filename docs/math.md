##map()
_**Description**_  
Re-maps a number from one range to another.  

_**Syntax**_  
map (value, fromLow, fromHigh, toLow, toHigh)

_**Parameters**_  
- value: the number to map (long);  
- fromLow: the lower bound of the value's current range (long);  
- fromHigh: the upper bound of the value's current range (long);  
- toLow: the lower bound of the value's target range (long);  
- toHigh: the upper bound of the value's target range (long).

_**Returns**_  
the mapped value (long)

_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

val = analogRead(0)				# reads an analog value 0-1023
val = map(val, 0, 1023, 0, 255) # maps the value to an interval 0-255
analogWrite(9, val)				# writes the value on a PWM pin
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); //imports wyliodrin module

var val = wyliodrin.analogRead(0);			   // reads an analog value 0-1023
val = wyliodrin.map(val, 0, 1023, 0, 255); 	   // maps the value to an interval 0-255
wyliodrin.analogWrite(9, val);				   // writes the value on a PWM pin
```

C/C++:
```
#include <Wyliodrin.h>		   //imports wyliodrin library

int main()
{
	int val;
	val = analogRead(0);			   // reads an analog value 0-1023
	val = map(val, 0, 1023, 0, 255);   // maps the value to an interval 0-255
	analogWrite(9, val);			   // writes the value on a PWM pin
	return 0;
}
```
