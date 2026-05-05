# Prisma SDWAN: Minimize Cellular Usage
This script is used to update circuit settings that minimize cellular usage. V 2.0


### Synopsis
This script can be used to update circuit settings to minimize cellular usage. 

It update the following settings for the circuit:
- Turn off application reachability probes
- Turn off controller connections
- Set VPN keepalives interval to 1740000 seconds
- Set keepalive failure count to 3
- Turn off bandwidth monitoring

This script can be used to update settings on one or more sites across one or more circuit labels


### Requirements
* SCM Account
* Python >=3.6
* Python modules:
    * Prisma SASE SDK
* ProgressBar2
* updating of the prismasase_settngs.py with your SCM API credentials

### License
MIT

### Installation:
 - **Github:** Download files to a local directory, manually run `cellularusage.py`. 

### Examples of usage:
Update settings for a single site on a single label:
```
./cellularusage.py -S Sitename -L "Ethernet Internet"
```
Update settings for a single site for multiple labels:
```
./cellularusage.py -S Sitename -L "Ethernet Internet, LTE"
```
Update settings for all sites for a single label:
```
./cellularusage.py -S ALL_SITES -L "Ethernet Internet"
```
Update settings for all sites for multiple labels:
``` 
./cellularusage.py -S ALL_SITES -L ALL_LABELS
```


### Help Text:
```angular2
Tanushrees-MacBook-Pro:cellularusage tanushreekamath$ ./cellularusage.py -h
usage: cellularusage.py [-h] [--print-lower] [--controller CONTROLLER] [--email EMAIL] [--password PASSWORD] [--insecure] [--noregion] [--sdkdebug SDKDEBUG] [--sitename SITENAME] [--label LABEL]

Minimize Cellular Usage (v1.0)

optional arguments:
  -h, --help            show this help message and exit

custom_args:
  My Custom Args

  --print-lower         Print all in lower case

API:
  These options change how this program connects to the API.

  --controller CONTROLLER, -C CONTROLLER
                        Controller URI, ex. https://api.elcapitan.cloudgenix.com

Login:
  These options allow skipping of interactive login

  --email EMAIL, -E EMAIL
                        Use this email as User Name instead of cloudgenix_settings.py or prompting
  --password PASSWORD, -PW PASSWORD
                        Use this Password instead of cloudgenix_settings.py or prompting
  --insecure, -I        Do not verify SSL certificate
  --noregion, -NR       Ignore Region-based redirection.

Debug:
  These options enable debugging output

  --sdkdebug SDKDEBUG, -D SDKDEBUG
                        Enable SDK Debug output, levels 0-2

Config:
  These options are to provide site and BW monitoring details

  --sitename SITENAME, -S SITENAME
                        Name of the Site. Or use keyword ALL_SITES
  --label LABEL, -L LABEL
                        Circuit Label to minimize cellular usage on. Provide one or more circuit labels or use the keyword ALL_LABELS
Tanushrees-MacBook-Pro:cellularusage tanushreekamath$ 


```



### Version
| Version | Build | Changes |
| ------- | ----- | ------- |
| **1.0.0** | **b1** | Initial Release|


### For more info
 * Get help and additional Prisma SDWAN Documentation at <https://docs.paloaltonetworks.com/prisma/prisma-sd-wan>
 
