# Traffic-Light-Controller

Traffic Light Controller
Introduction
Before the fabrication of lots of vehicles, there is no such thing called Traffic Lights since aggregation of pedestrians and vehicles coming and going in a particular locality during the same time is insignificant enough not to create a crowded traffic Lines. In addition before traffic Lights it is a person who is controlling the flow of vehicles and pedestrians. The first system of traffic signals was installed as a way to replace police officer control of vehicular traffic outside the Houses of Parliament in London on 9 December 1868. In the first two decades of the 20th century, semaphore traffic signals like the one in London were in use all over the United States with each state having its own design of the device. In many cases, it was controlled by a traffic officer who would blow a whistle before changing the commands on this signal to help alert travelers of the change. Eventually, Traffic Lights are getting more sophisticated and they are even AI supported controllers that command by detecting the number of pedestrians and vehicles moving.
    Here in our project we have tried to design a Traffic Light controller system that controls a pedestrian who wants to cross a highway by using a push button to signal vehicles before he passes the road. In addition to this we included another traffic light for the pedestrian to insure that he pressed the signaling push button.
Design Procedure and Analysis 
Here in our project we designed the System using what we have learned in the class.  We first think about the strategy to design the controller and we arrived at using counters specifically three bit counter to design the Traffic Lights sequence. And the counter just count starting from 7(111) to 0(000), so in this sequence of numbers we drive equations for the lights sequences and based on that equation we designed the circuit. Here is what we did step by step:
1.	The state diagram we constructed to design three bit step down counter with a push-button, which is controlling when to signal.










2.	Identify the number and Type of flip-flops required:-
Here in this part we have 8 states, so we need at least 3 flip flops to design the system. Hence for the sake of simplicity we choose to use 3 D – flip flops. We choose D flip flops because it is simpler to identify the excitation state for each case in the truth table.
3.	Sate and Excitation Table
Present state	Next state	Flip-flop inputs
|A	|B	|C	|M	|A+	|B+	|C+	|DA	|DB	|DB|
----------------------------------------
|0	|0	|0	|0	|0	|0	|0	|0	|0	|0 |
|0	|0	|0	|1	|1	|1	|1	|1	|1	|1 |
|0	|0	|1	|0	|0	|0	|0	|0	|0	|0 | 
|0	|0	|1	|1	|0	|0	|0	|0	|0	|0 |
|0	|1	|0	|0	|0	|0	|1	|0	|0	|1 |
|0	|1	|0	|1	|0	|0	|1	|0	|0	|1 |
|0	|1	|1	|0	|0	|1	|0	|0	|1	|0 |
|0	|1	|1	|1	|0	|1	|0	|0	|1	|0 |
|1	|0	|0	|0	|0	|1	|1	|0	|1	|1 |
|1	|0	|0	|1	|0	|1	|1	|0	|1	|1 |
|1	|0	|1	|0	|1	|0	|0	|1	|0	|0 |
|1	|0	|1	|1	|1	|0	|0	|1	|0	|0 |
|1	|1	|0	|0	|1	|0	|1	|1	|0	|1 |
|1	|1	|0	|1	|1	|0	|1	|1	|0	|1 |
|1	|1	|1	|0	|1	|1	|0	|1	|1	|0 |
|1	|1	|1	|1	|1	|1	|0	|1	|1	|0 |
5.	Using K-maps to drive the Logic equations
Here in this part, we used what we call it a karnaugh map to determine logic equations for each flip-flop inputs namely DA  ,DB ,DC as a function of input variables(A,B,C,M).

CM\AB	00	01	11	10
 00
	
1	
01	1	
1	
11			1	1
10			1	1
CM\AB	00	01	11	10

00	
		1
01	1	
	1
11		1	1	
10		1	1	

	

CM\AB	00
01
11	10
00
	1	1	1
01	1	1	1	1
11				
10				









After we determined the Logic equations of flip-flop inputs, then we synthesized the equation for output values we assigned for each color Lights. So based on this, we assigned red Light to lit-up on 5, 6 and 7 through the counter sequence, 4 for yellow Light and finally we assigned 0, 1, 2, 3for Green Light. In addition green Light is always on if the push button is not pressed.  
5.	Truth table and Logical equations for the Output states
Here in this part, we tried to express the output state as a function of input variables (A, B, C, and M).
A	B	C	Green	Yellow	Red
|0	0	0	1	0	0|
|0	0	1	1	0	0|
|0	1	0	1	0	0|
|0	1	1	1	0	0|
|1	0	0	0	1	0|
|1	0	1	0	0	1|
|1	1	0	0	0	1|
|1	1	1	0	0	1|
C/AB	00	01	11	10
0		
1	
1			1	1
6.	Logic equations using K-maps
C\AB	00	01	11	10
0	1	1	0	0
1	1	1	0	0
C\AB	00	01	11	10
0			
1
1				


7.	Finally we designed the system on proteus 8 base on what we drive in the above steps. 
	Flip-flops with their corresponding inputs
 

	Counter using seven segment display
 
	Traffic Lights
 
	Momentary Push-Button for the pedestrian 
 
	The whole Circuit
 
