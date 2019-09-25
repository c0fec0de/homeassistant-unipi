# Home Assistant on UniPi

Integration of the [UniPi](https://www.unipi.technology/) Hardware into [Home Assistant](https://www.home-assistant.io/)

## Introduction

[UniPi](https://www.unipi.technology/) builds [Raspberry Pi](https://www.raspberrypi.org/) based DIN rail universal programmable logic controllers (PLC) with analog/digital inputs and outputs.
This Home Assistant integration bases on [EVOK - the UniPi API](https://github.com/UniPiTechnology/evok). 

[Home Assistant](https://www.home-assistant.io/) is generic smart home hub, linking
all kinds of smart home technologies. 
[Amazon Alexa](https://www.home-assistant.io/components/alexa/), [Google Assistant](https://www.home-assistant.io/components/google_assistant/), [Philips Hue](https://www.home-assistant.io/components/hue/), [UniPi](https://www.unipi.technology/)and many more can interact with each other.

#### Supported Home Assistant Features:

* **UniPi Hub** The bridge between Home Assistant and UniPi
* **Binary Sensor**: Any digital input can be evaluated as [Home Assistant Binary Sensor](https://www.home-assistant.io/components/binary_sensor/) signaling buttons, switches, motion or any other event.
* **Switch**: Any digital output can be handled as [Switch](https://www.home-assistant.io/components/switch/)
* **Light**: Any digital output can be handled as [Light](https://www.home-assistant.io/components/light/)
* **Cover**: Two digital outputs can control a [Cover](https://www.home-assistant.io/components/cover/) (up/down motors).

## Hardware

* [UniPi NEURON](https://www.unipi.technology/products/unipi-neuron-3?categoryId=2) (including the extension modules)
* [UniPi 1.1](https://www.unipi.technology/products/unipi-1-1-1-1-lite-19?categoryId=1) or 
* [Axon](https://www.unipi.technology/products/unipi-axon-135?categoryId=13)

## Installation

Please see [Installation](Installation.md)
