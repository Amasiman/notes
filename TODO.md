# Priority

tested first secondary AMP image, which should apparently have better performance and need PTS adjustements, but its not working.  Also found some interesting AVDECC behaviour while testing and I



CMR follow up about RTC - 1074462

Review CMP-161 - should be fixed

CMR Further clarify testing documentation requirements
	- too vague, like only mentioning BPV linking
		- refer to WHY we need these values

CMR VLAN requirements review - arrange call with Mr Volkmann
	we shared VLAN concept and ask for review
	BCMR2-1326 
	VLAN Concept Denial of Service - Use VLAN to separate networks


CMR review installation response from Mr Volkmann
	- I see a lot of important topics highlighted where Standalone requirements are fucking with sys requirements


- busy with pre-integration tests for the CMR, I'm now preparing nanomsg test scripts and test reports for CMR AVB sign off
- happy to report that -4 amd -6 streaming is possible with preprocessed mp3 content (handbrake formats)
- had workshop with UMAN and EIZO around their -6 streaming issue.


DASH FORMAT LW
- the overall design and requirement for the dash format is actively being worked on in the investigation.


Billy:
1)	Lip sync for USB Video improvement?
	- we do not see issues with USB lip sync as reported by customer
		- pausing caused lip sync issue - created JIRA ticket
	- CMR needs lip sync review
2)	CM-R Pre-Integration command information
	- DTCs are not working in v19
	- I'm reviewing my scripts and preparing test reports
	- some concerns with IGN PIN wake up
3)	CM-R Integration
	- v19 is ready for CMC integration testing
		- Vasuki has started with AVDECC/stream testing
		- they were using the wrong versions
	- audio only streaming works for -6 streams, quality is not 100%
	- video with mpeg encoded audio works now, sporadic issues
		- no audio
		- stuttering video
4)	NXP Issue 
	- support contract
5)	SW architecture documentation --> linkage to responsibility / documentation to be done
	a.	Prio B
	- does not exist, must create tasks for suppliers 
		-  move this to internal discussion to confirm WHAT we need so we don't create a big work package here



NXP support contract discussion

RTC tickets for
	- change protected off to trigger at critical warning level (one lower)
	- CMC performance when flooding network with ping - for RBEI
		- audio breaks up in cockpit and cabin
	- negative impacts analysis of CMR permanent IGN line - for SOM
		- if customer connects this line, CIs CMR will not shut down when CMC cuts network

Clarify exactly what strange issues martin are having so Ameer can comment
	- also get settings from Dane to share with EIZO

Follow up with installation requirements for CMR

Document Iframe fixes from EIZO so LW can do the same

Confirm if testman can perform the requirements for CMC DTC/healthcare testing - for Kiran/Ron
 - https://inside-share-hosted-apps.bosch.com/DMS/GetDocumentService/Document.svc/GetDocumentURL?documentID=P12S137482-162455387-14255

Updated my CMR to v19 and started some sanity test - mostly confirming the fixes I know should be in
	- nanomsg fixes
	- streaming videos with mp3 encoded audio
	- DTC issues

Ask LW how to trigger DTC events, or just active DTC.
	- report strange output, get dtc errors when sending healthcare request
	
Investigate Fader issues on CMC

Get q5050 image from UMAN with all PHY as master

My TODO list from our call:
•	Clarify follow-up time (shutdown delay) requirement in BVP 292 for standalone CMR
•	Add references to software update power mode to standalone CMR spec
	o	Software Update mode is still required in standalone, and must be included in spec to facilitate verification testing
•	Review thermal requirement recommendation from LW to enable self-protection during critical levels, while in standalone mode
	o	Safer option when no adaptive power master is present
•	Confirm cascading requirements for standalone and CIs mode, if any.
	o	Align planned system layout with LPSD requirements.
•	Clarify sysman device_id requirements
	o	Is it required in standalone/CIs
	o	How is it configured

Add event repeat requirement to system messaging specification?

Open Point 1156962
	- review cascaded installation docs from Carsten

Clarify CRQ process with Eng hong, kenneth or Florian

