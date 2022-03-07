# Jeff
Controlling LEGO Linefollower vehicle by neural network using Python language.

**The assumption**

The assumption of the project is to build a vehicle controlled
by an artificial intelligence system based on neural network.
AI system must be able to set appropriate motoric power,
dependent on position of a black line on a track, in each of
four engines. The vehicle must not go off the track, and move
as slightly as possible.

![image](https://user-images.githubusercontent.com/56075332/157045398-7af0d8b2-2850-4d44-a090-6f71a9ea6508.png)


**Mathematical model**


* Normalization

The sensors are calibrated with a number from 0 to 100,
where 0 is no light reflection (black) and 100 is the maximum
value of reflected light. Due to the wear of the sensors, the
data had to be normalized.

* Basis

Depending on the values read from the sensors, the vehicle
can choose one of 6 options of moves (a detailed description can be found in the article).

* Neural Network

The assumption of the project was to create a neural
network and train it so that the vehicle would run smoother
than using the basic program. Our neural network is trained
by backward propagation of errors which calculates the
gradient of the error function and allow to change weights
on nodes. The network has 4 neurons in an input
layer, one for each of sensors and two hidden layers with
12 and 24 neurons. 21 neurons in an output layer represents
percentages from 0 to 100%, every 5 percent. We create two
neural networks, one for the left, and one for the right engines.

![image](https://user-images.githubusercontent.com/56075332/157046093-f96deeb4-6453-41f3-9caf-1b5a93a687f4.png)


A decision of neural network, a value of one of output
neurons is used in an equation below to calculate
percentage of maximum power of the engines which will
change into appropriate turn. The equation is given for the
left side.

MOCL = MAXMOC * stronaL/mianownik

Where stronaL is an index of chosen output neuron
multiplied by 5 to get a percentage value.
mianownik depends on which neural network made the
decision on the higher index.

* Testing

![image](https://user-images.githubusercontent.com/56075332/157046589-52db43a9-ac5b-4f0a-86a2-752a247c3301.png)

First we needed a database with sensors values and turns
calculated by the basic program. The vehicle collected data which was sent to the program with neural
network. Neural network has been correcting weights and
learning to make appropriate decisions on the trace. A fregment of the database is shown below. 

![image](https://user-images.githubusercontent.com/56075332/157046791-3ff74fe6-292f-4b03-859e-acb84328444a.png)


* Conclusions

Neural network with backpropagation algorithm allowed to
get really satisfying results, at least in the simulation. But
calculations are too slow and the vehicle is not keeping up with
making decisions. There are huge delays so that the vehicle
runs mainly under the control of the basic program, which
helps to go back to the line, after getting off the track.

