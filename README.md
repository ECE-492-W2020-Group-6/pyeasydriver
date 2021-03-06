Simple software driver for stepper motors controlled by the SparkFun EasyDriver motor controller board.

# Install

`pip install pyeasydriver`

# Usage

```python
from pyeasydriver.easydriver import EasyDriver, StepDirection
from gpiozero import Device
from gpiozero.pins.rpigpio import RPiGPIOFactory
import RPi.GPIO as rpigpio

rpigpio.setmode(rpigpio.BCM)
rpigpio.setwarnings(False)

Device.pin_factory = RPiGPIOFactory()

if __name__ == "__main__":
    STEP_PIN = 20
    DIR_PIN = 21
    ENABLE_PIN = 25
    MS1_PIN = 24
    MS2_PIN = 23


    driver = EasyDriver(step_pin=self.STEP_PIN,
                dir_pin=self.DIR_PIN, 
                ms1_pin=self.MS1_PIN, 
                ms2_pin=self.MS2_PIN,
                enable_pin=self.ENABLE_PIN)

    driver.step(200, direction=StepDirection.FORWARD)
    driver.step(200, direction=StepDirection.REVERSE)
```