confirm if event repeating is officially documented and implemented in sub-systems
	- add to system spec
	- first check wtf CMR and lesswire do with events otherwise this will create more work packages, which is not worth it if CMC
		ignores the events anyway...  Can be added later perhaps (if we need to speed up specific messages)

confirm CMA port6 usage

Review AVBOS tickets

Create AVDECC test list from Vasuki response

test LCM stuff for ASRAF
	SW Versions:
	CMC SW version: 22.2
	CIS SW Version : CIS_22.2_L_dev
	MIS_VERSION_AMPLIFIER_CRISPAUDIO:  : 6.2.0-3.1.3-rel
	MIS_VERSION_CAMERAPORT_EIZO: 6.1.3-7.1
	MIS_VERSION_GLASS_EIZO:  6.1.3-7.1 

clarify cascaded CMA requirements for UMAN (Jan)

email encryption

cs2000 patch for lesswire

AVBOS kernel update for widevine 
	- Open Point 1160236
	
clarify this standalone CMR installation requirements.
	- topic 40 in CMR weekly call
	- add nanomsg device ID
	- discuss volkmann email with doip people
	- dash format

Task 904472
	- confirm boot times of sub-systems
	- document start up behaviour

check voltage LCM management on subsystems.

distortion testing on CMA
	-SXM

lesswire JIRA tickets for mp3 encoding
	- test patch from Mr volkmann

compile new update for lesswire cis system

add dtc support to testman

Confirm with lesswire if their cascading document is accurate
	- why they need static IP on CMR
	- how static IPs and subnets are kept unique in cascaded standalone mode.

create tickets for EIZO
	- document unique gstreamer and stack changes

Cascaded CMR requirements

Push EIZO synth feedback to LW

Clarify DTC implementation on CMR

Open points for LW
- confirm new 1.2 thermal spec and share with LW
- push UMAN to confirm why CPU histogram started failing in 6.1.3
- confirm DoIP requirement for pulling individual sensor histogram
- get UMAN to confirm that getDTC and eventDTC is in same "replacable" plugin structure
    - also improve documentation

OPEN CMR topic
- get audio and video files that lesswire used
- get list of everything we can sign off on avdecc
	- onsolicited responses
	- controls
- compile avdecc list into checklist for pre-integration and release testing
- put CMC binaries on CMC to do v17 avdecc integration testing
- re-run nanomsg testing on CMR v18

create RTC tickets for pre-integration/integration testing and link testing spreadsheets


Compile requirements for secondary amplifier to A) give it to UMAN to implement and B) use it as signoff for pre-integration
	- part of current planning to define LCM test plan for sub systems
	- internal discussions required

Contact UMAN about AVBOS 79
Log strange new issues on CMC with manual button swivel

CMR and CMA pre-integration testing
	new CMA release ready to test
	new CMR release has broken AVB streaming and no DoIP update so no integration possible

Update CMC with test binaries that allows CMR streaming via HMI, 

Prep for CMR pre-integration testing
MAC ENDING documentation
Histogram/Thermal follow-up
 

# All

serious care activities

cascading pre-integration testing

Create RTC tickets and document testing according to the test spec from Florian
	- share test plan with Lesswire to request test reports
	- pre-integration tests (only sub systems)
	- integration tests (CIS behavior)

JIRA ticket workflow explanation diagrams
	- DJ will join the next meeting to clarify

histogram service in DOIP does not differentiate between sensors
    - confirm what are these values we can already pull with DOIP?

add AVB stream limits in cascading doc

Lesswire test setup
	- first identify what they have
	- then work out how to update
	- get them what else they need
	- create layout document to show them how to connect all devices without CMC

CMA clock synth:
	I want to see docs where all parties agree there is no risk.  if something happens in field we must have a clear course of action / responsible person

Assign someone to sync CMR release notes and test plans

Send sebastian Thermal questions to all component suppliers
	- do this via JIRA tickets

need diagrams for system release flow
	- show how raw (SWU key signed) images go from supplier to RBEI where it is doip encrypted (signed) then go to tester

request system architecture diagrams from UMAN
	- create deliverable matrix

Create MAC ending document
	- needs clear steps going forward
		- implement mac ending on sub-systems but do not set yet
	- explain what mac endings are and why we do not have to set them (yet)

