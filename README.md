AltBeacon Reference
===================

#### [AltBeacon](http://altbeacon.org/) - The Open and Interoperable Proximity Beacon Specification

Transmit and Receive Reference Scripts

## System Requirements

Linux, [BlueZ](http://www.bluez.org/) (Official Linux Bluetooth protocol stack), Bluetooth 4.0 Adapter

## About

These Linux shell scripts provide a reference for the AltBeacon standard.  They use the tools provided by BlueZ, the Linux Bluetooth stack, to showcase an AltBeacon implementation on a Linux machine.

`altbeacon-transmit` - Transmit as a BLE proximity beacon with the AltBeacon standard

`altbeacon-receive`  - Detect proximity beacons using the AltBeacon standard

For more information on the AltBeacon specification, visit the public [AltBeacon spec](https://github.com/AltBeacon/spec) repo hosted on GitHub

**Note**: the 20-byte beacon identifier has been subdivided into three parts in this example for interoperability

## License

    Copyright 2014 Radius Networks

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
    
This software is available under the Apache License 2.0, see [LICENSE](LICENSE) for details.

