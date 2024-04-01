# VSD-LABS
![thumb](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/999d09e6-7f6b-41f8-98b8-81939600af8a)



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

ClCU

**Results**

To calculate the results and also to view the floor-plan we need to open the def file i.e. *Design exchange format* file which is present in the **runs** folder under the date of performed run. 

![image](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/58d32a75-204f-497b-91e3-e8a450b6c60b)

For a better understanding of the floor plan we can open the *Magic* file by an invoking command-

*magic -T /home/kunalg123/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def*

![2024-03-30 (9)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/acde59c3-460c-46ac-bd62-7a21f9fcfaab)
![2024-03-30 (10)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/9bb69a86-f873-4791-8798-432cd6807a13)
![2024-03-30 (12)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/3fba9980-28fe-46bb-abc0-e57768951c59)
![2024-03-30 (12)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/278b6e72-e7cd-4848-9f9f-eb24895c07e8)
![2024-03-30 (12)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/df82daea-c982-4bd4-86a0-e01504cc751a)
![2024-03-30 (14)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/572f06dc-d46c-45e5-9aa2-37c3cdadee30)
![2024-03-30 (15)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/03aa6e39-46b5-473e-b3c6-82381e19c1dc)
![2024-03-30 (16)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/a8597266-5c6d-4e1e-bc46-fe802050fe5a)
![2024-03-30 (17)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/72dc6a23-35af-4d68-b7ab-8a7e8fe45e30)
![2024-03-30 (20)](https://github.com/abhaybs7505/VSD-LABS/assets/165189754/0fda4a7a-5401-421c-b4e1-c7bb26bb48a7)










