
# Minimal Micropython
This example uses the amazing library provided by [mcauser](https://github.com/mcauser/micropython-waveshare-epaper).
Currently the support is very limited.

## Micropython installation guide
### Step 1: Download the latest esptool
Download the latest esptool from [here](https://github.com/espressif/esptool/releases).
or use pip `pip3 install esptool`

### Step 2: Download micropython binary
Download the latest micropython binary from [here](https://micropython.org/download/esp32/).

### Step 3: Erase flash on paperd.ink
`esptool --chip esp32 --port <port> erase_flash`
Port is the port number you use for uploading code.
Could be `/dev/ttyUSB0` on linux, `/dev/ttyACM0` on mac or a COM port on windows.

### Step 3: Upload micropython
`esptool --chip esp32 --port <port> --baud 460800 write_flash -z 0x1000 <path to micropython bin>`

### Step 4: Open a serial terminal
Press reset button on the back of paperd.ink
Open a serial terminal at 115200 baud, you should see a python repl.

## Uploading code
### Step 1: Install [rshell](https://github.com/dhylands/rshell)
`pip3 install rshell`

### Step 2: Open rshell
Start rshell in the directory where your code is.
`rshell --buffer-size=30 -p <port> -a`

### Step 3: Upload code
The following command should be typed in rshell
`cp epaper4in2.py /pyboard/`
`cp boot.py /pyboard/`

### Step 4: Hit reset
After hitting reset you should be able to see the EPD update

## More detailed guides
1. [rshell](https://mitjafelicijan.com/esp8266-and-micropython-guide.html)
2. [uPyCraft IDE](https://randomnerdtutorials.com/getting-started-micropython-esp32-esp8266/)
