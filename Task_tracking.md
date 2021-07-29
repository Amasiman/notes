# 08/03/2021
> analyze EIZO crashes leading to broken VIDEO streams which CMC does not recover
	- send everyone logs and create ticket for crashing CMP/CMG
> enterprise architect access/licensing
> confirm ERA intercom volume change effects

# 09/03/2021
> review mails about not booting CMA issue and provide comments to Meow Ling
> compile intercom stream analysis
    > pull RTP stream from wireshark cap
    > import raw audio into audacity
    > compile screenshots and test results
> Review Gemmy quality process for Meow

# 10/03/2021
> 

# 11/03/2021
> report possible race condition in CMG
	- CMG logs show avtp media clock reset might be freezing


# 15/03/2021
> UML diagrams for DOOR STATUS
> 255 byte limit discussion

# 17/13/2021

Dealing with UNIT 373 - quality issue with the CMA from SOP1 that was broken on delivery
- flashing process failed
- manual version checks with DOIP tool - was not checked - user error
- helping meow ling guide CrispAudio and UMAN to improve the production process

Investigation tickets linked to media application crashes on EIZO components 
    - Martin Hintermann found a possible fix (newer version of the software multiplexer provided by NXP)

Discussions with Sadhees and Michael to clarify DOOR STATUS wakeup at CMA
    - Sadhees is looking into establishing communication between IMX and v850 so IMX can control WAKE OUT line from IMX for HOUR LOGIC

Reviewing CMC healthcare requirement documentation and test reports to compile test cases.  
    - Giving training to someone from RBEI on monday to create testing scripts


# 14/04/2021
Ask RBEI team about how they intend to configure mac endings
	- asked by CMR
	- also required for CMP
analyze Ron feedback
take more FR/FF wireshark traces
> get gstreamer debug logs for UMAN for no audio during seek issue


# 27/04/2021
get wireshark logs for Carsten at 20 cmg bench
	- only static number of CMG will show HDMI (not full 20)
	- the CMG that work changes after every reboot
	- get all logs from CMC to CMG/CMP for investigation

DTC discussion
	- clarify findings with Carsten
	- wtf does active mean
	- give Kiran feedback
	- confirm how DTC works in AVBOS with UMAN
		- active DTC always sent
		- can it be cleared without fixing anything?
		- any difference between healthcare and request message? besides power state
			- yes, one returns per id/type, the other returns all? must confirm.

	result
	- "cleared" is only possible via doip. not exposed to sysman
	- "set" is used to set 1st bit to on or off
	- '3rd' byte "dtc confirmed" is historic type, will stay active even after 1st byte clears
	- any issue that has ever been active only once will always be sent

Create RTC tickets to remove MTT

follow up with UMAN on primary amplifier risks with CS2000 failure
	- add jira ticket to track topic