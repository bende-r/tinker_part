# Installation

**_Clone_**

```bash
sudo git clone https://github.com/bende-r/tinker_part.git
cd tinker_part
```

**_ble_**

```bash
sudo apt-get install libglib2.0-dev
```

## Install packages

**_From libs.txt_**

```bash
sudo pip3 install -r libs.txt
```

**_Manualy_**

```bash
sudo pip3 install bluepy
sudo pip3 install btlewrap
sudo pip3 install logger
sudo pip3 install Flask
sudo pip3 install Flask-API
```

# Run

To start

```bash
 python3 main.py
```

To view device in DB

```http
http://host:5000
```

```json
[
  {
    "mac": "4c:65:a8:da:a8:91",
    "avg_battery": 99.0,
    "avg_temperature": 27.791000000000025,
    "avg_humidity": 42.06300000000002,
    "is_online": 1
  }
]
```

To scan available devices

```http
http://host:5000/scan
```

**\_All mac of this sensor start with **4C:65:A8:XX:XX:XX**\_**

```json
[
  {
    "RSSI": -82,
    "mac": "d7:c7:79:55:6e:e3",
    "type": "random"
  },
  {
    "RSSI": -92,
    "mac": "9c:8c:6e:0f:b8:68",
    "type": "public"
  },
  {
    "RSSI": -94,
    "mac": "77:ac:09:cd:67:9f",
    "type": "random"
  },
  {
    "RSSI": -52,
    "mac": "01:eb:29:c4:23:55",
    "type": "random"
  },
  {
    "RSSI": -50,
    "mac": "46:51:a9:91:77:e0",
    "type": "random"
  },
  {
    "RSSI": -60,
    "mac": "4c:65:a8:da:a8:91",
    "type": "public"
  }
]
```

To get device by **_mac_**

```http
http://host:5000/devices/4C:65:A8:XX:XX:XX
```

```json
{
  "avg_battery": 99.0,
  "avg_humidity": 40.56953125000001,
  "avg_temperature": 27.84765625000001,
  "is_online": 1,
  "mac": "4c:65:a8:da:a8:91"
}
```

To add device by **_mac_**

```http
http://host:5000/devices?mac=4C:65:A8:XX:XX:XX
```

```json
{
  "avg_battery": 0.0,
  "avg_humidity": 0.0,
  "avg_temperature": 0.0,
  "is_online": 0,
  "mac": "4c:65:a8:da:a8:91"
}
```

To get online devices

```http
http://host:5000/devices/online
```

```json
[
  {
    "mac": "4c:65:a8:da:a8:91",
    "avg_battery": 99.0,
    "avg_temperature": 27.791000000000025,
    "avg_humidity": 42.06300000000002,
    "is_online": 1
  }
]
```
