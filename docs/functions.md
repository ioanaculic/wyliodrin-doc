##pinMode()
_**Description**_  
Configures the specified pin to behave either as an input or an output.

_**Syntax**_  
pinMode (pin, mode)

_**Parameters**_  
- pin: the number of the pin whose mode you wish to set;  
- mode: [INPUT][input link], [OUTPUT][output link].

_**Returns**_  
None

_**Example**_  
Python:
```
from wyliodrin import * # imports wyliodrin module

pinMode (1, INPUT) 		# sets pin 1 as input  
pinMode (2, OUTPUT)		# sets pin 2 as output
```
##digitalWrite()
_**Description**_  
Write a [HIGH][high link] or a [LOW][low link] value to a digital pin.  
NOTE: If you do not set the pinMode() to [OUTPUT][output link], and connect an LED to a pin, when calling digitalWrite(HIGH), the LED may appear dim. Without explicitly setting pinMode(), on most of the boards, the pin will have enabled the internal pull-up resistor, which acts like a large current-limiting resistor.

_**Syntax**_  
digitalWrite (pin, value)

_**Parameters**_  
- pin: the number of the pin you wish to control;  
- value: [HIGH][high link], [LOW][low link].

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

##digitalRead()
_**Description**_  
Reads the value from a specified digital pin, either [HIGH][high link] or [LOW][low link].
Note: If the pin isn't connected to anything, digitalRead() can return either HIGH or LOW (and this can change randomly).

_**Syntax**_  
digitalRead (pin)

_**Parameters**_  
- pin: the number of the pin you wish to read;  

_**Returns**_  
[HIGH][high link] or [LOW][low link]

