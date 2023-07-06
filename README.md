# Design_and_analysis_of_nmos_pmos_and_Inverter_using_sky130pdk

Welcome to the Design and Analysis project using the SkyWater130 Process Design Kit (PDK). In this project, we will explore the characteristics and behavior of NMOS and PMOS devices, as well as design and analyze a CMOS inverter, utilizing the capabilities of the SkyWater 130nm process technology.

**Analysis of NMOS and PMOS**

We will begin by utilizing the 1.8V standard models of NMOS and PMOS available in the SkyWater130 PDK. Through analysis and experimentation, we will explore the common working principles of these devices and characterize their behavior by varying different parameters. This analysis will provide valuable insights into their performance and functionality.

**Design and Analysis of CMOS Inverter**

Next, we will dive into the design and analysis of a CMOS inverter. This will involve creating the schematic representation of the inverter and measuring various parameters such as delay, noise margin, rise time, and fall time. These measurements will serve as a case study to study SPICE simulation and understand the behavior of the CMOS inverter.

**Layout Design using MAGIC**

In the subsequent phase, we will shift our focus to the layout design of the CMOS inverter using the MAGIC layout editor. MAGIC provides a comprehensive platform for exploring and utilizing the different layers available in the SkyWater130 PDK. We will create the layout design of the inverter, ensuring adherence to design rules and constraints.

**Layout versus Schematic (LVS) Comparison**

To ensure the accuracy and consistency of our layout, we will perform a Layout versus Schematic (LVS) comparison. This step involves comparing the layout design with the previously created schematic representation. By utilizing tools like Netgen and the LVS capabilities of the SkyWater130 PDK, we will verify the correctness and integrity of the layout.

Throughout the project, we will leverage the models and resources provided by the SkyWater130 PDK, as well as open-source tools such as Xschem, NGSPICE, MAGIC, and Netgen. The project documentation will be structured in a manner that is easily understandable for anyone looking to follow the same methodology.

Join us in this exciting journey of designing and analyzing NMOS, PMOS, and CMOS circuits using the SkyWater130 PDK. Let's explore the capabilities of the PDK and gain valuable insights into the world of electronic design.

