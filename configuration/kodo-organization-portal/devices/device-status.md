# Device status

Each device registered in the system has a suitable status defining its current state.

Possible device status in the system:

* **Protected** ![](../../../.gitbook/assets/protected.png)  The status is presented with a green V symbol. This indicates that the device is active and that the device's last communication time did not exceed the value given in the policy assigned to the device owner.
* **Not protected** ![](../../../.gitbook/assets/unprotected.png)  The status is represented by the red triangle icon. This indicates that the device is active, but the last communication time of the device has exceeded the value specified in the policy assigned to the device owner.
* **Locked** ![](../../../.gitbook/assets/locked.png)  The status is presented with a red padlock icon. This indicates that the device is locked and the backup or restore operations cannot be performed.



## Protection statuses <a id="device-statuses"></a>

| **Status** |  | **Description** |
| :--- | :--- | :--- |
| Protected  | ![](../../../.gitbook/assets/protected.png) | The device is protected according to the assigned policy |
| Not protected ![](../../../.gitbook/assets/unprotected.png) |  | The device didn't connect with the server within the last "X" days. The number of days is configured at a policy level. |
| Locked ![](../../../.gitbook/assets/locked.png) |  | The device is locked. The user cannot log in and perform any operations from this device. |

![](../../../.gitbook/assets/image%20%28103%29.png)

![](../../../.gitbook/assets/image%20%28107%29.png)