MAC ENDING
	- where do we put these requirements so these mac ending questions don't pop up again
	- wait for Dane to confirm
	- clarify uncertainty
		- do you need a unique mac ending in the entire network? the connect function doesnt have that as parameter
		- What is the purpose of entity ID then? does entity_id + mac ending not form some kind of composite key?
			- also stream ID is also passed?
		- I'm confused because of multiple listeners (CMG) being able to have the same mac ending
	- confirm with VASUKI and whomever that mac ending controls are added to AEM for all components
	- work out how CMC manages these mac endings
		- when and how often it is set
		- how re-using mac endings work
		- mac endings are unique for talkers

Create supporting docs for CMX timing requirements - merge everything per Michael's request (from kim to network work packages)

Final lesswire RTC follow up
	- get full power consumption measurement during surveillance mode from CMR
		- focus on NAD consumption
		- include connection to server times
	- confirm RTC configuration options
		- DOIP?

Test B sample CMR on tower
	- full system update
	- check CMC avdecc implementation

UMAN must trigger protected OFF in thermal/voltage management functions (when protected off is actually implemented)

Update/refactor CIS spec doc 
- 2.5.4 Shutdown
	- subsystems cannot implement standby request because:
	- they cannot manually shut down
	- stopping apps and avdecc does not give a large enough shutdown time reduction to outweigh al the possible recovery issues this will introduce
	- CMC only sends user off, this is to ambiguous to trigger fs sync
		- changing this is additional implementation and issues on CMC; again not large enough gain to outweigh introduced issues
	- leave system as is - no wake up reason (i.e. LPSD) triggers standby processing (syncing, stoppings apps, etc.)

Schedule discussion with EIZO/Lesswire for AVDECC topics
	- pause seek resume

CMR ticket for testing nanomsg
	- overall ticket for nanomsg implementation
	- test v17 and add feedback
	- disable sysman then update to v17

CMR quality testing
	- how to meet september goal

Confirm https://rb-alm-20-p.de.bosch.com/ccm/web/projects/inf4cv#action=com.ibm.team.workitem.viewWorkItem&id=866461
	- ask carsten how they configure standalone/cis
	- ask lesswire why they need a device configured between 12/24
	- confirm all parties agree on how they configure standalone/cis (and 12/24 if it proves necessary)

Test watchdog CMA image
	- ask UMAN how to trigger freezes

Take CMR from tower for my desk (sysman testing)
-MAC ENDING double check
	- can they use static macs - what is EIZO doing
-CMR sysman testing


FINISH ONBOARDING PLAN

How can I document what I do so the knowledge is shared?
	- dont make the same mistake ievgen did

CMR
	-Lesswire AEM topic
		- who must update actual yaml?
	Review standalone SRS doc
		- check if LCM behavior is understood

MTT
	- talk with Ameer (UMAN) about their query into this with NXP

forward danes mails to our nxp contact - ask ievgen/jens who that is

send Yasmeet a message, make a friend in hildesheim

Create JIRA tickets for the process improvement - (the other half of MISMA 91 for CRISP I think?)

DTC
	- update sysman document to better clarify requirements
	- discuss and confirm healthcare processing
		- only process events
		- use healthcare response when needed (failover in case events stop coming)

Clarify open LCM topics on CMR - schedule call with LW, meow ling and woon nee
	- add tobias to cc chain
	- what are triggers for standalone and cis mode?
		- can one CMR do both in one config?
	- woon nee is responsible for technical aspects of CMR
	- fully define thermal self protection mechanism for CMR
	- fully define voltage self protection mechanism for CMR
	Trigger internal discussion with Michael/Jens about RTC
		- must also confirm why they use the same config for both systems 
		- 14V critical voltage level both 12v (standalone) and 24v?

sign off new AEM changes

Onboarding
1 - Speak to Oliver about 1st mandatory topic
2 - Speak to Michael

New guy who can do some intros with me
	Jasmeet Singh



# Research
GNSS

SAFE agile dev

HDCP encryption

avb encryption is part of 1722, but NXP AVB stack does not support this (yet)

CIS has T1 not TX phy - physical layer difference

research zener diode w.r.t. voltage protection
	- low impedance
		- why is this required when special diode used?