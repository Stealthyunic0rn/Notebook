# Registry
Found in /Windows/System32/config

## Hive
HKEY_LOCAL_MACHINE
HKEY_USERS
HKEY_CURRENT_USER
HKEY_CLASSES_ROOT
HKEY_CURRENT_CONFIG

**Subkeys in HKEY_LOCAL_MACHINE:**
- HARDWARE: built each time the computer starts containing the type and state of devices. Important subkeys are DESCRIPTION, DEVICEMAP, OWNERMAP, RESOURCEMAP
- SAM: directory database, security information for users and group accounts
- SECURITY: local security policy i.e user rights
- SOFTWARE: software info such as manufacture and version
- SYSTEM: device driver, service info and OS behavior, important subkeys are CLONE, CONTROLSET001,2,CurrentControlSet and DISK.

RegBack- backup of registries

Every user profile has a NTUSER.DAT. Plugs into the user as a current user (that users chunk of info in a registry)
HKEY_CURRENT_USER is basically NTUSER.DAT 

Shellbags: The customization (looks, icon size, sort) of a file explorer directory. Includes deleted paths.
  - Can also be found in USRCLASS.dat
  
  ### USB
  CurrentControlSet will only be on a live system
  To find the last used ControlSet, check the Select path.
  
  Globaly Unique Serial numbers have a & at the second to last char in the number.
  Mathcing the VID & PID to the serail points gives you more information of the make and model of the device.
  
  HKLM\SYSTEM\MountedDevices
  Match the serial number to find the Volume GUID (Globably Unique Identifer) 
  Find the serial number to obtain the Drive Letter of the USB
  Using the Volume GUID found in SYSTEM\MountedDevices, you can find hte user that mounted that device.
  
    

  
  