_**Example**_  
Python:
``` 
from wyliodrin import *  # imports wyliodrin module

pinMode (1, INPUT)       # sets pin 1 as input
value = digitalRead (1)  # reads the input pin and stores the value
print value  			 # prints the value on the screen
```
##analogWrite()
_**Description**_  
Writes an analog value ([PWM wave](http://ocw.cs.pub.ro/courses/iot/courses/02#pwm_-_pulse-width_modulation)) to a pin. Can be used to light a LED at varying brightnesses or drive a motor at various speeds.  
NOTE: The frequency of the PWM signal is different depending on the board you are using. We suggest reading the specifications of the board before using PWM signals.

_**Syntax**_  
analogWrite (pin, value)

_**Parameters**_  
- pin: the number of the pin you wish to control; 
- value: the duty cycle, an integer in the interval [0,255] 

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import *  # imports wyliodrin module

pinMode (1, OUTPUT)      # sets pin 1 as output
for i in range (0,255):  # i gets values from 0 to 255
	analogWrite (1, i)   # write value of i on pin 1
	delay (100) 		 # waits for 100 milliseconds
```

##analogRead()
_**Description**_  
Reads the value from the specified analog pin. The function scales the values to 0-1023 interval.  
Note: If the analog input pin is not connected to anything, the value returned by analogRead() will fluctuate based on a number of factors (e.g. the values of the other analog inputs, how close your hand is to the board etc.).

_**Syntax**_  
analogRead (pin)

_**Parameters**_  
- pin: the number of the pin you wish to read;  

_**Returns**_  
an integer value in the interval [0,1023]

_**Example**_  
Python:
``` 
from wyliodrin import *  # imports wyliodrin module

value = analogRead (1)   # reads the input pin and stores the value
print value  			 # prints the value on the screen
```

##analogWriteRaw()
_**Description**_  
Writes a raw analog value ([PWM wave](http://ocw.cs.pub.ro/courses/iot/courses/02#pwm_-_pulse-width_modulation)) to a pin. Can be used to light a LED at varying brightnesses or drive a motor at various speeds.  
NOTE: The values that can be written to the pin depend on each board.

_**Syntax**_  
analogWriteRaw (pin, value)

_**Parameters**_  
- pin: the number of the pin you wish to control; 
- value: the raw duty cycle, depends on the board  

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import *  # imports wyliodrin module

pinMode (1, OUTPUT)      # sets pin 1 as output
for i in range (0,255):  # i gets values from 0 to 255
	analogWriteRaw (1, i)# write value of i on pin 1
	delay (100) 
```

##analogReadRaw()
_**Description**_  
Reads the raw value from the specified analog pin. The values depend on the board.

_**Syntax**_  
analogReadRaw (pin)

_**Parameters**_  
- pin: the number of the pin you wish to read  

_**Returns**_  
an integer value from an interval that depends on the board

_**Example**_  
Python:
``` 
from wyliodrin import *  # imports wyliodrin module

value = analogReadRaw (1)# reads the input pin and stores the raw value
print value  			 # prints the value on the screen
```

##pulseIn()
_**Description**_  
Reads a pulse (either [HIGH][high link] or [LOW][low link]) on a pin. For example, if value is HIGH, pulseIn() waits for the pin to go HIGH, starts timing, then waits for the pin to go LOW and stops timing. Returns the length of the pulse in microseconds.

_**Syntax**_  
pulseIn (pin, value) 

_**Parameters**_  
- pin: the number of the pin on which wish to read the pulse;  
- value: type of pulse to read, either HIGH or LOW. 

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

##shiftIn()
_**Description**_  
Shifts in a byte of data one bit at a time. Starts from either the most (the leftmost) or least (the rightmost) significant bit. For each bit, the clock pin is pulled high, the next bit is read from the data line, and then the clock pin is taken low.

_**Syntax**_  
shiftIn (dataPin, clockPin, bitOrder)

_**Parameters**_  
- dataPin: the pin on which to input each bit;  
- clockPin: the pin to toggle to signal a read from dataPin;  
- bitOrder: which order to shift in the bits ([MSBFIRST][msbfirst link] or [LSBFIRST][lsbfirst link]). 

_**Returns**_  
the value read (byte)

_**Example**_  
Python:
``` 
from wyliodrin import *  			 # imports wyliodrin module

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

##shiftOut()
_**Description**_  
Shifts out a byte of data one bit at a time. Starts from either the most (the leftmost) or least (the rightmost) significant bit. For each bit, the clock pin is pulled high, the next bit is sent to the data line, and then the clock pin is taken low to indicate that the bit is available.  
NOTE: The **dataPin** and **clockPin** must already be configured as outputs by a call to [pinMode()](#pinmode).

_**Syntax**_  
shiftOut(dataPin, clockPin, bitOrder, value)

_**Parameters**_  
- dataPin: the pin on which to input each bit;  
- clockPin: the pin to toggle to signal a read from dataPin;  
- bitOrder: which order to shift in the bits ([MSBFIRST][msbfirst link] or [LSBFIRST][lsbfirst link]);  
- value: the byte to shift out.

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

##millis()
_**Description**_  
Returns the number of milliseconds since the board began running the current program. This number will overflow (go back to zero), after approximately 50 days.

_**Syntax**_  
millis ()

_**Parameters**_  
None

_**Returns**_  
number of milliseconds since the program started (unsigned long)

_**Example**_  
Python:
``` 
from wyliodrin import *  # imports wyliodrin module

delay (1000)			 # waits for one second
time = millis ()		 # gets the milliseconds since the program started and stores the number
print (time)			 # prints the stored value on the screen
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

##delay()
_**Description**_  
Pauses the program for the amount of time (in miliseconds) specified as parameter. 

_**Syntax**_  
delay (ms)

_**Parameters**_  
ms: the number of milliseconds to pause

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

##delayMicroseconds()
_**Description**_  
Pauses the program for the amount of time (in microseconds) specified as parameter. 

_**Syntax**_  
delayMicroseconds (us)

_**Parameters**_  
us: the number of microseconds to pause

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

pinMode (1, OUTPUT)    		# sets pin 1 as output
digitalWrite (1, HIGH) 		# sets the pin on
delayMicroseconds (10000)	# waits for 10 miliseconds
digitalWrite (1, LOW)  		# sets the pin off
```

##map()
_**Description**_  
Re-maps a number from one range to another.  

_**Syntax**_  
map (value, fromLow, fromHigh, toLow, toHigh)

_**Parameters**_  
- value: the number to map;  
- fromLow: the lower bound of the value's current range;  
- fromHigh: the upper bound of the value's current range;  
- toLow: the lower bound of the value's target range;  
- toHigh: the upper bound of the value's target range.

_**Returns**_  
the mapped value

_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

val = analogRead(0)				# reads an analog value 0-1023
val = map(val, 0, 1023, 0, 255) # maps the value to an interval 0-255
analogWrite(9, val)				# writes the value on a PWM pin
```

##highByte()
_**Description**_  
Extracts the high-order (leftmost) byte of a word (or the second lowest byte of a larger data type).

_**Syntax**_  
highByte (x)

_**Parameters**_  
- x: a value of any type.  

_**Returns**_  
byte

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

val = highByte (1500)		# gets the high byte of 1500 and stores it
print val					# prints the value on the screen
```

##lowByte()
_**Description**_  
Extracts the low-order (rightmost) byte of a variable.

_**Syntax**_  
lowByte (x)

_**Parameters**_  
- x: a value of any type.  

_**Returns**_  
byte

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

val = lowByte (1500)		# gets the low byte of 1500 and stores it
print val					# prints the value on the screen
```

##bitRead()
_**Description**_  
Reads a bit of a number.

_**Syntax**_  
bitRead (x, n)

_**Parameters**_  
- x: the number from which to read;
- n: which bit to read, starting at 0 for the least-significant (rightmost) bit.

_**Returns**_  
the value of the bit (0 or 1)

##bitWrite()
_**Description**_  
Writes a bit of a numeric variable.

_**Syntax**_  
bitWrite (x, n, b)

_**Parameters**_  
- x: the numeric variable to which to write;
- n: which bit of the number to write, starting at 0 for the least-significant (rightmost) bit;
- b: the value to write to the bit (0 or 1).

_**Returns**_  
None

##bitSet()
_**Description**_  
Sets (writes a 1 to) a bit of a numeric variable.

_**Syntax**_  
bitSet (x, n)

_**Parameters**_  
- x: the numeric variable whose bit to set;
- n: which bit to set, starting at 0 for the least-significant (rightmost) bit.

_**Returns**_  
None

##bitClear()
_**Description**_  
Clears (writes a 0 to) a bit of a numeric variable.

_**Syntax**_  
bitClear (x, n)

_**Parameters**_  
- x: the numeric variable whose bit to clear;
- n: which bit to clear, starting at 0 for the least-significant (rightmost) bit.

_**Returns**_  
None

##bit()
_**Description**_  
Computes the value of the specified bit (bit 0 is 1, bit 1 is 2, bit 2 is 4 etc.).

_**Syntax**_  
bit (n)

_**Parameters**_  
- n: the bit whose value to compute.

_**Returns**_  
the value of the bit

[high link]: 	constants.md#high
[low link]: 	constants.md#low
[input link]: 	constants.md#input
[output link]: 	constants.md#output
[msbfirst link]:constants.md#msbfirst
[lsbfirst link]:constants.md#lsbfirst