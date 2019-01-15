# UPnP for Homebridge

[Universal Plug and Play (UPnP)](http://upnp.org/resources/documents/UPnP_UDA_tutorial_July2014.pdf) is a set of networking protocols that permits networked devices to seamlessly discover each other's presence on the network and establish functional network services.

## Supported devices types

### [MediaRenderer v1](http://upnp.org/specs/av/UPnP-av-MediaRenderer-v1-Device.pdf)

Most of Smart TV supports this device type.

It requires implementation of [RenderingControl v1](http://upnp.org/specs/av/UPnP-av-RenderingControl-v1-Service.pdf) service,
 which allow control volume and mute states.
 
Current implementation of plugin automatically discover UPnP devices and add Lightbulb accessory
which allow to control volume by slider and mute by on/off.


## Install

```bash
$ npm install -g homebridge-upnp
```

## Usage

Simply add to your Homebridge config new platform called "UPnP" and restart Homebridge.

```json
{
  "platforms": [
      {
        "platform": "UPnP"
      }
  ]
}
```

Also you can provide custom config for [node-ssdp](https://github.com/diversario/node-ssdp/tree/v4.0.0) by `ssdpClient` and `ssdpServer` options:

```json
{
  "platforms": [
      {
        "platfrom": "UPnP",
        "ssdpClient": {
          "interfaces": ["br0"]
        },
        "ssdpServer": {
          "interfaces": ["br0"]
        }
      }
  ]
}
```
