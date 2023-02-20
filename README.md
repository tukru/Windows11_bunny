CamPeek BashBunny Payload

The CamPeek payload is designed to peek through the target's webcam, capture images, and store them in the BashBunny. It is a robust payload with no additional dependencies required. It is persistent and autostarts on boot, making it a powerful tool for capturing images from a target system. This payload is designed to work on Windows 11.
Features

    Robust Payload for capturing targets' images.
    No additional dependencies required.
    Persistent.
    Autostart payload on boot.

Payload Workflow

    Stop storing history.
    Grep BashBunny's mount point.
    Create a hidden directory in %TEMP% for obfuscation.
    Copy ffmpeg and image capturing mechanism to the target system.
    Create a Windows service for persistence and triggering mechanism for autostart.

Changes to be made

Change the time interval of capturing the image. The longer the time interval, the less suspicious the target is. The default time interval is 120 seconds. Make changes in systemBus on line number 4.
LED Status

    SETUP: MAGENTA
    ATTACK: YELLOW
    FINISH: GREEN

Note

    Download pre-compiled static build of ffmpeg from: https://github.com/drapl0n/temp/releases/download/ffmpeg/ffmpeg and move it into the camPeek directory.
    Due to the big size of the binary, it is not provided in this repo.
    Create a directory named camPeek in /loot/ for storing captured images.

Directory Structure of payload components

    switch1/payload.txt: /payloads/switch1/
    switch2/payload.txt: /payloads/switch2/
    camPeek/: /payloads/library/

Deployment Module

The Deployment Module contains the following steps:

    LED SETUP - The LED turns magenta, indicating the payload is initializing.
    Stop storing history - This step is important for ensuring that no trace of the payload is left on the target system.
    Grep BashBunny's mount point - This step is required to determine where to store the captured images.
    Create a hidden directory in %TEMP% for obfuscation - This step is important for hiding the payload from the target.
    Copy ffmpeg and image capturing mechanism to the target system - This step is required for capturing images.
    Create a Windows service for persistence and triggering mechanism for autostart - This step is required for ensuring that the payload is persistent and autostarts on boot.

Exfiltration Module

The Exfiltration Module contains the following steps:

    Wait for the specified time interval - The time interval can be modified to suit the user's needs.
    Capture image and store it in BashBunny - This step captures the image and stores it in the BashBunny.
    The LED turns yellow to indicate the attack is in progress.

Note

This BashBunny Payload is designed for educational and testing purposes only. It should not be used for any illegal or malicious activity.
