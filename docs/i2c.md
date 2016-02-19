##TwoWire()
_**Description**_  
Constructor - creates a Wire object, then calls [begin()](#begin). It also calls the function it receives a parameter once the new object is created.
NOTE: This function is to be used only in JavaScript and Python.

_**Syntax**_  
TwoWire(callbackFunction)

_**Parameters**_  
- callbackFunction: function to be called after the object is created; it takes no parameter and returns nothing.

_**Returns**_  
a Wire object

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

def myFunction ():
	print 'object created'

i2c = TwoWire (myFunction)	# creates a new TwoWire instance
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

// creates a new TwoWire instance
var i2c = new wyliodrin.TwoWire (function (){
	console.log ('object created');
});	
```

##begin()
_**Description**_  
Initiate the Wire library and join the I2C bus as a master or slave. This should normally be called only once.

_**Syntax**_  
begin([address])

_**Parameters**_  
- address: the 7-bit slave address (optional); if not specified, join the bus as a master (uint8_t or int).

_**Returns**_  
None

_**Example**_  
C/C++:
```
#include <Wyliodrin.h>	// imports wyliodrin library

int main()
{
	Wire.begin ();		// joins the I2C bus
	return 0;
}
```

##requestFrom()
_**Description**_  
Used by the master to request bytes from a slave device. The bytes may then be retrieved with the [available()](#available) and [read()](#read) functions. 

requestFrom() accepts a numeric argument changing its behavior for compatibility with certain I2C devices. If different from 0, requestFrom() sends a stop message after the request, releasing the I2C bus.

If 0, requestFrom() sends a restart message after the request. The bus will not be released, which prevents another master device from requesting between messages. This allows one master device to send multiple requests while in control.

The default value is different from 0.

_**Syntax**_  
requestFrom(address, quantity, [stop])

_**Parameters**_  
- address: the 7-bit address of the device to request bytes from (uint8_t or int);  
- quantity: the number of bytes to request (uint8_t or int);  
- stop: different from 0 will send a stop message after the request, releasing the bus. 0 will continually send a restart after the request, keeping the connection active.

_**Returns**_  
the number of bytes returned from the slave device (uint8_t)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

def myFunction ():
	print 'object created'

i2c = TwoWire (myFunction)	# creates a new TwoWire instance
i2c.requestFrom (2,6)		# requests 6 bytes from slave device no. 2
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

// creates a new TwoWire instance
var i2c = new wyliodrin.TwoWire (function (){
	console.log ('object created');
});	
i2c.requestFrom (2,6); 					// request 6 bytes from slave device #2
```

C/C++:
```
#include <Wyliodrin.h>		// imports wyliodrin library

int main()
{
	Wire.begin ();			// joins the I2C bus
	Wire.requestFrom (2,6); // request 6 bytes from slave device #2
	return 0;
}
```
##beginTransmission()
_**Description**_  
Begin a transmission to the I2C slave device with the given address. Subsequently, queue bytes for transmission with the [write()](#write) function and transmit them by calling [endTransmission()](#endtransmission).

_**Syntax**_  
beginTransmission(address)

_**Parameters**_  
- address: the 7-bit address of the device to transmit to (uint8_t or int).  

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

def myFunction ():
	print 'object created'

i2c = TwoWire (myFunction)	# creates a new TwoWire instance
i2c.beginTransmission (8)	# transmit to device #8
i2c.write ('a')				# sends one byte
i2c.endTransmission ()		# stop transmitting
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

// creates a new TwoWire instance
var i2c = new wyliodrin.TwoWire (function (){
	console.log ('object created');
});	
i2c.beginTransmission (8);		// transmit to device #8
i2c.write ('a');				// sends one byte
i2c.endTransmission ();			// stop transmitting
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	Wire.begin ();				// joins the I2C bus
	Wire.beginTransmission(8);  // transmit to device #8
  	Wire.write("a");            // sends one byte
  	Wire.endTransmission();     // stop transmitting
	return 0;
}
```

##endTransmission()
_**Description**_  
Ends a transmission to a slave device that was begun by [beginTransmission()](#beginTransmission) and transmits the bytes that were queued by [write()](#write).

endTransmission() accepts a numeric argument changing its behavior for compatibility with certain I2C devices. If different from 0, endTransmission() sends a stop message after transmission, releasing the I2C bus.

If 0, endTransmission() sends a restart message after transmission. The bus will not be released, which prevents another master device from transmitting between messages. This allows one master device to send multiple transmissions while in control.

The default value is different from 0.

_**Syntax**_  
endTransmission([stop])

_**Parameters**_  
- stop: optional; different from 0 will send a stop message after the transmission, releasing the bus. 0 will send a restart, keeping the connection active (uint8_t). 

_**Returns**_  
a value (uint8_t) which indicates the status of the transmission:
- 0:success;  
- 1:data too long to fit in transmit buffer;  
- 2:received NACK on transmit of address;  
- 3:received NACK on transmit of data;  
- 4:other error.

_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

def myFunction ():
	print 'object created'

i2c = TwoWire (myFunction)		# creates a new TwoWire instance
i2c.beginTransmission (8)		# transmit to device #8
i2c.write ('a')					# sends one byte
status = i2c.endTransmission ()	# stop transmitting
if (status == 0):				# check if transmission succeded
	print 'transmission successful'
else:
	print 'transmission error'
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 		// imports wyliodrin module

// creates a new TwoWire instance
var i2c = new wyliodrin.TwoWire (function (){
	console.log ('object created');
});	
i2c.beginTransmission (8);					// transmit to device #8
i2c.write ('a');							// sends one byte
var status = i2c.endTransmission ();		// stop transmitting
if (status == 0)							// check if transmission succeded
	console.log ('transmission successful');
else
	console.log ('transmission error');
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	uint8_t status;

	Wire.begin ();				// joins the I2C bus
	Wire.beginTransmission(8);  // transmit to device #8
  	Wire.write("a");            // sends one byte
  	Wire.endTransmission();     // stop transmitting
  	if (status == 0)			// check if transmission succeded
		printf ("transmission successful\n");
	else
		printf ("transmission error\n");
	return 0;
}
```

##write()
_**Description**_  
Writes data from a slave device in response to a request from a master, or queues bytes for transmission from a master to slave device (in-between calls to [beginTransmission()](#begintransmission) and [endTransmission()](#endtransmission)).

_**Syntax**_  
write (value)  
write (data, length)

_**Parameters**_  
- value: a value to send as a single byte (uint8_t);  
- data: an array of data to send as bytes (const uint8_t *);  
- length: the number of bytes to transmit (size_t).

_**Returns**_  
the number of bytes written, though reading that number is optional (size_t)
_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

def myFunction ():
	print 'object created'

i2c = TwoWire (myFunction)			# creates a new TwoWire instance
i2c.beginTransmission (8)			# transmit to device #8
written = i2c.write ('a')			# sends one byte
status = i2c.endTransmission ()		# stop transmitting
if (status == 0):					# check if transmission succeded
	print 'transmitted '+written+' bytes'
else:
	print 'transmission error'
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 		// imports wyliodrin module

// creates a new TwoWire instance
var i2c = new wyliodrin.TwoWire (function (){
	console.log ('object created');
});	
i2c.beginTransmission (8);					// transmit to device #8
var sritten = i2c.write ('a');				// sends one byte
var status = i2c.endTransmission ();		// stop transmitting
if (status == 0)							// check if transmission succeded
	console.log ('transmitted '+written+' bytes');
else
	console.log ('transmission error');
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	uint8_t status;
	size_t written;

	Wire.begin ();				// joins the I2C bus
	Wire.beginTransmission(8);  // transmit to device #8
  	written = Wire.write("a");  // sends one byte
  	Wire.endTransmission();     // stop transmitting
  	if (status == 0)			// check if transmission succeded
		printf ("transmitted %d bytes\n", written);
	else
		printf ("transmission error\n");
	return 0;
}
```

##available()
_**Description**_  
Returns the number of bytes available for retrieval with [read()](#read). This should be called on a master device after a call to [requestFrom()](#requestfrom) or on a slave inside the [onReceive()](#onreceive) handler.

_**Syntax**_  
available()

_**Parameters**_  
None

_**Returns**_  
the number of bytes available for reading (int)
_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

def myFunction ()):
	print 'object created'

def receiveEvent (howMany):
	global i2c
	while (1 <= i2c.available()): # loop through all 
	    c = i2c.read() 			  # receive the character
	    print c         		  # print the character

i2c = TwoWire (myFunction)		  # creates a new TwoWire instance
i2c.begin (8)					  # join I2C bus as slave with address no. 8
i2c.onReceive(receiveEvent) 	  # register event
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 		// imports wyliodrin module

// creates a new TwoWire instance
var i2c = new wyliodrin.TwoWire (function (){
	console.log ('object created');
});	

i2c.begin (8);					  			// join I2C bus as slave with address no. 8

i2c.onReceive(function (howMany){			// register event
	while (1 <= i2c.available()) 			// loop through all 
	{
	    c = i2c.read(); 			  		// receive the character
	    console.log (c);         		    // print the character
	}
});
```

C/C++:
```
#include <Wyliodrin.h>				//imports wyliodrin library

void receiveEvent(int howMany) 
{
  int c;
  while (1 < Wire.available()) 		// loop through all
  { 
    c = Wire.read(); 				// receive the character
    printf ("%d\n", c);         	// print the character
}

int main()
{
	uint8_t status;
	size_t written;

	Wire.begin (8);					// join I2C bus as slave with address no. 8
	Wire.onReceive(receiveEvent); 	// register event
	return 0;
}
```

##read()
_**Description**_  
Reads a byte that was transmitted from a slave device to a master after a call to [requestFrom()](#requestfrom) or was transmitted from a master to a slave.

_**Syntax**_  
read()

_**Parameters**_  
None

_**Returns**_  
the next byte received (int)

_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

def myFunction ():
	print 'object created'

def receiveEvent (howMany):
	global i2c
	while (1 <= i2c.available()): # loop through all 
	    c = i2c.read() 			  # receive the character
	    print c         		  # print the character

i2c = TwoWire (myFunction)		  # creates a new TwoWire instance
i2c.begin (8)					  # join I2C bus as slave with address no. 8
i2c.onReceive(receiveEvent) 	  # register event
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 		// imports wyliodrin module

// creates a new TwoWire instance
var i2c = new wyliodrin.TwoWire (function (){
	console.log ('object created');
});	

i2c.begin (8);					  			// join I2C bus as slave with address no. 8

i2c.onReceive(function (howMany){			// register event
	while (1 <= i2c.available()) 			// loop through all 
	{
	    c = i2c.read(); 			  		// receive the character
	    console.log (c);         		    // print the character
	}
});
```

C/C++:
```
#include <Wyliodrin.h>				// imports wyliodrin library

void receiveEvent(int howMany) 
{
  int c;
  while (1 < Wire.available()) 		// loop through all
  { 
    c = Wire.read(); 				// receive the character
    printf ("%d\n", c);         	// print the character
}

int main()
{
	uint8_t status;
	size_t written;

	Wire.begin (8);					// join I2C bus as slave with address no. 8
	Wire.onReceive(receiveEvent); 	// register event
	return 0;
}
```
##peek()
_**Description**_  
Prints a byte that was transmitted from a slave device to a master after a call to [requestFrom()](#requestfrom) or was transmitted from a master to a slave.  
NOTE: The byte is not read, it remains in the buffer until [read()](#read) is called.

_**Syntax**_  
peek()

_**Parameters**_  
None

_**Returns**_  
the next byte received (int)

_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

def myFunction ():
	print 'object created'

def receiveEvent (howMany):
	global i2c
	c = i2c.peek ()
	print c
	while (1 <= i2c.available()): # loop through all 
	    c = i2c.read() 			  # receive the character
	    print c         		  # print the character

i2c = TwoWire (myFunction)		  # creates a new TwoWire instance
i2c.begin (8)					  # join I2C bus as slave with address no. 8
i2c.onReceive(receiveEvent) 	  # register event
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 		// imports wyliodrin module

// creates a new TwoWire instance
var i2c = new wyliodrin.TwoWire (function (){
	console.log ('object created');
});	

i2c.begin (8);					  			// join I2C bus as slave with address no. 8

i2c.onReceive(function (howMany){			// register event
	var c = i2c.peek ();
	console.log (c);
	while (1 <= i2c.available()) 			// loop through all 
	{
	    c = i2c.read(); 			  		// receive the character
	    console.log (c);         		    // print the character
	}
});
```

C/C++:
```
#include <Wyliodrin.h>				// imports wyliodrin library

void receiveEvent(int howMany) 
{
  int c;
  c = Wire.peek ();
  printf ("%d\n", c);
  while (1 < Wire.available()) 		// loop through all
  { 
    c = Wire.read(); 				// receive the character
    printf ("%d\n", c);         	// print the character
}

int main()
{
	uint8_t status;
	size_t written;

	Wire.begin (8);					// join I2C bus as slave with address no. 8
	Wire.onReceive(receiveEvent); 	// registers event
	return 0;
}
```

##onReceive()
_**Description**_  
Registers a function to be called when a slave device receives a transmission from a master.

_**Syntax**_  
onReceive(handler)

_**Parameters**_  
- handler: the function to be called when the slave receives data; this should take a single int parameter (the number of bytes read from the master) and return nothing.

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

def myFunction ():
	print 'object created'

def receiveEvent (howMany):
	global i2c
	while (1 <= i2c.available()): # loop through all 
	    c = i2c.read() 			  # receive the character
	    print c         		  # print the character

i2c = TwoWire (myFunction)		  # creates a new TwoWire instance
i2c.begin (8)					  # join I2C bus as slave with address no. 8
i2c.onReceive(receiveEvent) 	  # register event
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 		// imports wyliodrin module

// creates a new TwoWire instance
var i2c = new wyliodrin.TwoWire (function (){
	console.log ('object created');
});	

i2c.begin (8);					  			// join I2C bus as slave with address no. 8

i2c.onReceive(function (howMany){			// register event
	while (1 <= i2c.available()) 			// loop through all 
	{
	    c = i2c.read(); 			  		// receive the character
	    console.log (c);         		    // print the character
	}
});
```

C/C++:
```
#include <Wyliodrin.h>				// imports wyliodrin library

void receiveEvent(int howMany) 
{
  int c;
  while (1 < Wire.available()) 		// loop through all
  { 
    c = Wire.read(); 				// receive the character
    printf ("%d\n", c);         	// print the character
}

int main()
{
	uint8_t status;
	size_t written;

	Wire.begin (8);					// join I2C bus as slave with address no. 8
	Wire.onReceive(receiveEvent); 	// registers event
	return 0;
}
```

##onRequest()
_**Description**_  
Register a function to be called when a master requests data from this slave device.

_**Syntax**_  
onRequest(handler)

_**Parameters**_  
- handler: the function to be called, takes no parameters and returns nothing.

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

def myFunction ():
	print 'object created'

def requestEvent ():
	global i2c
	i2c.write ('a')				  # sends character to master

i2c = TwoWire (myFunction)		  # creates a new TwoWire instance
i2c.begin (8)					  # join I2C bus as slave with address no. 8
i2c.onRquest(requestEvent) 	  	  # registers event
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 		// imports wyliodrin module

// creates a new TwoWire instance
var i2c = new wyliodrin.TwoWire (function (){
	console.log ('object created');
});	

i2c.begin (8);					  			// join I2C bus as slave with address no. 8

i2c.onRequest(function (){					// registers event
	i2c.write ('a');						// send character to master
});
```

C/C++:
```
#include <Wyliodrin.h>				// imports wyliodrin library

void requestEvent() 
{
  Wire.write ("a");					// sends character to master
}

int main()
{
	uint8_t status;
	size_t written;

	Wire.begin (8);					// join I2C bus as slave with address no. 8
	Wire.onRequest(requestEvent); 	// register event
	return 0;
}
```