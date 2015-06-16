## Circular buffers with Python

1. Modify your program to continually record to a circular buffer, and write it to disk when the button is pressed:

    ```python
    import io
    import time
    import picamera
    import RPi.GPIO as GPIO

    GPIO.setmode(GPIO.BCM)
    GPIO.setup(17, GPIO.IN, GPIO.PUD_UP)

    with picamera.PiCamera() as camera:
        stream = picamera.PiCameraCircularIO(camera, seconds=20)
        camera.start_preview()
        camera.start_recording(stream, format='h264')
        GPIO.wait_for_edge(17, GPIO.FALLING)
        camera.stop_recording()
        camera.stop_preview()
        for frame in stream.frames:
            if frame.header:
                stream.seek(frame.position)
                break
        with io.open('/home/pi/Desktop/video.h264', 'wb') as output:
            while True:
                data = stream.read1()
                if not data:
                    break
                output.write(data)
    ```

2. Delete `video.h264` from the desktop
3. Save and run your script
4. Press the button to save the last 20+ seconds of video to the drive
