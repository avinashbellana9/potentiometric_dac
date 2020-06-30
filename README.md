# POTENTIOMETRIC DIGITAL TO ANALOG CONVERTER
The project aims at designig a `potentiometric digital-to-analog converter`. The key idea is to realize a potentiometric dac with required specifications to be able to get installed in a home automation microcontroller.

# Why digital-to-analog converter?
A computer is designed to work in a digital domain.In today's world, the existence of digital electronics is boundless.Despite such advancement,the world is yet analogous and this seems to be inevitable.Hence,there is a need for a bridge between the digital and analog domains.On that account,there comes a need for digital-to-analog and analog-to-digital converters. 

# Quick glance of the IP
With the advent of high performance digital circuits,the need for data converters with high speed and accuracy for a wide range of applications has drawn the attention of scientists and researchers worldwide.In this project we try to design a potentiometric digital-to-analog converter.This repository consists of all the files required to design a potentiometric dac.

To develop an insight into the project, download the `understanding_pac` pdf document uploaded in this repository.Go through the document carefully and navigate to the references provided in the same whenever there is a need. The document also provides you with some `applications` of dac which helps in understanding their practical implications. 

Let us begin with the design of a `2-bit` potentiometric dac. All the steps required are mentioned below. Lets start!

# Installing the simulator: Ltspice

LTspice® is a high performance SPICE simulation software, schematic capture and waveform viewer with enhancements and models for easing the simulation of analog circuits. Included in the download of LTspice are macromodels for a majority of Analog Devices switching regulators, amplifiers, as well as a library of devices for general circuit simulation.

## Installation steps for windows 10

Follow the steps given below to install Ltspice simulator in windows 10.

1) Download LTspice from here [ltspice_download](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html#)
2) Now click on the download button for windows.The download tab is clearly shown in the picture below.
![ltspice downoad](https://user-images.githubusercontent.com/67196401/85849227-3512fb00-b7c8-11ea-98a5-528892f8a33a.PNG)
3) Now click on the application `ltspice` from your downloads and accept and continue. This is shown below.
![successful instal ltspice](https://user-images.githubusercontent.com/67196401/85849402-8327fe80-b7c8-11ea-98a4-498f695f9a70.PNG)
4) The simulator is installed and ready to use.

## Installation steps for Ubuntu

Follow the steps given below to install Ltspice simulator in Ubuntu.

1) LINUX Users have to install WINE from [here](https://wiki.winehq.org/Download) as LTSpice is not directly supported.
2) Similar steps are followed as mentioned for windows to download LTspice setup.
3) Right click on the downloaded setup file from your downloads and select the option Open With Wine Windows Program Loader.
4) After this, the basic installation steps are followed.

# Getting started with the design

1) Open Ltspice software by clicking on the shortcut icon vailable on your desktop. The window is similar to the one shown below.
![ltspice main window](https://user-images.githubusercontent.com/67196401/85849253-452ada80-b7c8-11ea-9d3d-79e5e875a459.PNG)
2) Follow this to open new schematic `File -> new -> new schematic`. This is clearly shown in the figure below.
![file-new schematic](https://user-images.githubusercontent.com/67196401/85849240-3fcd9000-b7c8-11ea-915d-8e252a8ad51c.png)
3) Have a look at the circuit diagrm given in the readme file and place components accordingly and complete the design. Designig the 10bit dac requires symbols and subcircuits to make the task easier. The components tab is shown in the figue below.
![edit-component](https://user-images.githubusercontent.com/67196401/85849237-3e03cc80-b7c8-11ea-88f8-e45040e358dc.png)
4) Add the osu180nm libraries on the schematic using `.include` command. The libraries are uploaded in the repository.
5) This way all the subcircuits are designed. 
6) To view spice netlist,follow this `view -> spice netlist`. This is shown in the figure below. To run this simulation in NGspice we have to make few changes to the netlist generated here to make it compatible with ngspice.
![view-spicenetlist](https://user-images.githubusercontent.com/67196401/85849277-4c51e880-b7c8-11ea-8a2a-054107dea26d.png)
7) To simulate the schematic designed so far follow the flow given `simulate -> edit simulation command -> enter transient analysis values(shown below) -> ok -> run`.
![simulate-run](https://user-images.githubusercontent.com/67196401/85849267-48be6180-b7c8-11ea-831f-2eb94a88d301.png).
![transient analysis](https://user-images.githubusercontent.com/67196401/85849275-4b20bb80-b7c8-11ea-9cfb-2249eba50d6f.png)
8) The plot appears. We can add or delete plot planes by clicking on the plot window. WR can aloso add traces using the same.

# NGspice installation 

ngspice is the open source simulator. 

## Ngspice installation for windows 10

Follow the steps below to install ngspice on windows10:

1) Click on [this](http://ngspice.sourceforge.net/download.html) to download ngspice software. 
![ngspice initial download](https://user-images.githubusercontent.com/67196401/85849263-478d3480-b7c8-11ea-9671-106272d1f433.PNG)
2) Do as shown in the image below. Click on the download button.
![ngspice download windows](https://user-images.githubusercontent.com/67196401/85849257-465c0780-b7c8-11ea-9ba1-f6a85f5025af.PNG)
3) You are directed to the download page. Do as shown below.
4) The software is now donloaded and ready to use.

