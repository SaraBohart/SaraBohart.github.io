---
title: Schematic and PCB
tags:
- tag1
- tag2
---

## Team PCBs
Team Member|Front|Back|
-----------|-----|-----|
Julia|![Julia Front image](https://github.com/user-attachments/assets/0d25fc20-95b1-4da8-baa6-b44eb9828932)|![Julia Back image](https://github.com/user-attachments/assets/5e545b6c-c6e6-4074-b08f-f4e3bbc625e8)|
Xander|![Xander Top image](https://github.com/user-attachments/assets/c57d0274-6a83-424e-83f4-5b0176c0c9da)|![Xander Bottom image](https://github.com/user-attachments/assets/b06f48fd-7473-4354-8240-c0fb83c9ce77)|
Sara|![New Top image](https://github.com/user-attachments/assets/bda47107-898e-452d-9d3d-ee4d669cff2f)|![New Bottom image](https://github.com/user-attachments/assets/8694815f-24c9-4057-a13c-be446701deaf)|
Ella|![Ella Top image](https://github.com/user-attachments/assets/65103e51-0313-472c-bc97-3a79d011aefb)|![Ella Bottom image](https://github.com/user-attachments/assets/e623c3b9-0d8b-4157-a720-f777cd7a6726)|



## PCB Original Design
The Following are the original Schematic and the PCB that was actually used for demonstration. It only contains one PIC and one voltage redulator, which is why the final product at the Innovation Showcase contained two extra boards (one with a PIC and one with a regulator). The final schematic and PCB above show the full final system combined onto one board. The folloing is shown for doccumentation of the engineering design process. The bill of materials for both the real design and the new design can be found [here](https://sarabohart.github.io/bom/).
### Old Schematic PNG
![MDv1.7.jpg](https://github.com/user-attachments/assets/44ca3e5b-298a-4426-a766-a28635dde562)
### Old Schematic PDF
[MDv1.7.pdf](https://github.com/user-attachments/files/19717740/MDv1.7.pdf)
### Old Schematic Zip
[MDv1.7.zip](https://github.com/user-attachments/files/19717743/MDv1.7.zip)

### Real PCB Design Image
![Original Front image](https://github.com/user-attachments/assets/60ea4961-1853-45a8-ace7-448fb470495a)
![Original Back image](https://github.com/user-attachments/assets/e1c6e2c6-4b32-444e-9ee6-6ab52b15a655)

### Real PCB Layout Image
![Real PCBs image](https://github.com/user-attachments/assets/be7cf89b-1b1d-4566-962a-232a0ff9f0c8)

The new schematic shows what this final board does with all of those jumperwires in a simpler and less chaotic way.

### Real PCB GERBER
[MotorDriverSB_GERBERr1_Canvas.zip](https://github.com/user-attachments/files/20048074/MotorDriverSB_GERBERr1_Canvas.zip)

## PCB Redesign
This is the final schmatic of the Motor Driver System. It includes the Switching regulators that were used to filter the power down to the 3.3V required by the PIC Microchip. Then it displays the motor driver with the motor connectors. The PIC is shown with net names that connect its pins to the appropriate pins on the other components. The remaining boxes show headers which are used for inter board communication and in circuit programming.

### New Schematic PNG
![FinalSchematic-1](https://github.com/user-attachments/assets/8d3a73e5-e987-4e59-a37d-0ad74ea9bb4b)

### New Schematic PDF
[FinalSchematic.pdf](https://github.com/user-attachments/files/20049355/FinalSchematic.pdf)

### New Schematic Zip
[FINAL.zip](https://github.com/user-attachments/files/20049369/FINAL.zip)
The following PCB design was never manufactured, but shows how all the components used in the final design would be combined on one board. This would be the version 2.0 of the hardware design. It would eliminate all of the fly wires needed for the real PCB and simplify the whole system. This would make it more stable and easier to keep track of. This design also fixes the mistake made witht the switching regulator. As you can see in the old schematic, the feedback pin was connected on the node with the inductor and the diode. It should have been connected on the node with the inductor, capacitor, and fuse. On the original PCB, I had to bend the pins on the switching regulators and solder wires to fix this issue. Since the new schematic does not have that mistake, this board will not have that issue. <br>
Furthermore, this design already uses the correct motor driver. between the first design and this one, the motor driver changed, meaning that the new motor driver had to be fly wired on to the board. This was difficult to keep track of if the wires got disconnected. The new design makes it so that these wires are nonexistant, eliminating the possibility of them being unplugged and mixed up.<br>
This design also automatically connects the logic pins across LEDs, making it much more difficult for the logic pins to be disconnected from eachother. This was an issue durring testing as the logic indicating LEDs were connected in a bread board. <br>
In the new design, the jumper wires that allowed all of the powers to be connected and disconnected have been replaced with fuse holders. The intention with this was so that museum staff who would be in charge of keeping this system running so the exhibit can be displayed to children would not have to worry about bridging the wrong connection. This way, they can plug in the appropriate fuse for the power rail and let the system run. if there is an issue with the power source and a surge happens, the fuses will protect the more expencive equipment, saving the opporator money. while it is a project requierment to have jumpers on the power rails, I beleive this would be more benefitial to the end user. Jumpers were included on my original PCB, which allowed for testing, debugging, and modification. Ideally, those steps would not be requiered of the museum staff who are displaying this exhibit. <br>
Overall, the redesign of the PCB would offer a more stable system that is much safer to display in an enviornment where childern would be interacting with it.<br>

### New PCB Design Image 
![New Top image](https://github.com/user-attachments/assets/bda47107-898e-452d-9d3d-ee4d669cff2f)
![New Bottom image](https://github.com/user-attachments/assets/8694815f-24c9-4057-a13c-be446701deaf)

### New PCB CAM
[CAMStackFinal.zip](https://github.com/user-attachments/files/20049262/CAMStackFinal.zip)
