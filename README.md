# System Log Manager

A powerful, lightweight Bash-based CLI tool designed for system administrators to efficiently manage, view, and clean up system logs on Linux distributions.

## Overview

System Log Manager provides a centralized interface to interact with logs in `/var/log`. It simplifies common tasks like tailing active logs, purging old compressed archives, and wiping user bash history, all from a clean, numbered menu.

## Interface Preview

```text
===============================================================================
                            SYSTEM LOG MANAGER                                 
===============================================================================

  1) alternatives                              34) device-map.json                          
  2) access                                    35) installer-journal.txt                    
  3) error                                     36) media-info                               
  4) other_vhosts_access                       37) subiquity-server-debug.log.3672          
  5) apport                                    38) subiquity-server-info.log.3672           
  6) edsp.log.zst                              39) telemetry                                
  7) eipp.log.xz                               40) ubuntu_bootstrap.log.3489                
  8) history                                   41) kern                                     
  9) term                                      42) lastlog                                  
 10) auth                                      43) php_errors                               
 11) boot                                      44) syslog                                   
 12) bootstrap                                 45) sa01                                     
 13) btmp                                      46) sa03                                     
 14) cloud-init-output                         47) sa04                                     
 15) cloud-init                                48) sa05                                     
 16) access_log                                49) sa06                                     
 17) error_log                                 50) sa07                                     
 18) apt-term                                  51) sa27                                     
 19) apt                                       52) sa28                                     
 20) history                                   53) sar04                                    
 21) main                                      54) sar05                                    
 22) xorg_fixup                                55) sar06                                    
 23) dmesg                                     56) sar26                                    
 24) dmesg.0                                   57) sar27                                    
 25) dpkg                                      58) sar28                                    
 26) faillog                                   59) ubuntu-advantage-apt-hook                
 27) fontconfig                                60) ubuntu-advantage                         
 28) gpu-manager                               61) unattended-upgrades-dpkg                 
 29) autoinstall-user-data                     62) unattended-upgrades-shutdown             
 30) casper-md5check.json                      63) unattended-upgrades                      
 31) cloud-init-output                         64) telemetry                                
 32) cloud-init                                65) vbox-setup                               
 33) curtin-install                            66) wtmp                                     

===============================================================================
  p) Purge old .gz logs
  a) Truncate all .log files and delete rotated archives
  h) Wipe bash history for current user
  q) Quit

Select a log number or action: 26

--- Target: /var/log/faillog ---
  f) View FULL log
  t) TAIL specific number of lines
  c) CLEAR / Truncate log to 0 bytes
  b) Back to main menu

Select action:
```

## Features

- **Automated Root Elevation:** Automatically detects and requests `sudo` privileges if not run as root.
- **Dynamic Log Discovery:** Automatically scans `/var/log` and subdirectories (up to 2 levels deep) to list all active log files.
- **Interactive Grid Layout:** Displays logs in a clean, alphabetical 2-column grid for easy navigation.
- **Bulk Cleanup:**
    - **Purge .gz Archives:** Instantly delete all compressed rotated logs to reclaim disk space.
    - **Total Purge:** Truncate all `.log` files and delete all rotated archives (`.gz`, `.xz`, `.[0-9]`) in one command.
- **Privacy Tools:** Wipe the current user's `.bash_history` file directly from the menu.
- **Granular Log Management:**
    - **View:** Open any log in a full-screen pager (`less`).
    - **Tail:** View the last *N* lines of any log.
    - **Truncate:** Reset any specific log file to 0 bytes without deleting it.

## Installation

1. **Clone or Download the script:**
   ```bash
   git clone https://github.com/nodefive/logman.git
   cd logman
   ```

2. **Make it executable:**
   ```bash
   chmod +x logman
   ```

3. **(Optional) Move to your path for global access:**
   ```bash
   sudo mv logman /usr/local/bin/logman
   ```

## Usage

Simply run the script:
```bash
logman
```
*Note: The script will prompt for your password to elevate to root if necessary.*

## Safety Note

This tool performs administrative actions. Be cautious when using the **Truncate All** or **Clear Log** functions, as they will permanently remove log data that may be useful for debugging.
## License

MIT License — Copyright (c) 2025 nodefive

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