## Ngspice installation for ubuntu

It’s Super Easy! simply click on Copy button to copy the command and paste into your command line terminal using built-in APT package manager.

1) Run update command to update package repositories and get latest package information.
`sudo apt-get update -y`

2) Run the install command with -y flag to quickly install the packages and dependencies.
`sudo apt-get install -y ngspice`

3) Check the system logs to confirm that there are no related errors. 

Note: `-y` flag means to assume yes and silently install, without asking you questions in most cases.

# Basic Block Diagram

![image](https://user-images.githubusercontent.com/67196401/85850273-1ada1c80-b7ca-11ea-83b5-da44a4f9aaf3.png)

# Circuit diagram

10bit digital-to-analog converter requires many resistors and switches. It is better to create subcircuits to built bigger designs. schematics for each subcircuit are designed and corresponding symbols are also designed. Each level is shown below.

## switch

![switch](https://user-images.githubusercontent.com/67196401/85849919-7526ad80-b7c9-11ea-9f11-c2b4338ae4e1.JPG)

## level 1: 2bit dac

The switch symbols are used to design a 2bit dac

![2bit](https://user-images.githubusercontent.com/67196401/85849886-67712800-b7c9-11ea-98b3-26025b8fb116.JPG)

## level 2: 3bit dac

Level 1 symbols are used to design 3bit dac

![3bit](https://user-images.githubusercontent.com/67196401/85849890-68a25500-b7c9-11ea-9c0d-bf77c11e7527.JPG)

## level 3: 4bit dac

Level 2 symbols are used to design 4bit dac

![4bit](https://user-images.githubusercontent.com/67196401/85849892-69d38200-b7c9-11ea-9c19-cb9590d1da5e.JPG)

## level 4: 5bit dac

Level 3 symbols are used to design 5bit dac

![5bit](https://user-images.githubusercontent.com/67196401/85849897-6b9d4580-b7c9-11ea-98a1-7926d100213c.JPG)

## level 5: 6bit dac

Level 4 symbols are used to design 6bit dac

![6bit](https://user-images.githubusercontent.com/67196401/85849900-6cce7280-b7c9-11ea-8f23-df760f569f4d.JPG)

## level 6: 7bit dac

Level 5 symbols are used to design 7bit dac

![7bit](https://user-images.githubusercontent.com/67196401/85849904-6dff9f80-b7c9-11ea-8e31-f0dc2ed3ef0e.JPG)

## level 7: 8bit dac

Level 6 symbols are used to design 8bit dac

![8bit](https://user-images.githubusercontent.com/67196401/85849907-6f30cc80-b7c9-11ea-80da-390b31c58c16.JPG)

## level 8: 9bit dac

Level 7 symbols are used to design 9bit dac

![9bit](https://user-images.githubusercontent.com/67196401/85849910-6fc96300-b7c9-11ea-8c99-88baa19e9bc4.JPG)

## level 9: 10bit dac

Level 8 symbols are used to design 10bit dac

![10bit](https://user-images.githubusercontent.com/67196401/85849913-70fa9000-b7c9-11ea-8d82-26d48d965e8a.JPG)

## 10 bit dac circuit diagram

Given below is the 10 bit dac circuit diagram. The analog voltage is 3.3v an digital voltage is 1.8v

![10bit crkt diagram](https://user-images.githubusercontent.com/67196401/85850898-56c1b180-b7cb-11ea-93f2-71b371416f53.JPG)

# Steps to run in Ngspice

1) Copy the netlist generated by ltspice and paste it notepad. Make the necessary changes to the netlist to make it compatible with ngspice software.Add the control statements, plot and print statements. The edited netlist is uploaded in the repository `10bit.cir.out`

2) Download the netlist and the MOS libraries uploaded above. 

3) Open ngspice and type in the command given below to open the path containg the files.
   `cd <path to your files>`
   
4) Now that ngspice is pointing to the directory containing the netlist files, the next command is to indicate which netlist file to open. This is done by typing in the command:
   `source <filename.file extension>`
   
   Here: source 10bit.cir.out
   
5) One of the advantages of ngspice is the ability to edit a netlist file quickly within ngspice without having to exit the program, open a text editor, make changes and then reopen ngspice. Editing a netlist file within ngspice is accomplished by simply typing the command: `edit`

6) To exit ngspice, type the command: `quit`

# Prelayout Graphs

## Vout/Vref plot

The below graph shows the `Vout/Vref vs digital code` for the digital values 0-31

![voutref_frst](https://user-images.githubusercontent.com/67196401/85852580-80300c80-b7ce-11ea-9627-862d2a1f4858.JPG)

The graph given below shows the `Vout/Vref vs digital code` for the digital values 480-511

![voutref_middle](https://user-images.githubusercontent.com/67196401/85852586-81f9d000-b7ce-11ea-9f55-d102185de5b2.JPG)

The graph given below shows the `Vout/Vref vs digital code` for the digital values 992-1023

![voutref_last](https://user-images.githubusercontent.com/67196401/85852589-832afd00-b7ce-11ea-8689-5093fc45ed6f.JPG)

The graph given below shows the `Vout/Vref va digital code` for values 0-31,480-511,992-1023

![voutref_all](https://user-images.githubusercontent.com/67196401/85852600-8920de00-b7ce-11ea-86bc-aef45c6d93ae.JPG)

## Differential non-linearity (DNL) graphs (@T=27C)

DNL vs digital code for 0-31 values:
![DNL_start](https://user-images.githubusercontent.com/67196401/85852885-29770280-b7cf-11ea-8a9a-977e1108addf.JPG)

DNL vs digital code for 480-511 values:
![DNL_middle](https://user-images.githubusercontent.com/67196401/85852883-27ad3f00-b7cf-11ea-876b-0b934590bd40.JPG)

DNL vs digital code for 992-1023 values:
![DNL_last](https://user-images.githubusercontent.com/67196401/85852879-254ae500-b7cf-11ea-85e2-5ce88742768b.JPG)

DNL vs digital code for 0-31, 480-511, 992-1023 values:
![DNL_lsb](https://user-images.githubusercontent.com/67196401/85852916-372c8800-b7cf-11ea-9f8f-77f8e44357cc.JPG)

## Integral Non-linearity (INL) graphs (@T=27C)

INL vs digital code for 0-31 values:
![INL_lsb_start](https://user-images.githubusercontent.com/58501983/86098341-980bd700-bad3-11ea-8b5e-7caebafedb1d.JPG)

INL vs digital code for 480-511 values:
![INL_middle](https://user-images.githubusercontent.com/67196401/85853255-d0f43500-b7cf-11ea-8311-a1b0d5d61781.JPG)

INL vs digital code for 992-1023 values:
![INL_last](https://user-images.githubusercontent.com/67196401/85853246-ce91db00-b7cf-11ea-9c06-821fd6de83ab.JPG)

INL vs digital code for 0-31, 480-511, 992-1023 values:
![INL_all](https://user-images.githubusercontent.com/67196401/85853260-d2bdf880-b7cf-11ea-82d8-ef95eafae096.JPG)

# Inverter layout and simulation
 The layout has been designed in electric vlsi layout design software. The layout is shown below.
 
 ![inverter_layout](https://user-images.githubusercontent.com/58501983/86098347-9c37f480-bad3-11ea-9b9d-85427eb6039d.JPG)
 
 The below picture shows the simulation output when a DC input is given.
 
 ![inverte_layout_dcinput](https://user-images.githubusercontent.com/58501983/86098591-f8027d80-bad3-11ea-8e6a-88e41da91e6c.JPG)

The picture below shows the simuation output when a piecewise linear input is given.

![inverter pwl input layout](https://user-images.githubusercontent.com/58501983/86098578-f2a53300-bad3-11ea-95fa-0a05059c4713.JPG)
 
 
