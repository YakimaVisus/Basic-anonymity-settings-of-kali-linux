# Базовые настройки анонимности kali linux
 Для начала сделаем так, чтобы при каждой загрузке системы MAC адрес менялся на рандомный, это никогда не бывает лишним. И для этого нам нужно открыть файл /etc/NetworkManager/NetworkManager.conf и изменить его содержимое, на такое:    
 
> [main] 
>plugins=ifupdown,keyfile
> 
>[ifupdown] 
>managed=false 
>
>[connection] 
>wifi.cloned-mac-address=random 
>
>[connection] 
>ethernet.cloned-mac-address=random 

# Добавим возможность пускать весь трафик системы через сеть Tor:
> sudo apt-get install tor  
> sudo systemctl start tor  
> git clone https://github.com/ruped24/toriptables2  
> cd toriptables2/  
> sudo mv toriptables2.py /usr/local/bin/  

_Теперь направляем весь трафик через Tor, командой:_
> sudo toriptables2.py -l  

_Чтобы сменить айпишник_
> sudo kill -HUP $(pidof tor)  

