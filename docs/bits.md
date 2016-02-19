##highByte()
_**Description**_  
Extracts the high-order (leftmost) byte of a word (or the second lowest byte of a larger data type).

_**Syntax**_  
highByte (x)

_**Parameters**_  
- x: any value (unsigned int).  

_**Returns**_  
the byte (uint8_t)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

val = highByte (1500)		# gets the high byte of 1500 and stores it
print val					# prints the value on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	//imports wyliodrin module

var val = highByte (1500);				// gets the high byte of 1500 and stores it
console.log (val);						// prints the value on the screen
```

C/C++:
```
#include <Wyliodrin.h>		//imports wyliodrin library

int main()
{
	uint8_t val;
	val = highByte (1500);	// gets the high byte of 1500 and stores it
	printf ("%d\n"val);		// prints the value on the screen
	return 0;
}
```
##lowByte()
_**Description**_  
Extracts the low-order (rightmost) byte of a variable.

_**Syntax**_  
lowByte (x)

_**Parameters**_  
- x: any value (unsigned int).  

_**Returns**_  
the byte (uint8_t)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

val = lowByte (1500)		# gets the low byte of 1500 and stores it
print val					# prints the value on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	//imports wyliodrin module

var val = lowByte (1500);				// gets the low byte of 1500 and stores it
console.log (val);						// prints the value on the screen
```

C/C++:
```
#include <Wyliodrin.h>		//imports wyliodrin library

int main()
{
	uint8_t val;
	val = lowByte (1500);	// gets the low byte of 1500 and stores it
	printf ("%d\n"val);		// prints the value on the screen
	return 0;
}
```
##bitRead()
_**Description**_  
Reads a bit of a number.

_**Syntax**_  
bitRead (x, n)

_**Parameters**_  
- x: the number from which to read (unsigned int);  
- n: which bit to read, starting at 0 for the least-significant (rightmost) bit (unsigned int).

_**Returns**_  
the value of the bit (0 or 1) (unsigned int)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

val = bitRead (1500, 3)		# gets the fourth bit of 1500 and stores it
print val					# prints the value (1) on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	//imports wyliodrin module

var val = bitRead (1500, 3);			// gets the fourth bit of 1500 and stores it
console.log (val);						// prints the value (1) on the screen
```

C/C++:
```
#include <Wyliodrin.h>		 //imports wyliodrin library

int main()
{
	uint8_t val;
	val = bitRead (1500, 3); // gets the low byte of 1500 and stores it
	printf ("%u\n"val);		 // prints the value on the screen
	return 0;
}
```
##bitWrite()
_**Description**_  
Receives a value and returns a new one with the specified bit set to the given numeric value.

_**Syntax**_  
bitWrite (x, n, b)

_**Parameters**_  
- x: the numeric variable to which to write (unsigned int);  
- n: which bit of the number to write, starting at 0 for the least-significant (rightmost) bit (unsigned int);  
- b: the value to write to the bit, 0 or 1 (unsigned int).

_**Returns**_  
the new value (unsigned int)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

val = bitWrite (1500, 0, 1)	# writes 1 on bit 0 and stores the new value
print val					# prints the new value (1501) on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	//imports wyliodrin module

var val = bitRead (1500, 0, 1);			// writes 1 on bit 0 and stores the new value
console.log (val);						// prints the value (1501) on the screen
```

C/C++:
```
#include <Wyliodrin.h>		 	 //imports wyliodrin library

int main()
{
	uint8_t val;
	val = bitRead (1500, 0, 1); // writes 1 on bit 0 and stores the new value
	printf ("%u\n"val);		    // prints the value on the screen
	return 0;
}
```
##bitSet()
_**Description**_  
Receives a value and returns a new one with the specified bit set to 1.

_**Syntax**_  
bitSet (x, n)

_**Parameters**_  
- x: the numeric variable whose bit to set (unsigned int);  
- n: which bit to set, starting at 0 for the least-significant (rightmost) bit (unsigned int).

_**Returns**_  
the new value (unsigned int)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

val = bitSet (1500, 0)		# writes 1 on bit 0 and stores the new value
print val					# prints the new value (1501) on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	//imports wyliodrin module

var val = bitSet (1500, 0);				// writes 1 on bit 0 and stores the new value
console.log (val);						// prints the value (1501) on the screen
```

C/C++:
```
#include <Wyliodrin.h>		 	 //imports wyliodrin library

int main()
{
	uint8_t val;
	val = bitRead (1500, 0); 	// writes 1 on bit 0 and stores the new value
	printf ("%u\n"val);		    // prints the value on the screen
	return 0;
}
```
##bitClear()
_**Description**_  
Receives a value and returns a new one with the specified bit cleared (set to 0).

_**Syntax**_  
bitClear (x, n)

_**Parameters**_  
- x: the numeric variable whose bit to clear (unsigned int);  
- n: which bit to clear, starting at 0 for the least-significant (rightmost) bit (unsigned int).

_**Returns**_  
the new value (unsigned int)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

val = bitClear (1501, 0)	# writes 0 on bit 0 and stores the new value
print val					# prints the new value (1500) on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	//imports wyliodrin module

var val = bitSet (1501, 0);				// writes 0 on bit 0 and stores the new value
console.log (val);						// prints the value (1500) on the screen
```

C/C++:
```
#include <Wyliodrin.h>		 	 //imports wyliodrin library

int main()
{
	uint8_t val;
	val = bitRead (1501, 0); 	// writes 0 on bit 0 and stores the new value
	printf ("%u\n"val);		    // prints the value on the screen
	return 0;
}
```

##bit()
_**Description**_  
Computes the value of the specified bit (bit 0 is 1, bit 1 is 2, bit 2 is 4 etc.).

_**Syntax**_  
bit (n)

_**Parameters**_  
- n: the bit whose value to compute (int).

_**Returns**_  
the value of the bit (unsigned int)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

val = bit (7)				# computes and stores the new value
print val					# prints the new value (128) on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	//imports wyliodrin module

var val = bit (7);						// computes and stores the new value
console.log (val);						// prints the value (128) on the screen
```

C/C++:
```
#include <Wyliodrin.h>	//imports wyliodrin library

int main()
{
	uint8_t val;
	val = bit (7); 		// computes and stores the new value
	printf ("%u\n"val); // prints the value on the screen
	return 0;
}
```