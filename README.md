# Rubrik_Quotas
Rubrik quotas functionality for Rubrik CDM 5.1.x & 5.2 
Tested using python 3.7.7 & 3.8.1

## Description

Script use is designed to give quotas funcationality on Rubrik CDM. The script has 'soft' and 'hard' limits. 

A soft limit 'slimits' will send an email out to an administrator of the Rubrik CDM platform wwarning that the soft threshold has been reached or exceeded. 

A hard limit 'hlimits' will pause the SLA's which have passed the threshold, resulting in no more backup jobs running to that SLA(s).

In order to test without pausing SLA's on a Rubrik cluster # line 61 'sla_pause'

## Variables to Configure 

Define soft and hard thresholds, these are calculated as a percentage of the total available storage of the Rubrik cluster

Confgure email settings for email message out if in breach of soft limits. Note in this version of the script it leverages https://mailtrap.io/ using 'smtplib'

# 📘 Documentation

This script leverages Rubrik CDM python_sdk and rubrik_cdm module will need to be loaded as per below:

Install from pip:

`pip install rubrik_cdm`

Install from source:
```
$ git clone https://github.com/rubrikinc/rubrik-sdk-for-python
$ cd rubrik-sdk-for-python
$ python setup.py install
```
Here are some resources to get you started! If you find any challenges from this project are not properly documented or are unclear, please [raise an issue](https://github.com/rubrikinc/rubrik-sdk-for-python/issues/new/choose)

* [Quick Start Guide](https://github.com/rubrikinc/rubrik-sdk-for-python/blob/master/docs/quick-start.md)
* [SDK for Python Documentation](https://rubrik.gitbook.io/rubrik-sdk-for-python/)
* [Rubrik API Documentation](https://github.com/rubrikinc/api-documentation)
* [VIDEO: Getting Start with the Rubrik SDK for Python](https://www.youtube.com/watch?v=wd1PxPOd3f8&feature=youtu.be)
* [BLOG: Hello World! Welcoming Rubrik’s Python SDK](https://www.rubrik.com/blog/introducing-rubrik-python-sdk/)

# :mag: Example

By default, the Rubrik SDK will attempt to read the the Rubrik Cluster credentials from the following environment variables:

* `rubrik_cdm_node_ip`
* `rubrik_cdm_username`
* `rubrik_cdm_password`
* `rubrik_cdm_token`

| Note: The `rubrik_cdm_username` and `rubrik_cdm_password` must be supplied together and may not be provided if the `rubrik_cdm_token` variable is present|
| --- |

```py
import rubrik_cdm
rubrik = rubrik_cdm.Connect()

cluster_version = rubrik.cluster_version()

print(cluster_version)


```

