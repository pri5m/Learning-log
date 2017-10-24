
Bitwise operators work by performing operations on the binary representations of the values. They return the result back in decimal, so these steps are followed:

1. Bitwise operation (22 ^ 3)

2. Convert each value to binary

3. Perform the operation (using a truth table)

4. Convert back to decimal

# Why Are These Operations Useful?
What do you think it would be used for?

Bitwise operations in programming languages play a fundamental role when
dealing with a lot of applications, especially when bandwith is limited
and we want to send as little bytes as possible. Almost all low-level
computing must be done using this kind of operations.

In embedded computers, sensors and other IoT devices, we use flags to
relate to configuration, write drivers or as instructions for
microcontrollers.

I.e. a bit relates to an individual setting.

1101 - sensor on, led on, power save off, Bluetooth connection on 1001 - sensor on, led off,
power save off, Bluetooth connection on
