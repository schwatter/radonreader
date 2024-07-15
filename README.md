# RadonReader

This project provides a tool which allows users collect current radon data from FTLab Radon Eye RD200 (Bluetooth only version).


# Hardware Requeriments
- FTLabs RadonEye RD200 
- Raspberry Pi 
- Bluetooth LE (Low Energy) support


# Software Requeriments
- Python 3.x.x
- bluepy Python library
<pre><code>sudo apt install python3-pip libglib2.0-dev
sudo pip3 install bluepy</code></pre>
- paho-mqtt
<pre><code>sudo apt install python3-paho-mqtt</code></pre>


# History
- 0.4 - Added Python3 support
- 0.3 - Added MQTT support


# Usage
<pre><code>usage: radon_reader.py [-h] -a ADDRESS [-b] [-v] [-s] [-m] [-ms MQTT_SRV]
                       [-mp MQTT_PORT] [-mu MQTT_USER] [-mw MQTT_PW] [-ma]

RadonEye RD200 (Bluetooth/BLE) Reader

optional arguments:
  -h, --help       show this help message and exit
  -a ADDRESS       Bluetooth Address (AA:BB:CC:DD:EE:FF format)
  -b, --becquerel  Display radon value in Becquerel (Bq/m^3) unit
  -v, --verbose    Verbose mode
  -s, --silent     Only output radon value (without unit and timestamp)
  -m, --mqtt       Enable send output to MQTT server
  -ms MQTT_SRV     MQTT server URL or IP address
  -mp MQTT_PORT    MQTT server service port (Default: 1883)
  -mu MQTT_USER    MQTT server username
  -mw MQTT_PW      MQTT server password
  -ma              Enable Home Assistant MQTT output (Default: EmonCMS)</code></pre>
  
# Example
<pre><code>
python /opt/rr/radon_reader.py -a E2:63:C7:B0:CC:EE -s -b -ms 192.168.178.13 -m -mp 1883 -mu username -mw password
</code></pre>