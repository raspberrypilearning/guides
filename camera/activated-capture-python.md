## Capture when activated in Python

1. Connect the Pi to the button as shown in the diagram below:

    ![](picamera-gpio-setup.png)

2. In the text editor, import the `RPi.GPIO` module, set up GPIO pin 17 and change the `sleep` line to use `GPIO.wait_for_edge` like so:

    ```python
    import time
    import picamera
    import RPi.GPIO as GPIO  # new

    GPIO.setmode(GPIO.BCM)  # new
    GPIO.setup(17, GPIO.IN, GPIO.PUD_UP)  # new

    with picamera.PiCamera() as camera:
        camera.start_preview()
        GPIO.wait_for_edge(17, GPIO.FALLING)  # new
        camera.capture('/home/pi/Desktop/image.jpg')
        camera.stop_preview()
    ```

3. Delete `image.jpg` from the desktop
4. Save and run your script
5. Once the preview has started, press the button connected to your Pi to capture an image
