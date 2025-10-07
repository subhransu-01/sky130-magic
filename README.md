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

# Quick Guide
- After opening _magic_ go to command window and set the grid. `grid 50nm 50nm`
- You can also set the grid from **Window** dialog box  
  <img width="1451" height="841" alt="Screenshot 2025-10-04 002716" src="https://github.com/user-attachments/assets/7d6c9e4f-6826-4aa5-b69a-31564ebc8fb3" />  
- After setting the grid , write `snap user` in the command window
- Turn on **Crosshair** from **Options** dialog box (Optional)
  <img width="1452" height="842" alt="Screenshot 2025-10-04 003638" src="https://github.com/user-attachments/assets/46006554-3f20-4f89-8ef9-5c2c9bbfa63a" />
- # Label & Port  
- Select the area you want to label or make port  
- Use the given command  
- `label [name]`  
- `port make`   
- `port index [value]`  
  <img width="1919" height="1015" alt="Screenshot 2025-10-07 202421" src="https://github.com/user-attachments/assets/e9e46585-401e-4a4f-baa4-e4e79ae0a170" />   
-  You set this from **Edit** dialog box , there is a option **Text...**      
  <img width="1919" height="1011" alt="Screenshot 2025-10-07 203443" src="https://github.com/user-attachments/assets/2c023ed7-eec6-4eb6-a9a0-5572ca1d4c42" />
     
- Enter name in **Text string** to _label_ the selected area  
- You can adjust text size in **Size**  
- To make port , use **enable** option in **Port** and enter **[value]** to give _port number_  
- Use **Attach to layer** option for attaching port with the layer (eg. metal1) or use **default**  
- To check _port number_ select the port area , then use `port index`
  <img width="1919" height="1013" alt="Screenshot 2025-10-07 202742" src="https://github.com/user-attachments/assets/36efce6e-10d8-4ded-9c8a-2cbcc14e4542" />
  
- # DRC
- You can check current DRC by `drc style` in the command window
- To set _DRC full_ go to **DRC** dialog box and set **DRC Complete**
  <img width="1448" height="841" alt="Screenshot 2025-10-04 005505" src="https://github.com/user-attachments/assets/a1b65e94-774e-4324-bc34-7e385b833aa2" />
- To check _DRC Error_
  use `select top cell` in the command window or you can select by cursor , then use `drc why` in the command window  
- To find the _DRC Error_ , use `select top cell` then `drc find` in the command window
- # PEX  
- For parasitic extraction use  
-  `extract all`  
-  `ext2spice hierarchy on` (eg. for top level keep **on** , for flatten **off** )  
-  `ext2spice scale off`  
-  `ext2spice cthresh [value]` (eg. ext2spice cthresh 100f)  
-  `ext2spice rthresh [value]` (eg. ext2spice rthresh 100u)  
-  `ext2spice`  
- # LEF & GDS
- To set the prboundary box , select area where you want the bounding box to be and use  
- `box value` to get the value (eg. 0 0 60 100)  
- `property FIXED_BBOX [box values]` (eg. property FIXED_BBOX "0 0 60 100")  
- `select top cell`  
- `property LEFclass CORE`  
- `property LEFsymmetry "X Y"`  
- `property LEFsite [library name]`  
- `lef write` , to create lef file  
- `gds write` , to create gds file
- To check _property_ , `select top cell` then use `property`  

# Some Reference  
[Magic Main](http://opencircuitdesign.com/magic/)  
[Quick Video by Dr. Saroj Rout](https://zoom.us/rec/share/9V1J33K5uY3kdc-3f6E3hHuCJ5psEw2-oJVwWLmwV7fcyYT1D3wFZFRP8xs8eCTn.rlaLXq7Upm_xbXgo)  
[Magic Video by Matt Venn](https://www.youtube.com/watch?v=IQ_DcWT_cbc)  


