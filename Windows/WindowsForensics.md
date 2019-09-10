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

  
  ### USB
  CurrentControlSet will only be on a live system
  To find the last used ControlSet, check the Select path.
  
  Globaly Unique Serial numbers have a & at the second to last char in the number.
  Mathcing the VID & PID to the serail points gives you more information of the make and model of the device.
  
  HKLM\SYSTEM\MountedDevices
  Match the serial number to find the Volume GUID (Globably Unique Identifer) 
  Find the serial number to obtain the Drive Letter of the USB
  Using the Volume GUID found in SYSTEM\MountedDevices, you can find hte user that mounted that device.
  
  HKLM\SYSTEM\CurrentControlSet\Enum\USBSTOR\Ven_Prod_Version\USB iSerial
  0064= First Install 
  0066= Last Connected
  0067= Last Removal
  
  ### MISC.
  HKLM\ControlSet001\Control\TimeZoneInformation
  \Control\ComputerName
  \Control\FileSystem
  \Servcies\Tcpip 
  
  HKLM\Software\Microsoft\Windows NT\CurrentVersion\NetworkList
   
   - \Signatrues
      - Managed
      - Unmanaged
   
   - \Nla
      - Cache
      
      Network types and first and last connected times will be in \profiles\(GUID)
 
 When you see a shortcut for example in file explorer in reality its a filename.txt.lnk file
  
  ## Definitions
  - **NTUSER.dat**: contains the the settings and preferencs for each user (installed prorgrans, desktop background, monitor res, ect). Stores information in the HKEY_CURRENT_USER hive then when you sign in or out, Windows saves that info to the NTUSER file.
  - **USRCLASS.dat**: where user profile info is stored.
    - Used to record configuration information from user processes that do not hasve access to write to the standard registry hives.
    - Needs to parse both USRCLASS * NTUSER for each user account to get all the Shellbags information.
  - **Shellbags**: The customization (looks, icon size, sort) of a file explorer directory. Includes deleted paths.
     - Can also be found in USRCLASS.dat
     - May also show the folders or servers that employees should not access.
   - **MRU**: most recently used
   - **Shimcache**: used by the OS to identify appliaction compatability issues.
      - Tracks metadata such as the full file path, last modified data, and file size but only contains the information proor to the systems last startup.
     - Can use this key to identify systems that specific malware was executed on.
     - Found in *SYSTEM\CurrentControlSet\Control\SessionManager\AppCompatCache*
  - LNK files - windows shortcut. Leads to alot of metadata
      - MAC times
      - Size of the target when it was last accessed
      - Serial number of the volume where the target was stored
      - MAC address of the host computer (sometimes)
 - Jump List: features added in Win7 that gives users a quick way to access recent applications.
      
     
 
  
  
    

  
  
