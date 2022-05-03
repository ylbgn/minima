# Minima-Node-Setup-Guide

- **Minima VPS Kurulumu:**
- **root olarak vps'ninize giriş yapın**
- **Kök dizininde olduğunuza emin olun**
- **Minima'nın daha eski sürümleri kuruluysa, lütfen bir sonraki adıma geçmeden önce bunları kaldırın. Minima'yı kaldırmak için lütfen bu betiği çalıştırın:**
```
wget -O minima_cleanup_v98.sh https://raw.githubusercontent.com/minima-global/Minima/master/scripts/minima_cleanup_v98.sh && chmod +x minima_cleanup_v98.sh && sudo ./minima_cleanup_v98.sh
```
- **İlk kez minima kuruyorsanız java'nın son sürümünün yüklü olduğuna emin olun. **

- **Java versiyon kontrol etme **
```
java --version
```
- **Java yüklü değilse örnekteki gibi yükleyin**
```
sudo apt-get install openjdk-8-jre```

- **Kök dizinde aşağıdaki betiği çalıştırın ve bir kaç dakika bekleyin** 
```
wget -O minima_setup.sh https://raw.githubusercontent.com/minima-global/Minima/master/scripts/minima_setup.sh && chmod +x minima_setup.sh && sudo ./minima_setup.sh -r 9002 -p 9001
```

- **Aşağıdaki adrese gidin ve teşvik programına kayıt olun** 

```
https://incentive.minima.global/account/login
```
- **Minima çalışırken, yukarıdaki teşvik programı web sitesinden kendi kimliğinizi kopyalayıp aşağıdaki id: yazan yere yapıştırıp komut satırına yazın**
```
sudo apt install curl
curl 127.0.0.1:9002/incentivecash%20uid:xxx-xxx-xxx-xxx-xxx
```

- **Düğüm günlük ping gönderecek ve her ping bir MİNİMA ödül hesabınıza eklenecek. incentive sitesinden günlük ping sayılarını kontrol edebilirsiniz.**  

- **Yararlı kodlar**

```
ctrl-c : Exits the Minima logs (Minima will continue to run in the background)
journalctl -u minima_9001 -f : Show the Minima logs
sudo ps -fC java : Shows all running Java processes

sudo apt install curl : allows you to use curl commands to interact with minima
Then y (for Yes)

sudo apt install jq : allows you to use jq to make the output look readable
Then y (for Yes)

Stopping/starting Minima (Service must be called minima.service)
sudo systemctl stop minima_9001 - Stop the Minima service
sudo systemctl disable minima_9001 - Disable the Minima service
sudo systemctl enable minima_9001 - Enable the Minima service 
sudo systemctl start minima_9001 - Start the Minima service

Interacting with Minima
curl 127.0.0.1:9002/status | jq - shows the status of Minima 
curl 127.0.0.1:9002/incentivecash | jq - shows your incentive cash balance
curl 127.0.0.1:9002/help | jq - shows the full list of commands
```





