##SPIClass()
_**Description**_  
Constructor - creates an SPI object.  
NOTE: This function is to be used only in JavaScript and Python.

_**Syntax**_  
SPIClass()

_**Parameters**_  
None

_**Returns**_  
an SPI object

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

spi = SPIClass ()			# creates a new SPI instance
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

var spi = new wyliodrin.SPIClass ();	// creates a new SPI instance
```

##begin()
_**Description**_  
Initializes the SPI bus by setting SCK, MOSI, and SS to outputs, pulling SCK and MOSI low, and SS high.

_**Syntax**_  
begin()

_**Parameters**_  
None

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

spi = SPIClass ()			# creates a new SPI instance
spi.begin ()				# initializes the SPI bus
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

var spi = new wyliodrin.SPIClass ();	// creates a new SPI instance
spi.begin ();							// initializes the SPI bus
```

C/C++:
```
#include <Wyliodrin.h>	//imports wyliodrin library

int main()
{
	SPI.begin ();		// initializes the SPI bus
	return 0;
}
```

##end()
_**Description**_  
Disables the SPI bus (leaving pin modes unchanged).

_**Syntax**_  
end()

_**Parameters**_  
None

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

spi = SPIClass ()			# creates a new SPI instance
spi.begin ()				# initializes the SPI bus
spi.end ()					# disables the SPI bus
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

var spi = new wyliodrin.SPIClass ();	// creates a new SPI instance
spi.begin ();							// initializes the SPI bus
spi.end ();								// disables the SPI bus
```

C/C++:
```
#include <Wyliodrin.h>	//imports wyliodrin library

int main()
{
	SPI.begin ();		// initializes the SPI bus
	SPI.end ();			// disables the SPI bus
	return 0;
}
```

##setBitOrder()
_**Description**_  
Sets the order of the bits shifted out of and into the SPI bus, either [LSBFIRST][lsbfirst link] or [MSBFIRST][msbfirst link].

_**Syntax**_  
setBitOrder(order)

_**Parameters**_  
- order: either [LSBFIRST](lsbfirst link) or [MSBFIRST](msbfirst link).

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

spi = SPIClass ()			# creates a new SPI instance
spi.begin ()				# initializes the SPI bus
spi.setBitOrder (LSBFIRST)	# sets bits order to LSBFIRST
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

var spi = new wyliodrin.SPIClass ();	// creates a new SPI instance
spi.begin ();							// initializes the SPI bus
spi.setBitOrder (wyliodrin.LSBFIRST);	// sets bits order to LSBFIRST
```

C/C++:
```
#include <Wyliodrin.h>			//imports wyliodrin library

int main()
{
	SPI.begin ();				// initializes the SPI bus
	SPI.setBitOrder (LSBFIRST);	// sets bits order to LSBFIRST
	return 0;
}
```

##setDataMode()
_**Description**_  
Sets the SPI data mode: that is clock polarity and phase.

_**Syntax**_  
setDataMode(mode)

