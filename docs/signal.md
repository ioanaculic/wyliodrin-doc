##sendSignal()
_**Description**_  
Sends a signal represented by name and value to Wyliodrin's dashboard.  
NOTE: The function works with Wyliodrin IDE.

_**Syntax**_  
sendSignal (name, value)

_**Parameters**_  
- name: the name of the signal (const char *);  
- value: the value of the signal (double).  

_**Returns**_  
the error code (0 for success) (int)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

sendSignal ('line', 0.5)	# sends signal with name line and value 0.5
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

wyliodrin.sendSignal ('line', 0.5);		// sends signal with name line and value 0.5
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	sendSignal ("line", 0.5);	// sends signal with name line and value 0.5
	return 0;
}
```

##sendSignalAndFlag()
_**Description**_  
Sends a signal represented by name and value to Wyliodrin's dashboard and puts a flag on the graph.  
NOTE: The function works with Wyliodrin IDE.

_**Syntax**_  
sendSignalAndFlag (flag, name, value)

_**Parameters**_
- flag: the name of the flag that appears on the graph (const char *);    
- name: the name of the signal (const char *);  
- value: the value of the signal (double).  

_**Returns**_  
the error code (0 for success) (int)

_**Example**_  
Python:
``` 
from wyliodrin import * 					# imports wyliodrin module

# sends signal with name line and value 0.5 and puts a flag with name myFlag on the graph
sendSignalAndFlag ('myFlag', 'line', 0.5)	
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 		// imports wyliodrin module

// sends signal with name line and value 0.5 and puts a flag with name myFlag on the graph
wyliodrin.sendSignalAndFlag ('myFlag', 'line', 0.5);	
```

C/C++:
```
#include <Wyliodrin.h>							// imports wyliodrin library

int main()
{
	// sends signal with name line and value 0.5 and puts a flag with name myFlag on the graph
	sendSignalAndFlag ("flag", "line", 0.5);	
	return 0;
}
```

##sendSignalsAndFlag()
_**Description**_  
Sends multiple signals represented by name and value to Wyliodrin's dashboard and puts a flag on the graph.  
NOTE: The function works with Wyliodrin IDE and only for C/C++.

_**Syntax**_  
sendSignalsAndFlag(flag, name1, value1, name2, value2, ...)

_**Parameters**_
- flag: the name of the flag that appears on the graph (const char *);    
- nameX: the name of the signal X (const char *);  
- valueX: the value of the signal X (double).  

_**Returns**_  
the error code (0 for success) (int)

_**Example**_  
C/C++:
```
#include <Wyliodrin.h>		// imports wyliodrin library

int main()
{
	
	// sends one signal with name line and value 0.5 and another with name temperature and value 15.7 
	// and puts a flag with name myFlag on the graph
	sendSignalsAndFlag ("myFlag", "line", 0.5, "temperature", 15.7);	
	return 0;
}
```

##sendSignals()
_**Description**_  
Sends multiple signals represented by name and value to Wyliodrin's dashboard.  
NOTE: The function works with Wyliodrin IDE and only for C/C++.

_**Syntax**_  
sendSignals(name1, value1, name2, value2, ...)

_**Parameters**_   
- nameX: the name of the signal X (const char *);  
- valueX: the value of the signal X (double).  

_**Returns**_  
the error code (0 for success) (int)

_**Example**_  
C/C++:
```
#include <Wyliodrin.h>		// imports wyliodrin library

int main()
{	
	// sends one signal with name line and value 0.5 and another with name temperature
	// and value 15.7 
	sendSignals ("line", 0.5, "temperature", 15.7);	
	return 0;
}
```

##putFlag()
_**Description**_  
Attaches a flag to a signal on the graph.  
NOTE: The function works with Wyliodrin IDE.

_**Syntax**_  
putFlag(name, flag)

_**Parameters**_   
- name: the name of the signal the flag is attached to (const char *);  
- value: the of the flag that appears on the graph (const char *).  

_**Returns**_  
the error code (0 for success) (int)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

putFlag ('line', myFlag)	# puts the flag myFlag on the graph which displays the line signal	
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

wyliodrin.putFlag ('line', myFlag);		// puts the flag myFlag on the graph which displays the line signal		
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	
	putFlag ("line", myFlag);  // puts the flag myFlag on the graph which displays the line signal	
	return 0;
}
```

##sendSignalsList()
_**Description**_  
Sends a list of signals to the dashboard. The list of signal labels and values should have the same number of elements.  
NOTE: The function works with Wyliodrin IDE.

_**Syntax**_  
sendSignalsList(names, values, elements)

_**Parameters**_   
- names: a list with the names of the signals (const char **);  
- values: a list with the values of the signals (double *);  
- elements: the length of the lists (int).  

_**Returns**_  
the error code (0 for success) (int)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

# sends one signal with name line and value 1.5 
# and another with name temperature and value 17.9
sendSignalsList (['line', 'temperature'], [1.5, 17.9], 2)
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

// sends one signal with name line and value 1.5 
// and another with name temperature and value 17.9
wyliodrin.sendSignalsList (['line', 'temperature'], [1.5, 17.9], 2);
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	const char names [2] = {"line", "temperature"};
	double values [2] = {1.5, 17.9};
	// sends one signal with name line and value 1.5 
	// and another with name temperature and value 17.9
	sendSignalsList (names, values, 2);	
	return 0;
}
```

##sendSignalsListAndFlag()
_**Description**_  
Sends a list of signals to the dashboard and puts a flag on the graphs. The list of signal labels and values should have the same number of elements.  
NOTE: The function works with Wyliodrin IDE.

_**Syntax**_  
sendSignalsList(flag, names, values, elements)

_**Parameters**_   
- flag: the name of the flag that appears on the graph (const char *);  
- names: a list with the names of the signals (const char **);  
- values: a list with the values of the signals (double *);  
- elements: the length of the lists (int).  

_**Returns**_  
the error code (0 for success) (int)

_**Example**_  
Python:
``` 
from wyliodrin import * 	# imports wyliodrin module

