##initCommunication()
_**Description**_  
Initialises the communication module. This function should be called only once, before sending and receiving messages. 
NOTE: The function works with Wyliodrin IDE and only for C/C++ and Python.

_**Syntax**_  
initCommunication()

_**Parameters**_   
None

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

initCommunication ()
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	initCommunication ();
	return 0;
}
```

##sendMessage()
_**Description**_  
Sends a message from one board to any board connected to Wyliodrin. 
NOTE: The function works with Wyliodrin IDE and only for C/C++ and Python.

_**Syntax**_  
sendMessage(to, label, message)

_**Parameters**_   
- to: the ID of the board you wish to send the message to. You find that on Wyliodrin’s
home page. Go to your board and, if you click on the settings, you will find Board ID. Copy and paste the receiver board’s ID (const char *);  
- label: the communication channel’s identifier (const char *);  
- message: the message to be sent (const char *).

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

initCommunication ()
sendMessage ('username_board@wyliodrin.com', 'buttons', 'pressed')
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	initCommunication ();
	sendMessage ('username_board@wyliodrin.com', 'buttons', 'pressed');
	return 0;
}
```

##setHandlerForLabel()
_**Description**_  
Assigns a function to be called when a messeg with a certain label is received. Note that the function does not wait for messages, you need to call #waitformessages to do that. 
NOTE: The function works with Wyliodrin IDE and only for C/C++ and Python.

_**Syntax**_  
setHandlerForLabel(label, handlerFunction)

_**Parameters**_   
- label: the communication channel’s identifier (const char *);  
- handlerFunction: the function to be called once a message is received; the function returns nothing and takes the following parameters: 
	- sender: the ID of the board sending the message (const char *);  
	- label: the communication channel's indentifier (const char *);  
	- error: the error code, 0 if no error occured (int);  
	- data: the received message (const char *).

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

initCommunication ()

def myFunction (sender, channel, error, message):
# check the message is from the right source,
# ignores all other messages that might appear
  if (sender == 'username_board@wyliodrin.com'): 
  	print ('message: ' + message)

setHandlerForLabel ('buttons', myFunction)
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

void myFunction (sender, channel, error, message)
{
// check the message is from the right source,
// ignores all other messages that might appear
  if (strncmp(sender, "username_board@wyliodrin.com", 20) == 0)
  	printf ("message: %s", message);
}

int main()
{
	initCommunication ();

	setHandlerForLabel ("buttons", myFunction);
	return 0;
}
```

##clearHandlerForLabel()
_**Description**_  
Remove the handler set for a label.  
NOTE: The function works with Wyliodrin IDE and only for C/C++ and Python.

_**Syntax**_  
clearHandlerForLabel(label)

_**Parameters**_   
- label: the communication channel’s identifier (const char *).

_**Returns**_  
None

_**Example**_  
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

initCommunication ()

clearHandlerForLabel ('buttons')
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

int main()
{
	initCommunication ();

	clearHandlerForLabel ("buttons");
	return 0;
}
```

##waitForMessages()
_**Description**_  
It waits for messages from any other board connected to Wyliodrin to be received for a certain number of seconds.
NOTE: The function works with Wyliodrin IDE and only for C/C++ and Python.

_**Syntax**_  
waitForMessages (seconds)

_**Parameters**_   
- seconds: the number of seconds to wait; if it is zero or negative, the function will block until the user manually kills the process (int).

_**Returns**_  
None

_**Example**_   
Python:
``` 
from wyliodrin import * 		# imports wyliodrin module

initCommunication ()

def myFunction (sender, channel, error, message):
# check the message is from the right source,
# ignores all other messages that might appear
  if (sender == 'username_board@wyliodrin.com'): 
  	print ('message: ' + message)

setHandlerForLabel ('buttons', myFunction)
waitForMessages (-1)
```

C/C++:
```
#include <Wyliodrin.h>			// imports wyliodrin library

void myFunction (sender, channel, error, message)
{
// check the message is from the right source,
// ignores all other messages that might appear
  if (strncmp(sender, "username_board@wyliodrin.com", 20) == 0)
  	printf ("message: %s", message);
}

int main()
{
	initCommunication ();

	setHandlerForLabel ("buttons", myFunction);
	waitForMessages (-1);
	return 0;
}
```