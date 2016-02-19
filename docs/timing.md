##millis()
_**Description**_  
Returns the number of milliseconds since the board began running the current program. This number will overflow (go back to zero), after approximately 50 days.

_**Syntax**_  
millis ()

_**Parameters**_  
None

_**Returns**_  
number of milliseconds since the program started (unsigned int)

_**Example**_  
Python:
``` 
from wyliodrin import *  # imports wyliodrin module

delay (1000)			 # waits for one second
time = millis ()		 # gets the milliseconds since the program started and stores the number
print (time)			 # prints the stored value on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); //imports wyliodrin module

wyliodrin.delay (1000);			 	   // waits for one second
var time = wyliodrin.millis ();		   // gets the milliseconds since the program started and stores the number
console.log (time)			 		   // prints the stored value on the screen
```

C/C++:
```
#include <Wyliodrin.h>		//imports wyliodrin library

int main()
{
	unsigned int time;
	delay (1000);			// waits for one second
 	time = millis ();		// gets the milliseconds since the program started and stores the number
	printf ("%d\n", time);  // prints the stored value on the screen
	return 0;
}
```
##micros()
_**Description**_  
Returns the number of microseconds since the board began running the current program. This number will overflow (go back to zero), after approximately 70 minutes.

_**Syntax**_  
micros ()

_**Parameters**_  
None

_**Returns**_  
number of microseconds since the program started (unsigned long)

_**Example**_  
Python:
``` 
from wyliodrin import *  # imports wyliodrin module

delay (1000)			 # waits for one second
time = micros ()		 # gets the microseconds since the program started and stores the number
print (time)			 # prints the stored value on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); //imports wyliodrin module

wyliodrin.delay (1000);			 	   // waits for one second
var time = wyliodrin.micros ();		   // gets the milliseconds since the program started and stores the number
console.log (time)			 		   // prints the stored value on the screen
```

C/C++:
```
#include <Wyliodrin.h>		//imports wyliodrin library

int main()
{
	unsigned int time;
	delay (1000);			// waits for one second
 	time = micros ();		// gets the milliseconds since the program started and stores the number
	printf ("%d\n", time);  // prints the stored value on the screen
	return 0;
}
```
##delay()
_**Description**_  
Pauses the program for the amount of time (in milliseconds) specified as parameter. 

_**Syntax**_  
delay (ms)

_**Parameters**_  
ms: the number of milliseconds to pause (unsigned int).

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * # imports wyliodrin module

pinMode (1, OUTPUT)    # sets pin 1 as output
digitalWrite (1, HIGH) # sets the pin on
delay (1000)		   # waits for a second
digitalWrite (1, LOW)  # sets the pin off
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 		//imports wyliodrin module

wyliodrin.pinMode (1, wyliodrin.OUTPUT);    // sets pin 1 as output
wyliodrin.digitalWrite (1, wyliodrin.HIGH); // sets the pin on
wyliodrin.delay (1000);		   				// waits for a second
wyliodrin.digitalWrite (1, wyliodrin.LOW);  // sets the pin off
```

C/C++:
```
#include <Wyliodrin.h>		//imports wyliodrin library

int main()
{
	pinMode (1, OUTPUT);    // sets pin 1 as output
	digitalWrite (1, HIGH); // sets the pin on
	delay (1000);		   	// waits for a second
	digitalWrite (1, LOW);  // sets the pin off
	return 0;
}
```
##delayMicroseconds()
_**Description**_  
Pauses the program for the amount of time (in microseconds) specified as parameter. 

_**Syntax**_  
delayMicroseconds (us)

_**Parameters**_  
us: the number of microseconds to pause (unsigned int).

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

pinMode (1, OUTPUT)    		# sets pin 1 as output
digitalWrite (1, HIGH) 		# sets the pin on
delayMicroseconds (10000)	# waits for 10 milliseconds
digitalWrite (1, LOW)  		# sets the pin off
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 		//imports wyliodrin module

wyliodrin.pinMode (1, wyliodrin.OUTPUT);    // sets pin 1 as output
wyliodrin.digitalWrite (1, wyliodrin.HIGH); // sets the pin on
wyliodrin.delayMicroseconds (10000);		// waits for 10 milliseconds
wyliodrin.digitalWrite (1, wyliodrin.LOW);  // sets the pin off
```

C/C++:
```
#include <Wyliodrin.h>		   //imports wyliodrin library

int main()
{
	pinMode (1, OUTPUT);       // sets pin 1 as output
	digitalWrite (1, HIGH);    // sets the pin on
	delayMicroseconds (10000); // waits for 10 milliseconds
	digitalWrite (1, LOW);     // sets the pin off
	return 0;
}
```
