![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 16 October, 2025

# Agenda

- Roll Call
- Brief Notices
- Announcements
- Technical Topics
  - OTA + RAUC https://rauc.io
  - Intent to Form SGL Project
- Closing

---

# Roll Call

## Attended this meeting

- Ramon Roche (Dronecode Foundation)
- Matt Weber (Boeing)
- Andrew Wilson (L3Harris, FPGA Zealot)
- Yasushi SHOJI (Space Cubics)
- Tim Bird (Sony)
- Jan Lübbe (Pengutronix)
- Philip Balister (OpenEmbedded)
- Pedro Roque (Caltech)
- Douglas Schilling Landgraf (RedHat)
- Rob Woolley (Wind River)
- David Hecox (JPL)
- Alexey Simonov (TII)
- Cyril Jean (Microchip)



## Attended recently in the past

- Christopher Heistand
- Dongshik Won (TelePIX, KAIST)
- Douglas Landgraf (Red Hat)
- Gabriele Paoloni (Red Hat)
- Ivan Perez (KBR @ NASA Ames Research Center)
- Kate Stewart (LF)
- Lukas Mazl (Technical University of Liberec)
- Manuel Betran (Boeing)
- Michael Krasnyk (The Exploration Company)
- Michael Mahoney (Wind River)
- Panos Kalorog (NRB)
- Tony James (Red Hat)
- Tim Bird (Sony)
- Yasushi SHOJI (Space Cubics)

---

# Brief Notices

## Code of Conduct and Legal Notices

- ELISA Project meetings involve participation by industry competitors, and it is the intention of the Linux Foundation to conduct all of its activities in accordance with applicable antitrust and competition laws. It is therefore extremely important that attendees adhere to meeting agendas, and be aware of, and not participate in, any activities that are prohibited under applicable US state, federal, or foreign antitrust and competition laws.
  - [Linux Foundation Antitrust Policy](http://www.linuxfoundation.org/antitrust-policy)
- Email communication will be treated as documentation and be received and made available by the Project under the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0). Please refer to the ELISA Technical Charter section 7 subsection iv. for details.
- The discussions in these meetings are exploratory. The opinions expressed by participants are not necessarily the policy of the companies.
- No recordings of working group meetings are permitted. Special provisions may be arranged for recording in advance with explicit consent of the participants.
- The kernel and LF Code of Conduct applies to all communication with this project
  - [Linux Foundation Code of Conduct](https://www.linuxfoundation.org/code-of-conduct/)
  - Linux [Contributor Covenant Code of Conduct](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/Documentation/process/code-of-conduct.rst)
  - Linux Kernel Contributor Covenant [Code of Conduct Interpretation](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/Documentation/process/code-of-conduct-interpretation.rst)

---

# Announcements

- [ELISA Discord Server](https://chat.elisa.tech/)
- [SGL Mailing List Sign-up](https://lists.elisa.tech/g/space-grade-linux)

## SGL Workshop

https://directory.elisa.tech/workshops/index.html

## Upcoming Events
- **Dec 8-10** Open Source Summit Japan 2025, Tokyo [link](https://events.linuxfoundation.org/open-source-summit-japan/)
  - SGL Keynote
- **Mar 23-26** Flight Software Workshop, Laurel, MD [link](https://flightsoftware.org/)
  - **Submission Deadline December 4**
- **Oct 27-29** ROSCon 2025 Singapore [link](https://roscon.ros.org/2025/)
  - Rob Woolley talking about space topics
  - Ramon doing a full day PX4 workshop
- **Nov 4-5** OSS Korea -> [Link](https://elisa.tech/event/open-source-summit-seoul-south-korea-2025/)
  - Presentation: "Intro and Consideration of Temporal Partitioning in Avionics"
- **Nov 18-19** ELISA Workshop [Link](https://elisa.tech/event/elisa-workshop-munich-2025/)
  - [Registration](https://czw--04.na1.hs-sales-engage.com/Ctc/RI+23284/cZw--04/JkM2-6qcW6N1vHY6lZ3mXW8p3-sx1rYFMdW10ST4Y3QSmknW3wHFgK19hk9nW8X5DFJ7qmp-rW4-Xwxc12wZrMW6Gm3hc9h-h8yW6HQ1yt3WZvSPW6PFDGB5H8wlRW5Th7Dk4tlLMMW85bf8V8hnbH-VMdFwK6cKWzbW5V1Ssj8bxY-9VXYLzr33jv2sW33Wjbz2CQhC_W7cVF864W7hVrW8RCJpT6FkSLgW4Tw3v3879vSWN43KBFCqxfM7W41Y-GJ5Z-qrKW8PV0Bb7QDKqmW5KlR0S7PXgbGW3KQ8Y55-YrbCf5cx88004)
- **Dec 11-13** : Linux Plumbers Conference 2025, in Tokyo -> [Link](https://lpc.events/)
  - Free Virtual LIVE stream during the event or $50 for interactive
  - Safe Systems with Linux MC -> [List of Topics](https://lpc.events/event/19/contributions/?config=0edacdbc-94ad-4caf-ac7a-352f9bebdb35)
  - Presentation: "Measuring Test Coverage of Kernel Object Code"

#### Recently Past Deadlines
- **(August 25-27)** Open Source Summit EU 2025 [link](https://events.linuxfoundation.org/open-source-summit-europe/)
  - [SGL Talk](https://osseu2025.sched.com/event/25VnF/space-grade-linux-building-a-safer-open-source-future-for-space-systems-ramon-roche-linux-foundation)
- Flight Software Workshop, Submission Deadline 24th of February, Event: March 24th - 27th. [link](https://flightsoftware.org/)
- ELC NA 2025 (and safety critical conference) (June 23-25, Denver)
- ELC EU 2025 (and safety critical conference, and Embedded Linux Conference) (Aug 25-27, Amsterdam)
- SmallSat Salt Lake City, Utah (Aug 10-13, SLC)
- AMD Space Day  (Aug 19, San Jose, CA.)

---

# Technical Topics

- OTA + RAUC https://rauc.io
- Intent to Form SGL Project

## OTA + RAUC

**Are these charts presented available?** yes will be distributed

**What side initiates the updates?** Typically there is a management app embedded side that calls RAUC via D-Bus or the CLI

**Bootloader support?**
uboot, barebox, grub, uefi x86, custom

**Does it support Hot/Live patching**
RAUC is intended to write to an inactive partition and then to reboot (A/B)

**Some resources:**
* https://bootlin.com/blog/another-system-update-adventure-with-rauc-barebox-yocto-project/ 
* https://github.com/rauc/meta-rauc
* https://github.com/rauc/meta-rauc-community/tree/master/ (A/B Full Hardware Examples)

**Would RAUC work over unreliable link? Does it require TCP?**
It current requires TCP and can handle resuming updates after an abort.
There is a concept to support pluggable backends for streaming: https://github.com/rauc/rauc/discussions/1440
https://www.pengutronix.de/de/blog/2022-10-12-rauc-adaptive-updates.html

**Whats the benefits over SWUpdate?**
In general you can do the same things, but RAUC has a more integrated approach, RAUC knows which target slots are available. Adaptive Streaming is not supported in SWUpdate

**Previous RAUC Presentations from ELC** ->[link](https://elinux.org/index.php?search=RAUC&title=Special%3ASearch&go=Go)

## Intent to Form SGL Project

Is this like CGL (Carrier Grade Linux) or AGL (Automotive Grade Linux)?  CGL had a spec that vendors certified against.  AGL started with an architecture document, then transitioned to a reference distribution.

Doing our own distribution is nice for people to pick up, but will Linux Distribution Vendors (like RedHat and Canonical) take the technology out of the Yocto Project build system (recipes) and turn them into deb or rpm packages?
It's beneficial to get the Linux distribution vendors involved and promoting the technology.

Do we want to target specific hardware, like the HPSC, or some existing cubesatkits?

Who is the audience for the reference distro? Some existing private companies already have their own Linux and flight software stackes (SpaceX, Planet, Tivak, Terran)?  Are they likely to adopt the SGL stack?  What about government agencies: NASA, ESA, JAXA, ISRA?  Is SGL a bridge between agencies to coordinate on a reference implementation of the OS and flight stack?

What class (A-E) of mission is this targetting?  Some SIG members are working on class A mission issues.

What would the project do to support security and other aspects for highly remote deployments.

Need to consider cost to support a binary distribution.  Supporting a full Yocto Distribution, with docs and support, can be expensive.

Are the governement agencies using contracts that encourage vendor solutions?  Roll-your-own, even supported by a large company, are difficult to get accepted.

Current meta-sgl seems easier to adopt in cubesats where they don't have the safety and certification constraints.

Having a reference distribution makes it easier to push changes upstream to the OS or vendor distributions.

Having a testing solution (for example, for EDAC) would valuable.

Yasushi writes (in chat):
a) I may be biased, but could we include Zephyr RTOS? It’s (1) a Linux Foundation project and (2) many spacecraft use an RTOS anyway.
 
b) What do you think about non-flight software such as ground systems? Are we only interested in flight software (FSW)?
 
c) Yocto is great—how about also supporting an immutable-OS approach like Fedora Silverblue / Fedora CoreOS?

Considers scenarios around Fault tolerance, e.g. FT-Linux - https://popcornlinux.org/fault-tolerant-linux/