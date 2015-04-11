## Pull Up or Pull Down

When a GPIO pin is in input mode the pin is said to be *floating*, meaning that it has no fixed voltage level. The pin will randomly float between `HIGH` and `LOW`. On occasion you might need to fix the voltage level to `HIGH` or `LOW`, for example when...

You can do this in two ways:

- A [pull up circuit](images/pull_up.png) pulls the voltage up to 3.3 volts and reads as `HIGH` by default. When the button is pressed the voltage drops to `LOW`.

- A [pull down circuit](images/pull_up.png) pulls the voltage down to 0 volts and reads as `LOW` by default. When the button is pressed the voltage jumps to `HIGH`.

Fortunately, the Raspberry Pi has built-in versions of all the above circuitry. It can be helpful to imagine that the two resistors `R1` and `R2` from the diagrams above are *inside* the circuitry of the Raspberry Pi, and they can be enabled or disabled as we desire. We can select either a pull up or a pull down *in our code* for each GPIO pin.
