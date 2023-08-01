# SNAPL_force_matching
The aim of this project is to create a visual feedback system which can be presented to 
a participant as they complete a force-matching task. In a force-matching task, a
participant is asked to squeeze a dynamometer (a device which measures force) with the 
goal of hitting and maintaining the target force within a specified range.

For example, a participant may be tasked to hit a target force of 10 kg &plusmn; 1 kg for 15 seconds. (I know kg is not a unit of force, 
but it is the convention of many experiments and measuring devices; just multiply by 
9.8 m/s<sup>2</sup> to get Newtons). In its final form, the product of this project would present to the particpant a
thin, white horizontal bar centered along the x-axis of the monitor. There would be a bracket positioned somewhere
along the vertical, with the y-coordinate of its midpoint corresponding to the target force of 10 kg and its length proportional to the &plusmn; 1 kg margin of error.
As the participant squeezes the dynamometer, the bar would increase in height, turning green in color whenever it
falls within range of the bracket.

In this project, we will be using hardware and software purchased from BIOPAC, in
combination with E-prime 2.0 software in order to create the visual feedback system that
we want. As a broad overview, the hardware from BIOPAC directly collects the 
force data from the participant as they squeeze the dynamometer. This data then gets sent to BIOPAC's
Acqknowledge software, which displays the data in a graph. The data also gets sent to a python script via
Network Data Transfer, a feature that is already built into the biopac software. The python script that we use is
an adaptation of an example script provided by BIOPAC. Included in our adaptation is a portion of code that sends this data
now to E-prime. E-prime is the program that is presented to directly the participant, and it is where the force data gets translated
into the visual feedback of the moving, color-coded bar.

Less important, but still relevant to certain aspects of this project, is our desire to collect two separate streams of EMG data
from the participant in addition to the dynamometer force data. This is mainly reflected in our adaptation of the python code, 
but is otherwise not too important to think about if you are not interested.

A list of materials that we purchase/use in this project is provided below:
1. [BIOPAC's Hand Clench Dynamometer for MRI](https://www.biopac.com/product/hand-clench-dynamom-for-mri/): measures the participant's grip strength
2. [BIOPAC's MP160 Unit](https://www.biopac.com/product-category/research/systems/mp150-starter-systems/): the central data collecting unit
3. [BIOPAC's DA100C Unit](https://www.biopac.com/product/general-purpose-transducer-amplifier/): an add-on to the MP160 to which the dynamometer connects
4. [BIOPAC's Acqknowledge 5.0 software](https://www.biopac.com/product/acqknowledge-software/): receives and displays the data on a graph in real time;
   also controls the data sampling rate, the length of data acquisition, and which channels are in use. 
6. [E-prime 2.0](https://pstnet.com/products/e-prime/): program used in many psychology studies; used to present instructions and visual feedback to the participant;
   also includes a script that stores the incoming dynamometer data in a csv file

There was truly a dearth of examples and documentation from BIOPAC, which made this whole process very difficult at times. And also, I could not find examples of E-prime communicating with Python,
which also added some hurdles to this process. It took a lot of scavenging and Frankensteining code to get a functional product. I'm also not a programmer by any means (intro to CS is all I've got under my belt), 
so if there are any improvements I could make, which I'm sure there are, please let me know! I hope this is helpful to anyone! 



   

   
