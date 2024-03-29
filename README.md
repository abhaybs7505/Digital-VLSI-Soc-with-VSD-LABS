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


Flip Flop ratio = Total Number of D flip flop / Total number of Cells

Percentage = Flip flop ratio * 100

Ratio = 1613/14876    
  =0.108429685

Percentage = 10.84296854%      
