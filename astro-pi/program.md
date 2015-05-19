# Astro Pi: first Program

1. Connect the Raspberry Pi peripherals (keyboard, mouse, monitor, and power).
1. Log in using the following login information:

  ```bash
  login: pi
  password: raspberry
  ```

  You will not see any text when typing the password; this is a security feature.
  
1. Load the graphical user interface by typing `startx`.
1. Open Python 3 using `Menu > Programming > Python 3`.
1. A Python Shell window will now appear.
1. Select `File > New Window`.
1. Type in the following code:

  ```python
  from astro_pi import AstroPi
  ap = AstroPi()
  ap.show_message("Hello my name is Tim Peake")
  ```

1. Select `File > Save` and choose a file name for your program.
1. Then select `Run > Run module`.
1. Your message should then scroll across the LED matrix in white text.
1. Feel free to change the message between the double quotation marks and run your code again.
