Device 1 is low on battery - it sends a signal to the transponder

The transponder will keep track of power levels, safe power constants, and inform the relay to transmit intervals

transponder recieves device location - on device location change, it sends the update to the transponder
this way no excessive data nor power is lost

relay sends power to device

if device no longer needs power, it sends a drop connection to transponder

if there is a remainder power data towards the device, subtract it

if there are any devices left, iterate through another power cycle

if there are no devices left, put transponder into a low-power state, until another device sends an activation signal

relay sends no (send) signal until transponder activates it

likewise with a transponder sends no (send) signal until a device activates it

only the relative location of the devices will be transmitted to, but the transponder can recieve from any direction
