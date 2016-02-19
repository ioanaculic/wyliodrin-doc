##pinMode()
_**Description**_  
Configures the specified pin to behave either as an input or an output.

_**Syntax**_  
pinMode (pin, mode)

_**Parameters**_  
- pin: the number of the pin whose mode you wish to set (int);  
- mode: [INPUT][input link], [OUTPUT][output link] (int).

_**Returns**_  
None

_**Example**_  
Python:
```
from wyliodrin import * # imports wyliodrin module

pinMode (1, INPUT) 		# sets pin 1 as input  
pinMode (2, OUTPUT)		# sets pin 2 as output
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	 // imports wyliodrin module

wyliodrin.pinMode (1, wyliodrin.INPUT);	 // sets pin 1 as input  
wyliodrin.pinMode (2, wyliodrin.OUTPUT); // sets pin 2 as output
```

C/C++:
```
#include <Wyliodrin.h>			//imports wyliodrin library

int main()
{
	pinMode (1, INPUT); 		// sets pin 1 as input  
	pinMode (2, OUTPUT);		// sets pin 2 as output
	return 0;
}
```
##digitalWrite()
_**Description**_  
Write a [HIGH][high link] or a [LOW][low link] value to a digital pin.  
NOTE: If you do not set the pinMode() to [OUTPUT][output link], and connect an LED to a pin, when calling digitalWrite(HIGH), the LED may appear dim. Without explicitly setting pinMode(), on most of the boards, the pin will have enabled the internal pull-up resistor, which acts like a large current-limiting resistor.

_**Syntax**_  
digitalWrite (pin, value)

_**Parameters**_  
- pin: the number of the pin you wish to control (int);  
- value: [HIGH][high link], [LOW][low link] (int).

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
var wyliodrin = require ('wyliodrin'); 		// imports wyliodrin module

wyliodrin.pinMode (1, wyliodrin.OUTPUT);    // sets pin 1 as output
wyliodrin.digitalWrite (1, wyliodrin.HIGH); // sets the pin on
wyliodrin.delay (1000);		  	 	   		//waits for a second
wyliodrin.digitalWrite (1, wyliodrin.LOW);  // sets the pin off
```

C/C++:
```
#include <Wyliodrin.h>		 //imports wyliodrin library

int main()
{
	pinMode (1, OUTPUT);     // sets pin 1 as output
	digitalWrite (1, HIGH);  // sets the pin on
	delay (1000);		  	 // waits for a second
	digitalWrite (1, LOW);   // sets the pin off
	return 0;
}
```
##digitalRead()
_**Description**_  
Reads the value from a specified digital pin, either [HIGH][high link] or [LOW][low link].
Note: If the pin isn't connected to anything, digitalRead() can return either HIGH or LOW (and this can change randomly).

_**Syntax**_  
digitalRead (pin)

_**Parameters**_  
- pin: the number of the pin you wish to read (int).  

_**Returns**_  
[HIGH][high link] or [LOW][low link] (int)

_**Example**_  
Python:
``` 
from wyliodrin import *  # imports wyliodrin module

pinMode (1, INPUT)       # sets pin 1 as input
value = digitalRead (1)  # reads the input pin and stores the value
print value  			 # prints the value on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin');  // imports wyliodrin module

wyliodrin.pinMode (1, wyliodrin.INPUT); // sets pin 1 as input
var value = wyliodrin.digitalRead (1);  // reads the input pin and stores the value
console.log (value);  			        // prints the value on the screen
```

C/C++:
```
#include <Wyliodrin.h>		  //imports wyliodrin library

int main()
{
	int value; 
	pinMode (1, INPUT);       // sets pin 1 as input
	value = digitalRead (1);  // reads the input pin and stores the value
	printf("%d\n", value); 	  // prints the value on the screen
	return 0;
}
```
##analogWrite()
_**Description**_  
Writes an analog value ([PWM wave](http://ocw.cs.pub.ro/courses/iot/courses/02#pwm_-_pulse-width_modulation)) to a pin. Can be used to light a LED at varying brightnesses or drive a motor at various speeds.  
NOTE: The frequency of the PWM signal is different depending on the board you are using. We suggest reading the specifications of the board before using PWM signals.

_**Syntax**_  
analogWrite (pin, value)

_**Parameters**_  
- pin: the number of the pin you wish to control (int); 
- value: the duty cycle, in the interval [0,255] (int).

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import *  # imports wyliodrin module

pinMode (1, OUTPUT)      # sets pin 1 as output
for i in range (0,256):  # i gets values from 0 to 255
	analogWrite (1, i)   # write value of i on pin 1
	delay (100) 		 # waits for 100 milliseconds
```

