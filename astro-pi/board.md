# Astro Pi - What is it?

The Astro Pi board is a HAT board for the Raspberry Pi which has the ability to sense a wide variety of conditions and provide output via the built-in LED matrix. Two Astro Pi will be travelling to the International Space Station (ISS) with British ESA astronaut Tim Peake. You can find out more about the mission and the board by watching the official Astro Pi competition video:

[![Astro PI Competition](https://i.vimeocdn.com/video/504039170_640.webp)](https://vimeo.com/117274487)

And here is NASA astronaut Reid Wiseman giving a fly-through tour of the ISS

[![Fly through of the weather station](http://img.youtube.com/vi/kVK20xyfPrU/0.jpg)](https://www.youtube.com/watch?v=kVK20xyfPrU)

## What's on the board?
1. Let's take a tour of the main features of the Astro Pi sensor board.
  ![Astro Pi Board Features](images/astro_pi_features.jpg)
1. The main features of concern to you are highlighted in red.
    - The LED matrix on the left has 64 [light emitting diodes](http://en.wikipedia.org/wiki/Light-emitting_diode) (LEDs) arranged in an 8 x 8 grid. On board the ISS the Astro Pi cannot be connected to a screen, they only have laptops, so these LEDs are acting as its display. They can be used to display shapes, icons and messages to the crew of the ISS.
    - Next is the [inertial measurement unit](http://en.wikipedia.org/wiki/Inertial_measurement_unit) (IMU). All space craft have these, they're very important for space flight. It's the small microchip just above the text `ACCEL/GYRO/MAG` on the Astro Pi. It's actually three sensors in one:
        - An accelerometer to measure the force of acceleration (like in a Wiimote)
        - A gyroscope to measure orientation (so you know which way you're pointing)
        - A magnetometer to measure the Earth's magnetic field (like a compass)

    So this is basically a movement sensor and will allow you to measure how you're moving the Astro Pi in your hand or, in space, how the ISS itself is moving.
    - Next is a [humidity](http://en.wikipedia.org/wiki/Humidity) sensor. This will allow you to measure air moisture. It's the small chip just below the text `HUMIDITY`. You can also use it to measure ambient temperature.
    - There is also a [ pressure](http://en.wikipedia.org/wiki/Atmospheric_pressure) sensor for measuring air pressure. Something which is certainly of concern in space. It's the chip to the right of the text `PRESSURE`.
    - Last but not least is the joystick. The Astro Pi cannot be connected to a USB keyboard or mouse in space either so it has its own five button joystick. This is the silver rectangle in the bottom right corner with the small stick poking out of the top. It can do up, down, left, right and middle clicks.
