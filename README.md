# How to implement OPC UA server on the Docker
## Using the [Microsoft IoT Edge OPC UA PLC](https://hub.docker.com/_/microsoft-iotedge-opc-plc)
This is a simple tutorial for the beginner who want to run the OPC UA server on the Docker and use an OPC UA browser to check the data.

## Prerequisites
1. You have installed Docker on your Windows PC/MAC/Linux device.(This totorial uses macOS)

## Pull the image
open your terminal and enter the following code, wait for downloading the latest version
```
docker pull mcr.microsoft.com/iotedge/opc-plc
```

## Run the container
using the following code to start the OPC UA server
```
docker run --rm -it -p 50000:50000 -p 8080:8080 --name opcplc mcr.microsoft.com/iotedge/opc-plc:latest --pn=50000 --autoaccept --sph --sn=5 --sr=10 --st=uint --fn=5 --fr=1 --ft=uint --ctb --scn --lid --lsn --ref --gn=5
```
Then you can see the following 
![Screenshot 2022-05-14 at 21 01 53](https://user-images.githubusercontent.com/53770568/168445088-2dcdab38-4974-4b72-848b-08af05c6993a.png)
