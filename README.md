## Build MicroPython for esp8266 in Docker

![bash-small](https://user-images.githubusercontent.com/13176091/54089754-070c6c00-4375-11e9-8495-d06e9d5f3fe3.png)  

Cборка ```FIRMWARE``` для микроконтроллера ```ESP8266``` в Docker    

ля сборки Docker, необходимо:  

* [MicroPython port to ESP8266](https://github.com/micropython/micropython/tree/master/ports/esp8266#micropython-port-to-esp8266)  
* [SDK for ESP8266/ESP8285 chips](https://github.com/pfalcon/esp-open-sdk)   
  
* [esptool GitHub](https://github.com/espressif/esptool)  
* [esptool PyPI](https://pypi.org/project/esptool/)  
* [setuptools PyPI](https://pypi.org/project/setuptools/)      
* [pySerial PyPI](https://pypi.org/project/pyserial/)  
* [pySerial GitHub](https://github.com/pyserial/pyserial)  
* [pySerial Documentation](https://pyserial.readthedocs.io/en/latest/shortintro.html)   


#### Сборка Docker для ESP8266
```bash
git clone https://github.com/gwvsol/ESP8266-ESP32-Script-to-build-MicroPython.git

cd ESP8266-ESP32-Script-to-build-MicroPython/esp8266

make build
```

#### Использование

```bash
drwxr-xr-x 2 work work 4096 авг  9 21:07 firmware
drwxr-xr-x 3 work work 4096 авг  9 11:19 modules
```

Модули и библиотеки которые необходимо включить в прошивку необходимо поместить в директорию ```modules```  
Собранная прошивка будет в директории ```firmware```  

```bash
make pre-build	- Preparing to building Docker
make build	    - Building a Docker
make start	    - Start of Docker
make stop       - Stopping Docker
make remove	    - Deleting a Docker image
make pyserial   - Monitoring the operation of the microcontroller via pyserial
make minicom    - Monitoring the operation of the microcontroller via minicon
make get-mac    - Getting the Mac address of the microcontroller
make get-id	    - Getting the microcontroller ID
make upload	    - Loading firmware to the microcontroller
make clean	    - Cleaning the microcontroller 
```

#### Сборка прошивки

```bash
make clean	    - Clearing the SDK
make modules    - Copying the source code
make build	    - The build of the firmware
```

#### Работа микроконтроллером 

```bash
make pyserial   - Monitoring the operation of the microcontroller via pyserial
make minicom    - Monitoring the operation of the microcontroller via minicon
make get-mac    - Getting the Mac address of the microcontroller
make get-id	    - Getting the microcontroller ID
make upload	    - Loading firmware to the microcontroller
make clean	    - Cleaning the microcontroller
```

***