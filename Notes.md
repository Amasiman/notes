Christoffel Basson (XC-CI1/ECP1)
Michael Pinneke (XC-CI1/ECP1) 

# AVB protocols
    IEEE 802.1AS-2011: Timing and Synchronization for Time-Sensitive Applications (gPTP);
    IEEE 802.1Qav-2009: Forwarding and Queuing for Time-Sensitive Streams (FQTSS);
    IEEE 802.1Qat-2010: Stream Reservation Protocol (SRP);
    IEEE 802.1BA-2011:[4] Audio Video Bridging (AVB) Systems;
    IEEE 1722-2011 Layer 2 Transport Protocol for Time Sensitive Applications (AV Transport Protocol, AVTP); and
    IEEE 1722.1-2013 Device Discovery, Enumeration, Connection Management and Control Protocol (AVDECC).

# uses for announcement out
 - Some coaches use this line to block users from muting during announcement.  Its called a relay because it's not very strong, pulled down to ground (research required)
 - older intercoms (such as ohdendorf) use this to prevent calling MIC1 while driver is talking





> avb encryption is part of 1722, but NXP AVB stack does not support this (yet)

Aufenthaltstitel verlängerung / Resident permit extension 





To check if using TEE (Trusted Execution Environment) of NXP possible, alternative solutions available with AVB OS / NXP
Integration of crypto lib (oemcrypto lib) into CMR SW, currently not available by NXP in Yocto build
Data transport on AVB network from CMR to CMG (AVB protocol, 100Base-T1 Ethernet)
Gstreamer implementation of CMR
Function of USB port restricted only to USB sticks
    Restriction on kernel modules to control features of USB
    Protection by AppArmor to limit access to USB/dev devices for wanted applications


I am Christoffel Basson (XC-CI1/ECP1), new system architect on CIS project, my direct manager is Michael Pinneke (XC-CI1/ECP1).  I need access for planning and review tasks


wifi password
bas9hi_msw
63481986



- negative thermal value problems

sysmantool.py
- line 539
- get_thermal_state(self)

- confirm default thermal and temp
    - check message definition for CMA



CMR versions

/var/lwuci/lwuci.py read 0 status.about.sw_version
/var/lwuci/lwuci.py read 0 status.about.AvbVersion


p3126


----------- media format notes

CMP
MPEG-TS container
    h.264 video
    mp3 audio

BYOD
MPEG-DASH
    h.254 video
    aac audio
        to smart devices
    mp3 audio
        to cma
            downmixed to 2 channel