# sends one signal with name line and value 1.5 
# and another with name temperature and value 17.9
# and puts the flag myFlag on both graphs
sendSignalsListAndFlag ('myFlag', ['line', 'temperature'], [1.5, 17.9], 2)
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

// sends one signal with name line and value 1.5 
// and another with name temperature and value 17.9
// and puts the flag myFlag on both graphs
wyliodrin.sendSignalsList ('myFlag', ['line', 'temperature'], [1.5, 17.9], 2);
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	const char names [2] = {"line", "temperature"};
	double values [2] = {1.5, 17.9};
	// sends one signal with name line and value 1.5 
	// and another with name temperature and value 17.9
	// and puts the flag myFlag on both graphs
	sendSignalsList ("myFlag", names, values, 2);	
	return 0;
}
```

##sendCoordinates()
_**Description**_  
Sends a signal described by latitude and longitude to be displayed on a maps dashboard element.   
NOTE: The function works with Wyliodrin IDE.

_**Syntax**_  
sendCoordinates(name, latitude, longitude)

_**Parameters**_   
- name: the name of the signal (const char *);  
- latitude: the latitude to be displayed on the maps (double);  
- longitude: the longitude to be displayed on the maps (double).

_**Returns**_  
the error code (0 for success) (int)

_**Example**_  
Python:
``` 
from wyliodrin import * 			# imports wyliodrin module

# places a point on the map, at latitude 45.5 and longitude 21.54
sendCoordinates ('coord', 45.5, 21.45)	
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

// places a point on the map, at latitude 45.5 and longitude 21.54
wyliodrin.sendCoordinates ('coord', 45.5, 21.45);
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	// places a point on the map, at latitude 45.5 and longitude 21.54
	sendCoordinates ('coord', 45.5, 21.45);	
	return 0;
}
```

##sendCoordinatesAndFlag()
_**Description**_  
Sends a signal described by latitude and longitude to be displayed on a maps dashboard element and also puts a flag.   
NOTE: The function works with Wyliodrin IDE.

_**Syntax**_  
sendCoordinates(name, latitude, longitude, flag)

_**Parameters**_   
- name: the name of the signal (const char *);  
- latitude: the latitude to be displayed on the maps (double);  
- longitude: the longitude to be displayed on the maps (double);  
- flag: the name of the flag that appears on the maps.

_**Returns**_  
the error code (0 for success) (int)

_**Example**_  
Python:
``` 
from wyliodrin import * 			# imports wyliodrin module

# places a point on the map, at latitude 45.5 and longitude 21.54
# and puts the flag myPoint at that coordinates
sendCoordinatesAndFlag ('coord', 45.5, 21.45, 'myPoint')	
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

// places a point on the map, at latitude 45.5 and longitude 21.54
// and puts the flag myPoint at that coordinates
wyliodrin.sendCoordinatesAndFlag ('coord', 45.5, 21.45, 'myPoint');
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	// places a point on the map, at latitude 45.5 and longitude 21.54
	// and puts the flag myPoint at that coordinates
	sendCoordinatesAndFlag ('coord', 45.5, 21.45, 'myPoint');	
	return 0;
}
```

##sendSignalXY()
_**Description**_  
Sends a signal described by two coordinates.     
NOTE: The function works with Wyliodrin IDE.

_**Syntax**_  
sendSignalXY(name, x, y)

_**Parameters**_   
- name: the name of the signal (const char *);  
- x: the x coordinate of the signal (double);  
- y: the y coordinate of the signal; y is considered the timestamp of the value x (double).  

_**Returns**_  
the error code (0 for success) (int)

_**Example**_  
Python:
``` 
from wyliodrin import * 			# imports wyliodrin module

# sends a signal with name myLine and defined by values 3 and 15.5
sendSignalXY ('myLine', 3, 15.5)
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

// sends a signal with name myLine and defined by values 3 and 15.5
wyliodrin.sendSignalXY ('myLine', 3, 15.5);
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	// sends a signal with name myLine and defined by values 3 and 15.5
	sendSignalXY ('myLine', 3, 15.5);
	return 0;
}
```

##sendSignalXYAndFlag()
_**Description**_  
Sends a signal described by two coordinates and puts a flag on the graph.     
NOTE: The function works with Wyliodrin IDE.

_**Syntax**_  
sendSignalXY(name, x, y, flag)

_**Parameters**_   
- name: the name of the signal (const char *);  
- x: the x coordinate of the signal (double);  
- y: the y coordinate of the signal; y is considered the timestamp of the value x (double);  
= flag: the name of the flag that appears on the graph.  

_**Returns**_  
the error code (0 for success) (int)

_**Example**_  
Python:
``` 
from wyliodrin import * 			# imports wyliodrin module

# sends a signal with name myLine and defined by values 3 and 15.5
# and puts the flag myFlag on the graph
sendSignalXYAndFlag ('myLine', 3, 15.5, 'myFlag')
```

JavaScript:
```
var wyliodrin = require ('wyliodrin'); 	// imports wyliodrin module

// sends a signal with name myLine and defined by values 3 and 15.5
// and puts the flag myFlag on the graph
wyliodrin.sendSignalXYAndFlag ('myLine', 3, 15.5, 'myFlag');
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	// sends a signal with name myLine and defined by values 3 and 15.5
	// and puts the flag myFlag on the graph
	sendSignalXYAndFlag ('myLine', 3, 15.5, 'myFlag');
	return 0;
}
```