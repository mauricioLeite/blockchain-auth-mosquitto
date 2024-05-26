# Blockchain Auth mosquitto
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

Implement a authentication for mosquitto based on blockchain technology.

mosquitto_sub -h localhost -t "sensor/temperature"

mosquitto_pub -h localhost -t sensor/temperature -m 23

# Running Mosquitto Go Auth on WSL
WSL Version: Ubuntu 20.04.6 LTS
Codename: focal 

[Reference project repo](https://github.com/iegomez/mosquitto-go-auth#requirements)

Install needed dependencies:

`sudo apt-get install libwebsockets15 libwebsockets-dev libc-ares2 libc-ares-dev openssl uuid uuid-dev libcjson-dev`


Download mosquitto and extract it:
```
wget http://mosquitto.org/files/source/mosquitto-2.0.15.tar.gz
tar xzvf mosquitto-2.0.15.tar.gz
cd mosquitto-2.0.15
```
Modify config.mk setting websocket support to `yes`.

Follow the principal tutorial until the section [building the plugin](https://github.com/iegomez/mosquitto-go-auth#building-the-plugin)

Install Go  

```
curl -OL https://golang.org/dl/go1.21.5.linux-amd64.tar.gz
echo "e2bc0b3e4b64111ec117295c088bde5f00eeed1567999ff77bc859d7df70078e go1.21.5.linux-amd64.tar.gz" | sha256sum --check
sudo tar -C /usr/local -xvf go1.21.5.linux-amd64.tar.gz
```

Export go PATH from `.zshrc` (or `.profile` if using default shell):
```
export PATH=$PATH:/usr/local/go/bin
```

Source the file again:
```
source ~/.zshrc
```

Test if installation is successfully with:
`go version`

After that, only need to make the `go-auth.so`.

Follow to [Configuration](https://github.com/iegomez/mosquitto-go-auth#configuration) section.  