JavaScript:
```
var wyliodrin = require ('wyliodrin');  //imports wyliodrin module

wyliodrin.pinMode (1, OUTPUT);      	// sets pin 1 as output
var i;
for (i = 0; i < 256; i++)  				// i gets values from 0 to 255
{
	wyliodrin.analogWrite (1, i);   	// write value of i on pin 1
	wyliodrin.delay (100); 		 		// waits for 100 milliseconds
}
	
```

C/C++:
```
#include <Wyliodrin.h>			//imports wyliodrin library

int main()
{
	int i;
	pinMode (1, OUTPUT);      	// sets pin 1 as output
	for (i = 0; i < 256; i++)  	// i gets values from 0 to 255
	{
		analogWrite (1, i);   	// write value of i on pin 1
		delay (100); 		 	// waits for 100 milliseconds
	}
	return 0;
}
```
##analogRead()
_**Description**_  
Reads the value from the specified analog pin. The function scales the values to 0-1023 interval.  
Note: If the analog input pin is not connected to anything, the value returned by analogRead() will fluctuate based on a number of factors (e.g. the values of the other analog inputs, how close your hand is to the board etc.).

_**Syntax**_  
analogRead (pin)

_**Parameters**_  
- pin: the number of the pin you wish to read (int).  
//imports wyliodrin module
_**Returns**_  
a value in the interval [0,1023] (int)

_**Example**_  
Python:
``` 
from wyliodrin import *  # imports wyliodrin module

value = analogRead (1)   # reads the input pin and stores the value
print value  			 # prints the value on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin');  //imports wyliodrin module

var value = wyliodrin.analogRead (1);   // reads the input pin and stores the value
console.log (value);  			 		// prints the value on the screen
	
```

C/C++:
```
#include <Wyliodrin.h>					//imports wyliodrin library

int main()
{
	int value;
	value = analogRead (1);   			// reads the input pin and stores the value
	printf ("value is : %d\n", value);  // prints the value on the screen
	return 0;
}
```
##analogWriteRaw()
_**Description**_  
Writes a raw analog value ([PWM wave](http://ocw.cs.pub.ro/courses/iot/courses/02#pwm_-_pulse-width_modulation)) to a pin. Can be used to light a LED at varying brightnesses or drive a motor at various speeds.  
NOTE: The values that can be written to the pin depend on each board.

_**Syntax**_  
analogWriteRaw (pin, value)

_**Parameters**_  
- pin: the number of the pin you wish to control (int); 
- value: the raw duty cycle, depends on the board  (int).

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import *   # imports wyliodrin module

pinMode (1, OUTPUT)       # sets pin 1 as output
for i in range (0,256):   # i gets values from 0 to 255
	analogWriteRaw (1, i) # write value of i on pin 1
	delay (100) 
```

JavaScript:
```
var wyliodrin = require ('wyliodrin');  //imports wyliodrin module

wyliodrin.pinMode (1, OUTPUT);      	// sets pin 1 as output
var i;
for (i = 0; i < 256; i++)  				// i gets values from 0 to 255
{
	wyliodrin.analogWriteRaw (1, i);   	// write value of i on pin 1
	wyliodrin.delay (100); 		 		// waits for 100 milliseconds
}
	
```

C/C++:
```
#include <Wyliodrin.h>			//imports wyliodrin library

int main()
{
	int i;
	pinMode (1, OUTPUT);      	// sets pin 1 as output
	for (i = 0; i < 256; i++)  	// i gets values from 0 to 255
	{
		analogWriteRaw (1, i);  // write value of i on pin 1
		delay (100); 		 	// waits for 100 milliseconds
	}
	return 0;
}
```
##analogReadRaw()
_**Description**_  
Reads the raw value from the specified analog pin. The values depend on the board.

_**Syntax**_  
analogReadRaw (pin)

_**Parameters**_  
- pin: the number of the pin you wish to read (int). 

_**Returns**_  
a value from an interval depending on the board (int)

_**Example**_  
Python:
``` 
from wyliodrin import *   # imports wyliodrin module

value = analogReadRaw (1) # reads the input pin and stores the raw value
print value  			  # prints the value on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin');  	//imports wyliodrin module

var value = wyliodrin.analogReadRaw (1);   // reads the input pin and stores the value
console.log (value);  			 		   // prints the value on the screen
	
```

C/C++:
```
#include <Wyliodrin.h>						//imports wyliodrin library

int main()
{
	int value;
	value = analogReadRaw (1);   			// reads the input pin and stores the value
	printf ("raw value is : %d\n", value);  // prints the value on the screen
	return 0;
}
```
##pulseIn()
_**Description**_  
Reads a pulse (either [HIGH][high link] or [LOW][low link]) on a pin. For example, if value is HIGH, pulseIn() waits for the pin to go HIGH, starts timing, then waits for the pin to go LOW and stops timing. Returns the length of the pulse in microseconds.

_**Syntax**_  
pulseIn (pin, value) 

_**Parameters**_  
- pin: the number of the pin on which wish to read the pulse (uint8_t);  
- value: type of pulse to read, either HIGH or LOW (uint8_t). 

_**Returns**_  
the length of the pulse in microseconds (unsigned long)

_**Example**_  
Python:
``` 
from wyliodrin import *  		# imports wyliodrin module

pinMode (1, INPUT)				# sets pin 1 as input
while True:
	value = pulseIn (1, HIGH)   # reads the microseconds between LOW and HIGH stores the value
	print value  			 	# prints the value on the screen
```

JavaScript:
```
var wyliodrin = require ('wyliodrin');  //imports wyliodrin module

wyliodrin.pinMode (1, wyliodrin.INPUT);	// sets pin 1 as input
while (true)
{
	// reads the microseconds between LOW and HIGH stores the value
	var value = wyliodrin.pulseIn (1, wyliodrin.HIGH); 
	console.log (value);  			 	// prints the value on the screen
}
```

C/C++:
```
#include <Wyliodrin.h>				//imports wyliodrin library

int main()
{
	unsigned long value;
	pinMode (1, INPUT);				// sets pin 1 as input
	while (true)
	{

		value = pulseIn (1, HIGH); // reads the microseconds between LOW and HIGH stores the value
		printf ("%d\n", value);    // prints the value on the screen
	}
	return 0;
}
```
##shiftIn()
_**Description**_  
Shifts in a byte of data one bit at a time. Starts from either the most (the leftmost) or least (the rightmost) significant bit. For each bit, the clock pin is pulled high, the next bit is read from the data line, and then the clock pin is taken low.

_**Syntax**_  
shiftIn (dataPin, clockPin, bitOrder)

_**Parameters**_  
- dataPin: the pin on which to input each bit (uint8_t);  
- clockPin: the pin to toggle to signal a read from dataPin (uint8_t);  
- bitOrder: which order to shift in the bits ([MSBFIRST][msbfirst link] or [LSBFIRST][lsbfirst link]) (uint8_t). 

_**Returns**_  
the value read (uint8_t)

_**Example**_  
Python:
``` 
from wyliodrin import *  	# imports wyliodrin module

latchPin = 8
clockPin = 12
dataPin  = 11

pinMode (latchPin, OUTPUT) # sets latch pin as output

# sets pins to input
pinMode (clockPin, INPUT)
pinMode (dataPin, INPUT)

# set latchPin to low and hold low for as long as you are reading
digitalWrite(latchPin, LOW)

# read the first byte and store it
firstByte = shiftIn(dataPin, clockPin, LSBFIRST)

# return the latch pin high to signal chip that it can send the next byte
digitalWrite(latchPin, HIGH)
```

JavaScript:
```
var wyliodrin = require ('wyliodrin');  //imports wyliodrin module

var latchPin = 8;
var clockPin = 12;
var dataPin  = 11;

wyliodrin.pinMode (latchPin, wyliodrin.OUTPUT); // sets latch pin as output

// sets pins to input
wyliodrin.pinMode (clockPin, wyliodrin.INPUT);
wyliodrin.pinMode (dataPin, wyliodrin.INPUT);

// set latchPin to low and hold low for as long as you are reading
wyliodrin.digitalWrite(latchPin, wyliodrin.LOW);

// read the first byte and store it
var firstByte = wyliodrin.shiftIn(dataPin, clockPin, wyliodrin.LSBFIRST);

// return the latch pin high to signal chip that it can send the next byte
wyliodrin.digitalWrite(latchPin, wyliodrin.HIGH);
```

C/C++:
```
#include <Wyliodrin.h>			//imports wyliodrin library

int main()
{
	uint8_t latchPin = 8;
	uint8_t clockPin = 12;
	uint8_t dataPin  = 11;

	uint8_t firstByte;

	pinMode (latchPin, OUTPUT); // sets latch pin as output

	// sets pins to input
	pinMode (clockPin, INPUT);
	pinMode (dataPin, INPUT);

	// set latchPin to low and hold low for as long as you are reading
	digitalWrite(latchPin, LOW);

	// read the first byte and store it
	firstByte = shiftIn(dataPin, clockPin, LSBFIRST);

	// return the latch pin high to signal chip that it can send the next byte
	digitalWrite(latchPin, HIGH);
	return 0;
}
```
##shiftOut()
_**Description**_  
Shifts out a byte of data one bit at a time. Starts from either the most (the leftmost) or least (the rightmost) significant bit. For each bit, the clock pin is pulled high, the next bit is sent to the data line, and then the clock pin is taken low to indicate that the bit is available.  
NOTE: The **dataPin** and **clockPin** must already be configured as outputs by a call to [pinMode()](#pinmode).

_**Syntax**_  
shiftOut(dataPin, clockPin, bitOrder, value)

_**Parameters**_  
- dataPin: the pin on which to input each bit (uint8_t);  
- clockPin: the pin to toggle to signal a read from dataPin (uint8_t);  
- bitOrder: which order to shift in the bits ([MSBFIRST][msbfirst link] or [LSBFIRST][lsbfirst link]) (uint8_t);  
- value: the byte to shift out (uint8_t).

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import *  			 # imports wyliodrin module

latchPin = 8
clockPin = 12
dataPin  = 11

# sets pins to output
pinMode (latchPin, OUTPUT)
pinMode (clockPin, OUTPUT)
pinMode (dataPin, OUTPUT)

# set latchPin to low and hold low for as long as you are transmitting
digitalWrite(latchPin, LOW) 
shiftOut(dataPin, clockPin, LSBFIRST, 200) # write the value 200
# return the latch pin high to signal chip that it no longer needs to listen for information
digitalWrite(latchPin, HIGH)
```

JavaScript:
```
var wyliodrin = require ('wyliodrin');  //imports wyliodrin module

var latchPin = 8;
var clockPin = 12;
var dataPin  = 11;

// sets pins to output
wyliodrin.pinMode (latchPin, wyliodrin.OUTPUT);
wyliodrin.pinMode (clockPin, wyliodrin.OUTPUT);
wyliodrin.pinMode (dataPin, wyliodrin.OUTPUT);

// set latchPin to low and hold low for as long as you are transmitting
wyliodrin.digitalWrite(latchPin, wyliodrin.LOW); 
wyliodrin.shiftOut(dataPin, clockPin, wyliodrin.LSBFIRST, 200); // write the value 200
// return the latch pin high to signal chip that it no longer needs to listen for information
wyliodrin.digitalWrite(latchPin, wyliodrin.HIGH);
```

C/C++:
```
#include <Wyliodrin.h>			//imports wyliodrin library

int main()
{
	uint8_t latchPin = 8;
	uint8_t clockPin = 12;
	uint8_t dataPin  = 11;

	// sets pins to output
	pinMode (latchPin, OUTPUT);
	pinMode (clockPin, OUTPUT);
	pinMode (dataPin, OUTPUT);

	// set latchPin to low and hold low for as long as you are transmitting
	digitalWrite(latchPin, LOW); 
	shiftOut(dataPin, clockPin, LSBFIRST, 200); // write the value 200
	// return the latch pin high to signal chip that it no longer needs to listen for information
	digitalWrite(latchPin, HIGH);
	return 0;
}
```
[high link]: 	constants.md#high
[low link]: 	constants.md#low
[input link]: 	constants.md#input
[output link]: 	constants.md#output
[msbfirst link]:constants.md#msbfirst
[lsbfirst link]:constants.md#lsbfirst