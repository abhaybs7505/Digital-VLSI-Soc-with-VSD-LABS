# VSD-LABS
![thumb](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/999d09e6-7f6b-41f8-98b8-81939600af8a)


Section 1:

Section2: 

[Section 3](#section3-design-library-cell-using-magic-layout-and-ngspice-characterization)



# Section-1: Inception of open source EDA, Openlane & Sky130 PDK:



**Objectives-**

+ Show PICORV32a design synthesis and calculate its flip flop ratio.

Screenshots-

#Invoking Openlane directory

+ Here *docker* command is used to invoke openlane directory.
+ *./flow.tcl -interactive* command is used to process step by step.
+ *package require openlane 0.9* is used to import all the packages.
+ *prep -design picorv32a* is used to load the config of picrov32a.
  
![2024-03-29 (2)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/20d61be6-f48c-4b1e-8f31-7e7c75907431)

#Running synthesis

+ *run_synthesis* performs yosys RTL synthesis.

![2024-03-29 (3)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/68405928-531a-414e-98c8-349b14d1fecb)

![2024-03-29 (4)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/0f19e83a-b8c6-44ce-8337-aaab49147a6f)

#Statistics

![2024-03-29 (6)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/b4ddbb35-ec4c-4ec7-a07b-576869ab5109)
![2024-03-29 (7)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/d06bab87-6986-4e4b-a03a-b7f4a8ee874a)


Flip-Flop ratio = $\frac{Total Number of D flip flop}{Total number of Cells}$

Percentage = Flip flop ratio * 100

$Ratio$ = $\frac{1613}{14876}$

Percentage = 10.84296854%      


# Section-2: Good floorplan vs Bad floorplan and introduction to library cells:
**Objectives-**
+ Run 'picorv32a' design floorplan using OpenLANE flow and generate necessary outputs.
+ Calculate the die area in microns from the values in floorplan def.
+ Load generated floorplan def in magic tool and explore the floorplan.
+ Run 'picorv32a' design congestionn aware placement using OpenLANE flow and generate necessary outputs.
+ Load generated placement def in magic tool and explore the placement.

**Screenshots-**

![2024-03-30](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/5db40839-a645-4b7b-887d-e2c3dec769d3)

#Running RTL Synthesis

![2024-03-30 (1)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/c0d64d76-0b66-4f18-b0d7-5d6cf5e63420)

#Running the floorplan

![2024-03-30 (2)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/c54b2a97-a937-48ce-be84-fc224f1a3e81)
![2024-03-30 (3)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/077a3341-f70c-4237-8e69-b3adb90b48f4)

**Calculation according to Floorplan**
1000 Unit Distance = 1 Micron

Die width in unit distance = 6606865

Die height in unit distance = 671405

Distance in microns = $\frac{Value in Unit Distnace}{100}$

Die width in microns = $\frac{6606865}{1000}$ = 660.685 microns

Die height in microns = $\frac{671405}{1000}$ = 671.405 microns

Area of Die in microns = 660.685 * 671.405 = 443587.212425 Sq microns




**Results**

To calculate the results and also to view the floor-plan we need to open the def file i.e. *Design exchange format* file which is present in the **runs** folder under the date of performed run. 

![image](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/58d32a75-204f-497b-91e3-e8a450b6c60b)

For a better understanding of the floor plan we can open the *Magic* file by an invoking command-

*magic -T /home/kunalg123/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def*

![2024-03-30 (9)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/acde59c3-460c-46ac-bd62-7a21f9fcfaab)

To select a object hover the mouse onto the object and then press 's' on the keyborad.

To Zoom in select the object and then press 'z' & to Zoom out press 'shift+z'

![2024-03-30 (10)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/9bb69a86-f873-4791-8798-432cd6807a13)
![2024-03-30 (12)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/3fba9980-28fe-46bb-abc0-e57768951c59)
![2024-03-30 (12)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/278b6e72-e7cd-4848-9f9f-eb24895c07e8)
![2024-03-30 (12)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/df82daea-c982-4bd4-86a0-e01504cc751a)
![2024-03-30 (14)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/572f06dc-d46c-45e5-9aa2-37c3cdadee30)
![2024-03-30 (15)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/03aa6e39-46b5-473e-b3c6-82381e19c1dc)
![2024-03-30 (16)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/a8597266-5c6d-4e1e-bc46-fe802050fe5a)
![2024-03-30 (17)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/72dc6a23-35af-4d68-b7ab-8a7e8fe45e30)
![2024-03-30 (20)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/0fda4a7a-5401-421c-b4e1-c7bb26bb48a7)

# Section3 Design library cell using Magic Layout and ngspice characterization

**Objectives:**

1. Cloning custom inverter standard cell design from github repository link: Standard cell design and characterization using OpenLANE flow.
2. Load custom inverter layout in magic and explore.
3. Spice extraction of inverter in magic.
4. Editing the spice model file through simulation.
5. Post-layout ngspice simulations.
6. Finding problems in the *DRC* section of the magic tech file for the skywater process and fix them.

#Cloning from github repository

![2024-04-04 (1)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/bea61f22-14f1-448e-abfc-2e045428078d)

#Inverter Layout Design 

![2024-04-04 (1)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/8c727a47-3830-491c-bad0-1b44be39ac2c)

#To Identify NMOS & PMOS
![2024-04-04 (3)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/e63e9b4d-5294-46d7-8cac-4673ca17fcd1)
![2024-04-04 (4)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/68cb04be-7556-4bcf-8026-2979cf211b9b)

#Verifying that Y o/p is connected to PMOS & NMOS drain

![2024-04-04 (5)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/25bf7f5d-c513-4a53-85a3-dcef4ac7b6a3)

#Verification of VPWR connectivity to PMOS source

![2024-04-04 (6)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/d06d2a52-4018-4c6b-9cec-edb5cb7bd528)

#Verification of VGND connectivity to NMOS source

![2024-04-04 (7)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/54ee9eea-126c-4dbe-8a2d-0676a9f43a86)

tkcon window:

![2024-04-04 (8)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/2f0520ec-4a9f-4ce9-be86-bf479716e07a)

#sky130A spice file

![2024-04-04 (9)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/3c86359b-9397-4df3-92d9-1e73a31eaf56)

#Stimulating the spice file in magic

![2024-04-04 (10)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/3b63fe31-4fc0-4efd-89ab-2da6b2946021)

#Editing the spice file according to the given requirement

![2024-04-04 (11)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/00376351-e264-4888-be2e-95f527de6083)

#Running ngspice:

To load spice file type the command - *ngspice sky130_inv.spice* followed by *plot y vs time a*

![2024-04-04 (13)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/cd39efc9-93b8-4741-bb78-9a0fef54fa72)

![2024-04-04 (15)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/334149d0-23f2-431b-8085-52696516952b)

**20% Screenshot**

![314009074-0180052c-4b8c-4bd8-928c-cd8ab34d5a17](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/ebcd6bd1-84f7-4c0b-bb95-0024102694fe)

**80% Screenshot**

![314009811-7bc0eeee-c7cd-464e-a90b-cac8d4f83144](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/39aa6491-3551-46f6-8d01-021c85a47c60)

**50% Screenshot**

![314018565-e34363cd-a70f-4939-b8e5-efb10620ce93](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/f32f314c-3635-4740-9230-6618164694a1)

calculyioyuodjry

#Finding the errors in DRC section of old magic file:

![2024-04-05 (1)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/97971bf3-5ed7-4a8e-b0da-c96a0f2e35f4)

#This is the .magicrc file

![2024-04-05 (1)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/2c45420d-dd2b-4a51-a761-de6a681c5a28)

*To refer the Sky130A Periphery rules: https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html* 

**This will be useful for viewing the poly.9 rule, difftap.2 rule, nwell.4 rule correction**

![2024-04-05 (3)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/929d48ca-b778-4a86-bf31-5b8c1e620235)
![2024-04-05 (4)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/07171554-1522-4bd9-b14c-f50d9c45c2e9)
![2024-04-05 (6)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/09693002-dfd8-4af4-be9f-95a013fb2c00)

#Poly.9 rule violation, No Drc error

![2024-04-05 (7)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/ff7bf398-ef11-42af-9bfd-2cd8b084804f)

#Updated sky130A.tech file

![315579814-dc30df54-3282-42f0-8e7d-fc4d8877ed64](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/fd31d72a-17e9-4662-b6d7-05f5c9a5542f)
![315565406-d112ca07-854c-41e7-8822-c269e21defea](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/ef2d905d-4541-46a1-b026-c3dce43c01b0)

#Rule implemented

![315580472-d5afe8d8-691b-485d-a89a-8f901e18b56e](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/1b91e47d-baa9-4902-8910-85172edb2e5b)

#difftap.2 rule violation, No DRC error

Screenshot of rule implemented

To Implement this we need to update the sky130A.tech file

![315588573-a3f92160-6701-48fb-b6cf-e4c41dc4a531](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/20c7cd0a-c3d6-4f04-9b7c-8017b3086eee)

#Updated sky130A.tech file

![315587555-b5892f9b-9c5d-4b1b-baa2-6fe45f3965b1](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/3cd3edfc-b1c0-4bb2-9c6c-47fd578a5e0f)


#Incorrect nwell.4 rule, No DRC violation

![315594932-87da8944-0ad8-455d-97ec-3909eac656c3](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/3f4ab2ef-df9d-4c20-bd8e-41e74fa601e3)

#Change of Commands in sky130A.tech file

![315598066-886c6930-6314-4a6f-97d9-6b8423444ac0](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/08522fa0-e3a9-440f-bbb5-c8ae34145112)
![315598080-d9808e9a-42c2-4421-9b82-2ef65a5a1ad7](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/e841ff53-3604-4021-9b03-e98e43225c1d)

#To check run the commands in tkcon window
*tech load sky130A.tech*
*drc style drc(full)*
*drc check*
*drc why*

![315600131-49b1004d-f860-4ca7-86f4-4d79784a01cf](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/81b8843f-90ec-4e24-b227-b0b0e5fa1501)


# Section 4 Pre-layout timing analysis and importance of good clock tree

**Objectives:**
1. Fix DRC errors and verify the design to be inserted into our flow.
2. Save the finalized layout with custom name and open it.
3. Generate lef from the layout.
4. Copy the newly generated lef and associated required lib files to 'picorv32a' design 'src' directory.
5. Edit 'config.tcl' to change lib file and add the new extra lef into the openlane flow.
6.Run openlane flow synthesis with new custom inverter cell.
7. Remove the newly introduced violations with the introduction of custom inverter cell by modifying design parameters.
8. Once synthesis has accepted our custom inverter run floorplan, placement and verify the cell is accepted in PnR flow.
9. Post-Synthesis timing analysis with OpenSTA tool.
10. Make timing ECO fixes to remove violations.
11. Replace the old netlist with the new netlist generated after timing ECO fix and implement the floorplan, placement & cts.
12. Post-CTS OpenROAD timing analysis.
13. Explore post-CTS OpenROAD timing analysis by removing 'sky130_fd_sc_hd__clkbuf_1' cell from clock buffer list variable 'CTS_CLK_BUFFER_LIST'.


#Fix up small DRC errors and verify the design is ready to be inserted into our flow.

**Rules**

**Rule 1:**  The input and output ports of the standard cell should lie on the intersection of the vertical and horizontal tracks.

**Rule 2:** Width of the standard cell should be odd multiples of the horizontal track pitch (taking 3 here)

**Rule 3:** Height of the standard cell should be even multiples of the vertical track pitch.

#Commands to be typed:

*cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign*

*magic -T sky130A.tech sky130_inv.mag &*

![2024-04-06](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/93366ba4-767b-4ed2-a74e-d4cf73389daa)

#Verified Rule 1:

![2024-04-06 (2)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/c10da267-42ef-460a-a6fe-4b29ef87a09a)


#Verified Rule 2:

![2024-04-06 (3)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/799eead6-9c15-4615-9889-eaed9aa192f3)

Horizontal pitch = 0.46um

Width of standard cell = 1.38um = 0.46*3 

#Verified Rule 3:

![2024-04-06 (3)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/b6db17ca-54f8-4d40-aee4-39ff0e301b19)

Vertical pitch = 0.34um

Height of standard cell = 2.72um = 0.34*8 






