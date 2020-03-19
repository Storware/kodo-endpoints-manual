# Status of devices

Each device registered in the system has a suitable status defining its current state.

Possible device status in the system:

* **Protected** ![](../../.gitbook/assets/protected%20%281%29.png) Status presented with a green shield icon. Indicates that the device is active and that the device's last communication time did not exceed the value given in the policy assigned to the device owner.
* **Not protected** ![](../../.gitbook/assets/not_procted%20%281%29.png) Status represented by the red triangle icon. Indicates that the device is active, but the last communication time of the device has exceeded the value specified in the policy assigned to the device owner.
* **Waiting for activation** ![](../../.gitbook/assets/activate%20%281%29.png) Status presented by the red hourglass icon. Indicates that the device is inactive and is awaiting for activation by the administrator. Such status is assigned to each new registered device.
* **Locked** ![](../../.gitbook/assets/locked.png) Status presented with a red padlock icon. Indicates that the device is locked and cannot login.

