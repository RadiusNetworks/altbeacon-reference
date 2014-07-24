#!/bin/bash

# AltBeacon - The Open and Interoperable Proximity Beacon Specification
#
# Transmit Reference Script
#
# System Requirements: Linux, BlueZ (Official Linux Bluetooth protocol stack), Bluetooth 4.0 Adapter

# Advertising Data Flags (not part of AltBeacon standard)
AD_Length_Flags="02"    # Length of Flags AD structure in bytes
AD_Type_Flags="01"    # Type of AD structure as Flags type
AD_Data_Flags="1a"    # Flags data LE General Discoverable

# AltBeacon Advertisement
AD_Length_Data="1b"    # Length of Data AD structure in bytes
AD_Type_Manufacturer_Specific_Data="ff"    # Type of AD structure as Manufacturer Specific Data
AD_Data_Company_Identifier="18 01"    # Company identifier (little endian).  Radius Networks ID used for example (0x0118).  Substitute your assigned manufacturer code, if available.
AD_Data_Proximity_Type="be ac"    # AltBeacon advertisement code.  Big endian representation of 0xBEAC
# Note: the 20-byte beacon identifier has been subdivided into three parts in this example for interoperability
AD_Data_ID1="00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00"    # Organizational identifier as 16-byte UUID value
AD_Data_ID2="00 01"    # Beacon Group as 2-byte value
AD_Data_ID3="00 01"    # Beacon Unit as 2-byte value
AD_Data_Reference_RSSI="c5"    # Signed 1-byte value representing the average received signal strength at 1m from the advertiser
AD_Data_Manufacturer_Reserved="01"    # Reserved for use by manufacturer to implement special features

# Set up advertising data flags
AD_Flags=`echo "$AD_Length_Flags $AD_Type_Flags $AD_Data_Flags"`

# Set up AltBeacon advertisement
AltBeacon_Advertisement=`echo "$AD_Length_Data $AD_Type_Manufacturer_Specific_Data $AD_Data_Company_Identifier $AD_Data_Proximity_Type"`
AltBeacon_Advertisement=`echo "$AltBeacon_Advertisement $AD_Data_ID1 $AD_Data_ID2 $AD_Data_ID3 $AD_Data_Reference_RSSI $AD_Data_Manufacturer_Reserved"`

echo "Transmitting AltBeacon profile with the following identifiers:"
echo "ID1: $AD_Data_ID1"
echo "ID2: $AD_Data_ID2"
echo "ID3: $AD_Data_ID3"
echo "MFG RESERVED: $AD_Data_Manufacturer_Reserved"
echo ""
echo "AltBeacon Advertisement: $AltBeacon_Advertisement"
echo ""
# Set Bluetooth device ID
BLUETOOTH_DEVICE="hci0"

# Command Bluetooth device up
sudo hciconfig $BLUETOOTH_DEVICE up

# Stop LE advertising
sudo hciconfig $BLUETOOTH_DEVICE noleadv

# HCI_LE_Set_Advertising_Data command
# Command parameters: Advertising_Data_Length (1f), Advertising_Data
sudo hcitool -i $BLUETOOTH_DEVICE cmd 0x08 0x0008 1f $AD_Flags $AltBeacon_Advertisement

# Start LE advertising (non-connectable)
sudo hciconfig $BLUETOOTH_DEVICE leadv 3

