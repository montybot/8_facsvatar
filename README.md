# Use FACSvatar with FACSHuman
__DISCLAIMER__ 
At this time the frame rate is very low on small configuration.

## How it works

    MakeHuman        | localhost:5571 <-----> Zmq bridge <----> localhost:5570 | Openface
    FACSvatar plugin |                         FACSvatar                       | with zmq

## Installation procedure
To use FACSvatar with FacsHuman, you need to follow these steps.

Install MakeHuman from source (less difficult than trying to integrate zeromq inside standalone version)
http://www.makehumancommunity.org/wiki/Documentation:Running_MakeHuman_from_source

And follow the procedure to install FacsHuman from here, same as for the standalone version.
https://github.com/montybot/FACSHuman

Put FACSvatar __7_FACSHuman.py__ inside the plugin directory

Grab it from 
https://github.com/montybot/8_facsvatar

Launch MakeHuman and activate it inside Settings/Plugins

Close MakeHuman

## For makehuman
Install python 2.7 if needed
Install zeromq for python 2.7
```
pip2 install zmq
```
## For FACSvatar
Install zeromq for python 3.x
```
pip install zmq
```

Download and unzip Openface_2.1.0_zeromq.zip from here :
https://github.com/NumesSanguis/FACSvatar/releases
change that lines inside config.xml in the the openface directory
```
<IP>127.0.0.1</IP>
<Port>5570</Port>
```

Download or clone FACSvatar from here
https://github.com/NumesSanguis/FACSvatar

## To run all of these softwares together
Start MakeHuman and if the plugin is correctly installed you have a new FACSvatar tab inside Modeling

You can start and stop FACSvatar listener from here

Start the bridge and FACSvatar module
Launch main.py from
```
C:\...YOUR_LOCATION...\FACSvatar-master\modules\process_bridge
```

Or make a .bat file with :
```
CALL cd  C:\...YOUR_LOCATION...\FACSvatar-master\modules\process_bridge
CALL python main.py
pause
```

Start the zmq version of Openface and open the webcam in File-> Open webcam

__That's all folks__ :+1:
