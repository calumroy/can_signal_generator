# can_signal_generator
Read a DBC file and a configuration file and generator signals to write to a CAN bus.

A python script to send CAN messages onto a can bus.

Read a DBC file and a configuration file and generator signals to write to a CAN bus.
This tool generates steps and sin wave signals for any field within a CAN message defined in a DBC file.
It runs a test where multiple signals are generated depending on the config file.

Simple usage example:
    `python3 can_signal_generator.py -p ./params_test1.yaml`

NOTES:
    Make sure the specified CAN DBC file exist at the location speicifed in the config file.
    Make sure the CAN interface speicfied in the config exist and has been setup.
    E.g to setup a virtual can buses in linux run this bash script as sudo:  
        ```  
        #!/bin/bash
        (( EUID == 0 )) || { echo "This script must be run with root privileges" ; exit 1; }
        echo "setting up virtual can interface"
        modprobe vcan

        ip link add dev can3 type vcan
        ip link set up can3
        ```
