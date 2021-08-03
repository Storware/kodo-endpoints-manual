# Sizing Guide

There are two types of people: those who are doing backups, and those who will be doing them. But just **doing** backups is not everything. To avoid unnecessary surprises the best strategy is to **plan** your backup environment/procedure **before implementing** it. In this section, we've collected guides that you may find useful as you think about your KODO for Endpoints implementation.

The sizing guide describes requirements for a virtual or physical machine to install KODO for Endpoints server with IBM Spectrum Protect server.

First, you need to gather information about the total amount of data to be protected in your environment. This can be a daunting task when it comes to endpoint protection, but you have to make some assumptions because the amount of data to protect is different on each workstation or laptop.

To calculate the required backup storage space, multiply the number of devices you own by the assumed average amount of data per device and divide by 2 \(the assumed deduplication and compression ratio 2:1\). This is our recommendation, but the deduplication ratio may vary depending on the data characteristic of the devices.

The other requirement is to calculate the disk space required to store information about protected files in the IBM Spectrum Protect server database.

We've made a sample calculation for the database storage. If a single client has 500k files to protect and each file has 3 versions, then the protected environment with 500 endpoints requires about 1.7 TB of additional storage for the database. Reserve appropriate database disk space on the server.

Based on our best practice, we have prepared four configurations that are typical of most use cases.

Browse the next sections and find the appropriate system configuration that fits your organization size.

{% hint style="info" %}
The maximum number of endpoints protected by a single instance of KODO for Endpoints server is 25,000. If your organization has more endpoints to protect, please install another instance of KODO for Endpoints server.
{% endhint %}





