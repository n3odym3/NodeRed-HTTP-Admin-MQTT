# NodeRed-HTTP-Admin-MQTT
Remotely modify and deploy a NodeRed flow from another NodeRed via MQTT (and the HTTP Admin API)

## Use case
* NodeRed on different devices (2 or more)
* NodeRed Master : full access (NodeRed GUI editor)
* NodeRed Slave : only MQTT 

This demo allows to pull any flow of the Slave, deploy it on a Sandbox in the Master editor to modify it then pull it back to the Slave (all via MQTT). 

This sketch could also be used to deploy a flow in many devices in parallel and many more thanks to the HTTP-Admin API : https://nodered.org/docs/api/admin/methods/ )

## Instructions

### Installation 

#### 1) Deploy the Master and the Slave flows
You can test on one device by running two instances of NodeRed in parallel or two container Docker (on different ports).

Don't forget to setup the MQTT.

If you have different Slaves you can select a specific Slave with the MQTT Topic (Ex : Get/Flows/Slave/01 | Get/Flows/Slave/02 ...)

#### Master
<img src="/Images/Master.PNG?raw=true" width="100%"> 

#### Slave
<img src="/Images/Slave.PNG?raw=true" width="100%">

#### 2) If your Flow is password protected, set the USER and the PASSWORD (in both flows) then generate a Token
<img src="/Images/UserPass.png?raw=true" width="100%">

#### 3) Set the Sandbox ID (Master)
<img src="/Images/SandboxID.png?raw=true" width="100%">

#### 4) Pull the Flows config of the Slave
Clic on the inject Node, the full Flows config of the Slave will appear in the debug.
Explore the array to find the "Label" of the Flow that you want to edit and copy it's corresponding ID
<img src="/Images/GetFlows.png?raw=true" width="100%">

#### 5) Paste the ID in the "Pull Flow" Node. Then Pull the Flow
The slected Flow will be deployed in the Sandbox of the Master
<img src="/Images/SetEditID.png?raw=true" width="100%">

#### 6) Edit the Flow
Go to the "Sandbox" tab and edit the Flow
<img src="/Images/Sandbox.png?raw=true" width="100%">

#### 7) Push the edited flow to the Slave
This action will push the Flow to the Slave and clear the Sandbox
<img src="/Images/Push.png?raw=true" width="100%">

#### Congratulation ! You have successfully edited a Flow without being connected to the device.
