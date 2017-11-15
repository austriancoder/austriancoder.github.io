---
layout: post
title: M-Audio Keystation 49e USB midi-keyboard
date: '2008-01-07 13:01:11'
---


Wie ich auf der Seite von linuxdriverproject sehen kann, schein das M-Audio 49e midi-keyboard und Linux nicht zu funktionieren. Dem kann ich nicht zustimmen und werde hier ein kleines HowTo posten.

- Als ersten einmal die Ausgabe von *lsusb -vvv*:

Bus 002 Device 012: ID 0a4d:0090 Evolution Electronics, Ltd
 Device Descriptor:
 bLength 18
 bDescriptorType 1
 bcdUSB 1.00
 bDeviceClass 0 (Defined at Interface level)
 bDeviceSubClass 0
 bDeviceProtocol 0
 bMaxPacketSize0 64
 idVendor 0x0a4d Evolution Electronics, Ltd
 idProduct 0x0090
 bcdDevice 1.13
 iManufacturer 1 Evolution Electronics Ltd.
 iProduct 2 USB Keystation 49e
 iSerial 0
 bNumConfigurations 1
 Configuration Descriptor:
 bLength 9
 bDescriptorType 2
 wTotalLength 101
 bNumInterfaces 2
 bConfigurationValue 1
 iConfiguration 3 Audio Class
 bmAttributes 0xc0
 Self Powered
 MaxPower 0mA
 Interface Descriptor:
 bLength 9
 bDescriptorType 4
 bInterfaceNumber 0
 bAlternateSetting 0
 bNumEndpoints 0
 bInterfaceClass 1 Audio
 bInterfaceSubClass 1 Control Device
 bInterfaceProtocol 0
 iInterface 0
 AudioControl Interface Descriptor:
 bLength 9
 bDescriptorType 36
 bDescriptorSubtype 1 (HEADER)
 bcdADC 1.00
 wTotalLength 9
 bInCollection 1
 baInterfaceNr( 0) 1
 Interface Descriptor:
 bLength 9
 bDescriptorType 4
 bInterfaceNumber 1
 bAlternateSetting 0
 bNumEndpoints 2
 bInterfaceClass 1 Audio
 bInterfaceSubClass 3 MIDI Streaming
 bInterfaceProtocol 0
 iInterface 0
 MIDIStreaming Interface Descriptor:
 bLength 7
 bDescriptorType 36
 bDescriptorSubtype 1 (HEADER)
 bcdADC 1.00
 wTotalLength 65
 MIDIStreaming Interface Descriptor:
 bLength 6
 bDescriptorType 36
 bDescriptorSubtype 2 (MIDI_IN_JACK)
 bJackType 1 Embedded
 bJackID 1
 iJack 0
 MIDIStreaming Interface Descriptor:
 bLength 6
 bDescriptorType 36
 bDescriptorSubtype 2 (MIDI_IN_JACK)
 bJackType 2 External
 bJackID 2
 iJack 0
 MIDIStreaming Interface Descriptor:
 bLength 9
 bDescriptorType 36
 bDescriptorSubtype 3 (MIDI_OUT_JACK)
 bJackType 1 Embedded
 bJackID 3
 bNrInputPins 1
 baSourceID( 0) 2
 BaSourcePin( 0) 1
 iJack 0
 MIDIStreaming Interface Descriptor:
 bLength 9
 bDescriptorType 36
 bDescriptorSubtype 3 (MIDI_OUT_JACK)
 bJackType 2 External
 bJackID 4
 bNrInputPins 1
 baSourceID( 0) 1
 BaSourcePin( 0) 1
 iJack 0
 Endpoint Descriptor:
 bLength 9
 bDescriptorType 5
 bEndpointAddress 0x81 EP 1 IN
 bmAttributes 2
 Transfer Type Bulk
 Synch Type None
 Usage Type Data
 wMaxPacketSize 0x0040 1x 64 bytes
 bInterval 0
 bRefresh 0
 bSynchAddress 0
 MIDIStreaming Endpoint Descriptor:
 bLength 5
 bDescriptorType 37
 bDescriptorSubtype 1 (GENERAL)
 bNumEmbMIDIJack 1
 baAssocJackID( 0) 3
 Endpoint Descriptor:
 bLength 9
 bDescriptorType 5
 bEndpointAddress 0x02 EP 2 OUT
 bmAttributes 2
 Transfer Type Bulk
 Synch Type None
 Usage Type Data
 wMaxPacketSize 0x0040 1x 64 bytes
 bInterval 0
 bRefresh 0
 bSynchAddress 0
 MIDIStreaming Endpoint Descriptor:
 bLength 5
 bDescriptorType 37
 bDescriptorSubtype 1 (GENERAL)
 bNumEmbMIDIJack 1
 baAssocJackID( 0) 1
 Device Status: 0x0000
 (Bus Powered)

- Nun einmal die Ausgabe von *dmesg* beim Einstecken des Keyboards:

usb 2-6: new full speed USB device using ohci_hcd and address 14
 ohci_hcd 0000:00:0a.0: GetStatus roothub.portstatus [5] = 0x00100103 PRSC PPS PES CCS
 usb 2-6: skipped 1 descriptor after interface
 usb 2-6: skipped 5 descriptors after interface
 usb 2-6: skipped 1 descriptor after endpoint
 usb 2-6: skipped 1 descriptor after endpoint
 usb 2-6: default language 0x0409
 usb 2-6: new device strings: Mfr=1, Product=2, SerialNumber=0
 usb 2-6: Product: USB Keystation 49e
 usb 2-6: Manufacturer: Evolution Electronics Ltd.
 usb 2-6: uevent
 usb 2-6: usb_probe_device
 usb 2-6: configuration #1 chosen from 1 choice
 usb 2-6: adding 2-6:1.0 (config #1, interface 0)
 usb 2-6:1.0: uevent
 usb 2-6:1.0: uevent
 snd-usb-audio 2-6:1.0: usb_probe_interface
 snd-usb-audio 2-6:1.0: usb_probe_interface – got id
 usb 2-6: adding 2-6:1.1 (config #1, interface 1)
 usb 2-6:1.1: uevent
 usb 2-6:1.1: uevent
 drivers/usb/core/inode.c: creating file ‘014’
 hub 2-0:1.0: state 7 ports 10 chg 0000 evt 0040

- Die Konfiguration des Kernels

Ist eigentlich sehr sehr einfach. Man muss nur **Device Drivers/Sound/Advanced Linux Sound Architecture/USB Devices/USB Audio/MIDI driver **als Modul oder fest in den Kernel kompilieren.

Schon kann man mit dem Midi-Keyboard in wine und nativ arbeiten, z.B. mit rosegarden.

[](javascript:void(0) "Rosgarden und das 49e midi-keyboard") [](javascript:void(0) "Rosgarden und das 49e midi-keyboard") [![Rosgarden und das 49e midi-keyboard](http://www.christian-gmeiner.info/wordpress/wp-content/uploads/2008/01/rosgarden.thumbnail.png)](http://www.christian-gmeiner.info/wordpress/wp-content/uploads/2008/01/rosgarden.png "Direct link to file")