# Content

 **1. About Tools**
    
     1.1 Ngspice
    
     1.2 Magic
    
     1.3 Netgen
    
     1.4 xschem
    
     1.5 Skywater Technology
   
 3. Analysis of MOSFET models
   
     2.1 General MOS analysis
   
     2.2 strong 0 and weak
   
     2.3 Weak 0 and strong 1

 4. CMOS Inverter Design and Analysis
     3.1 Why CMOS Circuits
    
     3.2 CMOS Inverter Analysis(Pre-Layout)

  # 1. About Tools
  
   **1.1 Ngspice**
   
  ![image](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_and_pmos_using_sky130pdk/assets/57873021/9073cdd0-8e57-4177-9557-cc476fa6e9c2)

  [Ngspice](https://ngspice.sourceforge.io/) is an open-source mixed-level/mixed-signal electronic circuit simulator widely used for circuit design, analysis, and verification. It allows users to 
  model and simulate the behavior of electronic circuits using a variety of circuit elements, including resistors, capacitors, inductors, transistors, and more.

  Ngspice provides a command-line interface for interaction and scripting, making it flexible and suitable for both interactive usage and automated workflows. It 
  supports a wide range of circuit netlist formats, including the popular SPICE format, allowing seamless integration with existing design flows and tools.

   Its versatility and accessibility make it a valuable asset in the field of electronic design automation.

   > *You can refer to Ngspice manual [here](https://ngspice.sourceforge.io/docs.html)*

   **1.2 Magic**
   
   ![image](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_and_pmos_using_sky130pdk/assets/57873021/57ec58d6-9023-4d6a-ae0e-eb2db101f1db)

   [Magic](http://opencircuitdesign.com/magic/) is an open-source layout tool widely used in the field of digital integrated circuit design. It provides a powerful platform for creating and editing 
   layouts of integrated circuits at various levels of abstraction, ranging from individual transistors to complete chip designs.
   
   Magic offers a range of features to enhance productivity and design efficiency. It includes a comprehensive set of drawing tools and alignment aids to facilitate 
   precise and accurate layout creation. It supports design rule checking (DRC) and layout versus schematic (LVS) verification, helping to identify and resolve 
   potential design errors and mismatches.

   Its feature-rich nature, extensibility, and community support make it an invaluable asset in the realm of digital integrated circuit design.

   > *You can refer to Magic manual [here](http://opencircuitdesign.com/magic/magic_docs.html)*

   **1.3 Netgen**
   
   ![image](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_and_pmos_using_sky130pdk/assets/57873021/215efd81-b834-4845-a390-d8c8be694ed2)

   [Netgen](http://opencircuitdesign.com/netgen/) is an open-source netlist comparison and verification tool used in the field of electronic design automation (EDA). It provides a powerful platform for 
   analyzing and comparing digital circuit netlists to ensure consistency and correctness across different stages of the design process.

   Netgen supports a wide range of netlist formats, including popular industry standards like SPICE and Verilog. It offers comprehensive netlist parsing and analysis 
   capabilities, allowing you to explore the hierarchical structure of the design, examine signal dependencies, and identify potential issues.

   Its ability to detect discrepancies and ensure design consistency contributes to the overall success and reliability of your circuit designs.

   > *You can refer to Netgen manual [here](http://opencircuitdesign.com/netgen/tutorial/tutorial.html)*

   **1.4 Xschem**
   
   ![image](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_and_pmos_using_sky130pdk/assets/57873021/90b859e9-d0f5-4bca-bff5-cb439948ecec)

   [Xschem](https://xschem.sourceforge.io/stefan/index.html) is an open-source electronic schematic capture and simulation tool widely used in the field of electronic design automation (EDA). It provides a versatile 
   platform for designing and simulating analog and digital circuits, facilitating the creation and analysis of complex circuit schematics.

   Xschem also supports advanced features such as model parameter extraction, sensitivity analysis, and waveform plotting, allowing you to fine-tune circuit designs 
   and explore design trade-offs. It offers a flexible scripting interface, enabling automation of repetitive tasks and customization of the tool's behavior to suit 
   specific requirements.

   Its user-friendly interface, extensive simulation capabilities, and community support make it an invaluable tool in the field of electronic design.

   > *You can refer to xschem manual [here](https://xschem.sourceforge.io/stefan/xschem_man/xschem_man.html)*

   **1.5 Skywater Technology**
   
   ![image](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_and_pmos_using_sky130pdk/assets/57873021/f8f19c5c-1ded-40c1-a87b-82dc2e572bab)

   The [SkyWater](https://www.skywatertechnology.com/technology-and-design-enablement/) Technology Foundry 130nm Process Design Kit (PDK) is a comprehensive collection of files, libraries, and documentation that enables the design and 
   fabrication of integrated circuits (ICs) using the SkyWater 130nm process technology.

   The SkyWater130 PDK is typically utilized in conjunction with electronic design automation (EDA) tools, enabling designers to create and verify their IC designs 
   within a familiar design environment. The PDK provides the necessary information for layout design, including design rules, layer information, and guidelines for 
   ensuring compatibility with the SkyWater 130nm process technology.

   Overall, the SkyWater130 PDK is an essential resource for IC designers seeking to leverage the capabilities of the SkyWater 130nm process technology. Its 
   comprehensive set of files, libraries, and guidelines streamline the design process and facilitate the creation of high-quality integrated circuits.

   > *You can refer to skywater130 manual [here](https://skywater-pdk.readthedocs.io/en/main/)*

   ## Analysis of NMOS and PMOS

   *******************************
In this section, we will conduct an analysis of the NMOS and PMOS devices. For our analysis, we will utilize the basic 1.8V model available in the SkyWater130 PDK. While there are various other models available for different purposes, we will focus on this particular model for our analysis.

To begin, open the Xschem application. Upon startup, the application window will be displayed which will look like this.

![Xschem](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/645240df-2a3d-4054-8c1a-14cfee174751)

Create a new schematic by selecting the "File" option and choosing to create a new file. A blank window will appear where we can build our schematic.

![Xschem_newfile](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/fe8e4259-d104-4bb4-8ed9-d9cf85d4f89e)

To instantiate the required components, use the shortcut "Shift + I" to open the component instantiation window. Here, you will find two libraries: "xschem device library" and "xschem_sky130 device library". Select the following components:

nfet_01v8.sym from the xschem_sky130 library.
vsource.sym from the xschem device library.
code_shown.sym from the xschem device library.
gnd.sym from the xschem device library.

Connect the components using wires to create the desired schematic. Use the "W" shortcut to draw wires between the components. Your schematic should resemble the desired configuration.

![Xschem_Nmos](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/7ee51c5b-57cf-4d26-8b87-5d6064f4e922)

This circuit facilitates the determination of key parameters such as threshold voltage, transconductance, and drain current.

Once the schematic is complete, generate the netlist by clicking on the "Netlist" option located in the top right corner. Ensure that the "Spice netlist" option is selected in the "Options" menu, and make sure the "Show netlist" window is enabled (shortcut: "Shift + A"). The netlist window will display the generated netlist, it should look like this if you have not made any errors while making the schematic and if there are any error in the schematic that will be highlighted in the separate error window from where you can debug those.

![Xschem_netlist_nmos](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/6d9689cd-69dc-4f82-8af4-953f34d3c9cc)

The next step in our analysis is to simulate our design. Click on the "Simulate" option next to the netlist option. This will open the Ngspice terminal, where we can run the simulation which will look like this.

![Ngspice](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/c5af1e51-ef28-48c2-9f43-5e1709678f83)

Here are some useful commands for the Ngspice terminal:

```display```: Shows all the variables available for plotting characteristics<br>
```setplot```: Displays all the plots available for simulation<br>
```plot```   : Helps choose the variables to plot for analysis<br>

By utilizing these commands, we can analyze and plot the characteristics of our NMOS and PMOS devices.

after giving the ```display``` command we can see the variables available to us for which we can plot the characterstics for our case we will be plotting the vds#branch which will plot the the I-V characteristics of the NMOSFET. By varying the gate-to-source voltage (Vgs) and drain-to-source voltage (Vds), the current flowing through the NMOSFET can be observed and analyzed.

when I sweep Vgs source for different values of Vds, I get the below plot:

![i-v_nmos_vgs_sweeping](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/f4ee3d7d-9e20-4f69-9306-378f393d65b5)

as we can see now the plot got generated and which we will be getting after DC sweeping Vgs for different value of Vds from the above plot we can see that our Vth i.e treshold voltage is lying in between the 600mV to 700mV.

Similarly, when I sweep Vds source for different values of Vgs, I get the below plot:

![i-v_nmos_vds_sweeping](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/0a018595-9f45-40ab-a907-139eee058725)

above two plots looks completey as we expected if you are familiar with the nmos characterstic curve we can see the linear and saturation part of the curve distinctively.

now we will calculate Gm transconductance plot independently for the both of our I-V characteristics to find it we simply use the ```deriv()``` command this will help in taking derivative with respect to independent variable present at the current simulation. As we are aware of the definition of Gm i.e *dIds/dVds* so we will get the respective plot

![transconducatance_nmos](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/a590d91a-7891-4730-b747-8f7ef387924a)

![transconducatance_nmos](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/bffb9fbf-0fe0-4c8b-98b6-4a854366925f)

 
   *You can go through this [Ngspice documentation](https://ngspice.sourceforge.io/docs/ngspice-manual.pdf) to get an idea of terminal commands and their syntax.*

same process can be repeated for the PMOS analysis we will be getting our result like below when we do so...

PMOS schematic 

![schematic_pmos](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/c488f0c3-1ddb-439f-a2b9-5191b97c185d)

I-V characteristics of the PMOSFET
when I sweep Vgs source for different values of Vds, I get the below plot:

![i-v_nmos_vgs_sweeping](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/128e2a78-93fa-4e1e-8e2e-51bf6c05015b)

Similarly, when I sweep Vds source for different values of Vgs, I get the below plot:

![i-v_nmos_vds_sweeping](https://github.com/SudeepGopavaram/Design_and_analysis_of_nmos_pmos_and_inveter_using_sky130pdk/assets/57873021/1ba2e9f3-0d7a-41da-8bf4-3574254df3ed)








   ************************************************
code_shown block plays an important role in process this block consist of our 
   
  In this section we would start with our analysis which focuses on the characterization of NMOSFET (N-channel Metal-Oxide-Semiconductor Field-Effect Transistor). This section provides a comprehensive understanding of the NMOSFET and its current-voltage (I-V) characteristics.

This section includes a characterization circuit for the NMOSFET, which allows for the measurement and analysis of its behavior. This circuit facilitates the determination of key parameters such as threshold voltage, transconductance, and drain current.

Additionally, we will explores the I-V characteristics of the NMOSFET. By varying the gate-to-source voltage (Vgs) and drain-to-source voltage (Vds), the current flowing through the NMOSFET can be observed and analyzed. This characterization helps in understanding the device's conduction behavior, including the saturation region, linear region, and pinch-off region.

   In this sec 
   we will be using the basic 1.8v model, there are also lot of models 
   other than this which can be used depending on our purpose but for 
   our analysis we will be going with this particular model only.

   when you first startup with your xschem application it will look like this.

   start by creating new schematic from the ```file``` option a new file will be created with a blank window infron of you.

   we will start by instatiating the required component for our schematic use the shortcut ```shift + i``` for instantiating component a window will pop up on which you can see two libraries one is xschem device library where as other one is xschem_sky130 device library select the required components as mentioned below
   
   ```nfet_01v8.sym``` - from xschem_sky130 library<br>
   ```vsource.sym``` - from xschem device library<br>
   ```code_shown.sym``` - from xschem device library<br>
   ```gnd.sym``` - from xschem device library<br>

   with the help of our selected component we will make our desired schematic by connecting each component with the help of wire use the shortcut ```w``` our schematic should look like this.

   after this we will be creating the netlist for our schematic by clicking on the ```netlist``` on the top right side but make sure that you have selected the "spice netlist" from the ```option menu``` and your show netlist window must also be enables shortcut to enable the netlist window is ```shift + a``` it should look like this.


   next step in our analysis is simulating our design click on the ```simulate``` option rigth next to the netlist option a window should open like this is nothing but Ngspice terminal.

   lets go through some terminal commands
   ```display``` will show you all the variable between which you can plot the characterstics 
   ```setplot``` will show all the plot that are availble for simulation
```plot``` will help you choose the variable to plot
   

   here is our first plot for our NMOS when we DC sweep on Vgs source for different values of Vds:

   our second plot when we DC sweep on Vds source for different value of Vgs


   now we will calculate Gm transconductance parameter to find it we simply use the ```deriv()``` command this will help in taking derivative with respect to independent variable present at the current simulation. As we are aware of the definition of Gm i.e *dIds/dVds* so we will get the respectibe plot

   *You can go through this [Ngspice documentation](https://ngspice.sourceforge.io/docs/ngspice-manual.pdf) to get an idea of terminal commands and their syntax.*

   Now as we have now all the required important plots with us for NMOS we can get the same for PMOS by following the same procedure.

   one point to note here is that you can notice that when we measure the current for both the NMOS and PMOS at the same voltage we will be getting different voltage, now to get that same for both the MOSFET at same voltage the condition is *W/L of PMOS = x * W/L OF NMOS*

CODE_SHOWN BLOCK


## Strong 0 and Weak 1

   
     
     
