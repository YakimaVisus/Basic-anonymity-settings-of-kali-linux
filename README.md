# Базовые настройки анонимности kali linux
 Для начала сделаем так, чтобы при каждой загрузке системы MAC адрес менялся на рандомный, это никогда не бывает лишним. И для этого нам нужно открыть файл /etc/NetworkManager/NetworkManager.conf и изменить его содержимое, на такое:  
 [main] 
plugins=ifupdown,keyfile
 
[ifupdown] 
managed=false 

[connection] 
wifi.cloned-mac-address=random 

[connection] 
ethernet.cloned-mac-address=random 
