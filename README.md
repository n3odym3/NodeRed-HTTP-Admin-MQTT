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
You can test one device by running two instances of NodeRed in parallel or two container Docker (on different ports).
