# Data encryption

In the policy configuration, you can turn on the option that will allow a user to encrypt data before sending to the server , encryption and key need to be configured on KODO client itself.

To encrypt protected data KODO is using the AES-256 algorithm.

If the backup copy of the user device has been encrypted, administrative data restore is no longer possible.

You can enable data encryption in `General` tab of `Policies` configuration by checking `Allow users to encrypt their data using own encryption key` option. ![](../../.gitbook/assets/encryption.png)

{% hint style="info" %}
Data encryption at rest is currently supported only on Windows platform only
{% endhint %}