_**Parameters**_  
- mode: [SPI_MODE0](constants.md#spi_mode0), [SPI_MODE1](constants.md#spi_mode1), [SPI_MODE2](constants.md#spi_mode2), [SPI_MODE3](constants.md#spi_mode3).

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

spi = SPIClass ()			# creates a new SPI instance
spi.begin ()				# initializes the SPI bus
spi.setDataMode (SPI_MODE0)	# sets data mode to SPI_MODE0
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

var spi = new wyliodrin.SPIClass ();	// creates a new SPI instance
spi.begin ();							// initializes the SPI bus
spi.setDataMode (wyliodrin.SPI_MODE0);	// sets data mode to SPI_MODE0
```

C/C++:
```
#include <Wyliodrin.h>			 //imports wyliodrin library

int main()
{
	SPI.begin ();				 // initializes the SPI bus
	SPI.setDataMode (SPI_MODE0); // sets data mode to SPI_MODE0
	return 0;
}
```

##setClockDivider()
_**Description**_  
Sets the SPI clock divider relative to the system clock. On AVR based boards, the dividers available are 2, 4, 8, 16, 32, 64 or 128. The default setting is SPI_CLOCK_DIV4, which sets the SPI clock to one-quarter the frequency of the system clock.

_**Syntax**_  
setClockDivider(divider)

_**Parameters**_  
- divider: [SPI_CLOCK_DIV2](constants.md#spi_clock_div2),  [SPI_CLOCK_DIV4](constants.md#spi_clock_div4), [SPI_CLOCK_DIV8](constants.md#spi_clock_div8), [SPI_CLOCK_DIV16](constants.md#spi_clock_div16), [SPI_CLOCK_DIV32](constants.md#spi_clock_div32), [SPI_CLOCK_DIV64](constants.md#spi_clock_div64), [SPI_CLOCK_DIV128](constants.md#spi_clock_div128).

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 				# imports wyliodrin module

spi = SPIClass ()						# creates a new SPI instance
spi.begin ()							# initializes the SPI bus
spi.setClockDivider (SPI_CLOCK_DIV2)	# sets clock divider to SPI_CLOCK_DIV2
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 			// imports wyliodrin module

var spi = new wyliodrin.SPIClass ();			// creates a new SPI instance
spi.begin ();									// initializes the SPI bus
spi.setClockDivider (wyliodrin.SPI_CLOCK_DIV2);	// sets clock divider to SPI_CLOCK_DIV2
```

C/C++:
```
#include <Wyliodrin.h>						//imports wyliodrin library

int main()
{
	SPI.begin ();				 			// initializes the SPI bus
	SPI.setClockDivider (SPI_CLOCK_DIV2);	// sets clock divider to SPI_CLOCK_DIV2
	return 0;
}
```

##transfer()
_**Description**_  
SPI transfer is based on a simultaneous send and receive: the received data is returned.

_**Syntax**_  
transfer(data)

_**Parameters**_  
- data: the byte to send out over the bus (uint8_t).

_**Returns**_  
the received data (uint8_t)

_**Example**_  
Python:
``` 
from wyliodrin import * 		  # imports wyliodrin module

spi = SPIClass ()				  # creates a new SPI instance
spi.begin ()					  # initializes the SPI bus
data = 'a'
receivedVal = spi.transfer (data) # sends the 'a' character and recevies a value over the spi bus
print receivedVal 				  # prints the received value
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

var spi = new wyliodrin.SPIClass ();	// creates a new SPI instance
spi.begin ();							// initializes the SPI bus
data = 'a';
receivedVal = spi.transfer (data); 		// sends the 'a' character and recevies a value over the spi bus
console.log (receivedVal); 				// prints the received value
```

C/C++:
```
#include <Wyliodrin.h>					//imports wyliodrin library

int main()
{
	uint8_t data;
	uint8_t receivedVal;
	SPI.begin ();				 		// initializes the SPI bus
	data = 'a';
	// sends the 'a' character and recevies a value over the spi bus
	receivedVal = spi.transfer (data); 
	printf ("%u\n", receivedVal); 		// prints the received value
	return 0;
}
```

##transferBuffer()
_**Description**_  
Transfers SPI data (sends and receives) using buffers.  
NOTE: This function can only be used in C/C++.

_**Syntax**_  
transferBuffer(data)

_**Parameters**_  
- txData: the buffer containing the data to be sent (uint8_t *);  
- rxData: the buffer in which the received data is stored (uint8_t *);  
- len: 	  the size of the buffers (uint32_t);  

_**Returns**_  
None

_**Example**_  

C/C++:
```
#include <Wyliodrin.h>					//imports wyliodrin library

int main()
{
	uint8_t data [3] = "abc";
	uint8_t received [3];
	SPI.begin ();				 		// initializes the SPI bus
	// sends the "abc" string and recevies data over the spi bus
	SPI.transfer (&data, &received, 3); 
	printf ("%s\n", receivedVal); 		// prints the received value
	return 0;
}
```

[msbfirst link]:constants.md#msbfirst
[lsbfirst link]:constants.md#lsbfirst