
sudo snap install lxd


# linux mint process to install lxd

1. **Remove the Mint block file:**
    
    bash
    
    ```
    sudo rm /etc/apt/preferences.d/nosnap.pref
    ```
    
    Use code with caution.
    
2. **Update your package list and install `snapd`:**
    
    bash
    
    ```
    sudo apt update
    sudo apt install snapd -y
    ```



lxc launch ubuntu:24.04 ubuntuserver




