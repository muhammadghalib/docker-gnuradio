# Docker GNU Radio

Build :  
for v3.7 = sudo docker build -t ubuntu:gnuradio-v37 .  
for v3.8 = sudo docker build -t ubuntu:gnuradio-v38 .  
for v3.9 = sudo docker build -t ubuntu:gnuradio-v39 .  

for v3.7 Transmitter = sudo docker build -t ubuntu:gnuradio-v37-transmitter .  
for v3.7 Receiver = sudo docker build -t ubuntu:gnuradio-v37-receiver .  

Run :  
for v3.7 transmitter :  
sudo docker run \  
--net=host \  
--env="DISPLAY" \  
--volume="$HOME/.Xauthority:/root/.Xauthority:rw" \  
--privileged \  
--device=/dev/bus/usb:/dev/bus/usb \  
-v /dev/bus/usb:/dev/bus/usb \  
--device=/dev/snd \  
-v persistent-37-transmitter:/home/gnuradio-transmitter/persistent \  
--group-add=audio \  
-it ubuntu:gnuradio-v37-transmitter bash  

for v3.7 receiver :  
sudo docker run \  
--net=host \  
--env="DISPLAY" \  
--volume="$HOME/.Xauthority:/root/.Xauthority:rw" \  
--privileged \  
--device=/dev/bus/usb:/dev/bus/usb \  
-v /dev/bus/usb:/dev/bus/usb \  
--device=/dev/snd \  
-v persistent-37-receiver:/home/gnuradio-receiver/persistent \  
--group-add=audio \  
-it ubuntu:gnuradio-v37-receiver bash  


 
