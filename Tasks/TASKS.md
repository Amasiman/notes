

Help trigger broken clock synth testing at crispaudio
	- discuss with Woon nee




Flash CMA with dev image for debug gstreamer logs  (and wireshark traces)
RTC issue follow up on CMR
	- only needed for thermal, if protected off mode consumption too high.
	- waiting for consumption numbers for protected off
	- not needed for IGN/LPSD
	- update spec docs to make purpose for power modes clearer
		- we're not just trying to lower consumption - just protect devices
		- voltage protection can be done with hardware so nothing more than protected off required
Follow up with CMR issue 21 - CMR waking up CMA
add ticket to cmr tracker for pausing
serial output on CMA




- 1 year ago stream id implemented for control stream
- cmg has black screen if this is not used because end of stream is assumed



CMR discussion
	- discuss mac endings
	- clarify open topics for me because everything is assigned to Vasuki
	
	mac endings
		- needed for SSR, set using libSSR
		- why ask if it should be replaced?
		- how is it configured? i.e. giving CMG/CMA mac address to CMR




what needs to be improved in CIS
	- suppliers are implementing systems in isolation, breaking internal and external systems
		- internal issues (not bosch responsibility, but wat can we do?)
			- hw supplier not talking properly with sw supplier
			- different sw module teams not talking with each other
		- external issues
			- integration partners (other systems that use your system) components stop working

	- better process management
		- clear indication from sub-systems that their implementers are aware of these process flows









> investigate tests for AVB quality checks if clock synthesizer fails
focus is on LCM and nanomsg


> Update and distribute door status UMLs
> review implemented power states in CMR and ask lesswire when default states required for LCM will be ready
	- user off
	- response to power set for ON
	- response to power get healthcare
> follow up with CrispAudio (sven) about doip automation
	- get Carsten involved to take over eventually

> Figure out how to use doip libraries and create scripts to 'automate' versions checks

> create test module to sign of CMC
 - compile tests from test cases
	- how we test (function)
	- what we test for (result)
	- how we view output/results
 - determine solution
	- emulate CMP and CMA
	- testing software on CMG

> Thermal clarification
 - component suppliers must move away from single sensor values.  CMC expects general device temp - up to component suppliers to keep track.
 - sensor id can still be added but this is just informative for history/troubleshooting.

> comment on docs for meow
> get wireshark traces for map/hdmi switching issue on Martin tower

> Follow up with EIZO - possible media clock thread lock on CMG
> GET JIRA ACCESS AND LOG:
	- glitching on CMG when switching between map and hdmi output
		- re-create and cap logs/tracese
> Create EA workflow for door status wake-up and discuss with RBEI
	- show level trigger flow where door status wakes up system and why CMA must take over
		- because CMA will shut down if door is closed and there is no WAKE IN
	- show new flow with edge trigger
	- NOTE - UMAN need to modify power man to always wait full timeout on MIC2/3 wakeup and not standby when edge triggers are removed

> thermal message clarification
	- should sub-systems follow CMA (send highest thermal level)
	- or should highest priority sensor be defined beforehand
	- what happened to the histogram ideas?
	- CMA must add processing for thermal request WITH sensor ID for historical reasons (according to spec)
		- does that mean it is understood that CMC is responsible for histogram?


# LATER
> Designate T3 or T4 for pure development testing
	- maybe both? one for evobus and one for generic
	- need to different integration images in circulation
		- dev
		- release


# OPTIONAL

> Respond to Michael Voltage/Thermal mail
 - review thermal document for approval
 - over voltage processing skipped?
 - voltage processing different between CMA/CMC and sub systems
 - thermal processing the same for all

 Clarify CMA port 6 roadmap
	- is LPSD wakeup now expected for CMR?
	- does CMR fall under normal sub-system LCM requirements

> Follow up with Jens/Florian about DRM requirements

> cascaded tower
	- discuss topology with Ralf so he can create installation container
	- test CMP
	- follow up with Mohamed about hardware state on T3
	- get installation container from Carsten for cascaded CMP on T3
	- test nanomsg


> talk to Carsten about DOIP logging for CMA production line version checking
	- found out that doip layers are all python, Crisp can create scripts to pull versions and automate

> Review LessWire LCM documents for Michael

> DOORS access
	- cloud workspace (remote desktop)

> enterprise architect
	> connect projects - which projects?


> identify CIS stakeholders
	> chat with Florian about who does what (malaysian team, indian team)

> talk with Tim about the video quality and how we're going to follow up on that

> catch up on PACCAR project network wake-up

> review Sebastian Kohler mail links

> start training sessions
> start planning integration tasks
	- stream reservation
	- CMR progress
		- avdecc
		- sysman
	- intercom