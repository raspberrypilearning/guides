## Capturing video with Python

1. Modify your program to record video instead:

    ```python
    import time
    import picamera
    import RPi.GPIO as GPIO

    GPIO.setmode(GPIO.BCM)
    GPIO.setup(17, GPIO.IN, GPIO.PUD_UP)

    with picamera.PiCamera() as camera:
        camera.start_preview()
        GPIO.wait_for_edge(17, GPIO.FALLING)
        camera.start_recording('/home/pi/Desktop/video.h264')
        time.sleep(1)
        GPIO.wait_for_edge(17, GPIO.FALLING)
        camera.stop_recording()
        camera.stop_preview()
    ```

2. Save and run your script
3. Press the button to start recording video; press it again to stop and exit the program
