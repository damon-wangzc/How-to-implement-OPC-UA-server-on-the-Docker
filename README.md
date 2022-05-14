# How to implement OPC UA server on the Docker
## Using the [Microsoft IoT Edge OPC UA PLC](https://hub.docker.com/_/microsoft-iotedge-opc-plc)
This is a simple tutorial for the beginner who want to run the OPC UA server on the Docker and use an OPC UA browser to check the data.

## Prerequisites
1. You have installed Docker on your Windows PC/MAC/Linux device.(This totorial uses macOS)
2. Need an OPC UA Browser

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


## Download and install [Prosys OPC UA Browser](https://downloads.prosysopc.com/opc-ua-browser-downloads.php)

## Open Prosys OPC UA Browser and enter the address
the address form is as follows, "192.168.1.105" is the IP address of your device, 50000 is the port to get access
```
opc.tcp://192.168.1.105:50000
```
<img width="1068" alt="Screenshot 2022-05-14 at 21 23 13" src="https://user-images.githubusercontent.com/53770568/168445698-9010cd66-ec45-40a0-b14e-22b0f1290a4d.png">

Press enter and choose "Sign & Encrypt" and "Basic256Sha256"
<img width="1112" alt="Screenshot 2022-05-14 at 21 23 27" src="https://user-images.githubusercontent.com/53770568/168445702-0ee6e2ea-7c86-43d2-b819-c3c191efc517.png">

Then click "Accept Permanently" or "Accept Once"
![WechatIMG43](https://user-images.githubusercontent.com/53770568/168445799-cc8af103-22d7-46ec-963f-80bd61109c37.png)

Then click "Accept Permanently" or "Accept Once"

Now you can see the data
<img width="1112" alt="Screenshot 2022-05-14 at 21 26 43" src="https://user-images.githubusercontent.com/53770568/168445746-2b88a7ef-c2cd-4459-9bb5-aeef6c8c5c96.png">




