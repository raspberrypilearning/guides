## Countdown capture (selfies!) in Python

1. Modify your program to include the delay after the button wait:

    ```python
    import time
    import picamera
    import RPi.GPIO as GPIO

    GPIO.setmode(GPIO.BCM)
    GPIO.setup(17, GPIO.IN, GPIO.PUD_UP)

    with picamera.PiCamera() as camera:
        camera.start_preview()
        GPIO.wait_for_edge(17, GPIO.FALLING)
        time.sleep(5)  # new
        camera.capture('/home/pi/Desktop/image.jpg')
        camera.stop_preview()
    ```

2. Delete `image.jpg` from the desktop
3. Save and run your script
4. Press the button and try to take a selfie
