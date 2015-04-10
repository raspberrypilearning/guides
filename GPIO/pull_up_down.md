## Pull Up or Pull Down
In this lesson we are going to make a very basic switch and program the Raspberry Pi to detect its position. The switch could actually just be two jumper wires that you touch together, or it could be a button if you have them. If they are touching the switch is closed, and if not the switch is open.

![](images/jumpers.jpg)

In the previous lesson we learnt about the concept of `HIGH` and `LOW`. When a GPIO pin is in input mode the pin is said to be *floating*, meaning that it has no fixed voltage level. That's no good for what we want, as the pin will randomly float between `HIGH` and `LOW`. We need to know for sure that the wires have touched. So we need to fix the voltage level to `HIGH` or `LOW`, and then make it change *only* when the we touch the wires together.

We can do this in two ways:

- A [pull up circuit](images/pull_up.png) pulls the voltage up to 3.3 volts and reads as `HIGH` by default. When the button is pressed the voltage drops to `LOW`.

- A [pull down circuit](images/pull_up.png) pulls the voltage down to 0 volts and reads as `LOW` by default. When the button is pressed the voltage jumps to `HIGH`.

Fortunately, the Raspberry Pi has built-in versions of all the above circuitry. It can be helpful to imagine that the two resistors `R1` and `R2` from the diagrams above are *inside* the circuitry of the Raspberry Pi, and they can be enabled or disabled as we desire. We can select either a pull up or a pull down *in our code* for each GPIO pin.
