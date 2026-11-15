# VL53L9 person detection

End-to-end binary person-presence classifier (person / no person) running on-device
using depth data from the VL53L9CX direct ToF sensor.

**Hardware:** STEVAL-VL53L9 evaluation board on an STM32 NUCLEO-N657X0. The STM32N6's
Neural-ART NPU runs the model on-device. The STEVAL board also supports the STM32N6570-DK.

**Pipeline:** sensor bringup -> dataset collection and labeling -> model training ->
quantization (ST Edge AI if needed) -> deployment and on-target evaluation.

We use the STM32 NUCLEO-N657X0-Q because the STEVAL-VL53L9 is designed for it.
If this project is successful, it will be extended to more advanced methods.
