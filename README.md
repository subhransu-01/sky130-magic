# Install and Setup EDA Tools  
[To install Ubuntu 24.04 on Windows Subsytem for Linux (WSL)](https://github.com/silicon-vlsi/SI-2025-AnalogIC/blob/main/content/cad-install-setup-wsl-ubuntu.md)  
[To install and setup the EDA tools](https://github.com/silicon-vlsi/SI-2025-AnalogIC/blob/main/content/cad-install-eda.md)
# Steps for Installation and Setup Magic  
**Directory Structure** after installation should look like this:  
```bash
share
└── pdk
cad
├── eda-ngspice
├── eda-xschem
├── eda-magic
└── eda-netgen
work
├── xschem
└── magic
.xschem/
└── simulations
```
  
- **Change to working directory** 💻 `cd ~/work/magic`
- Run the given command to set the technology file.  
  ```bash
  ln -s ~/share/pdk/sky130A/libs.tech/magic/sky130A.tech .
  ```
- 💻 `magic -T ~/work/sky130A.tech` or `magic -d XR -T ~/work/sky130A.tech` to start _magic_ 
- For better graphics , use `magic -d XR -T ~/work/sky130A.tech` to start _magic_
- If you are able to succesfully completed the steps then you are all set for designing layouts using the SKY130 technology.

# Quick Steps
  





