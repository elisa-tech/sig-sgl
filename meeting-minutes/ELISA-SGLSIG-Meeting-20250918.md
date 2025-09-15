![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 18 September, 2025

# Agenda

- Roll Call
- Brief Notices
- Announcements
- Technical Topics
  - OSS EU + ELCE 25 Review
  - Linux under Radiation Environments Research
  - Open PRs
  - Roadmap follow-up
- Closing

---

# Roll Call

## Attended this meeting

- Ramon Roche (Dronecode Foundation)
- Dillon Wells (CesiumAstro)
- Philip Balister (OpenEmbedded, OpenSDR)
- Tim Bird (Sony)
- Andrew Wilson (L3Harris, BYU, FPGA Zealot)
- Rob Woolley (Wind River)
- Saket Sinha
- Aditya Bhattacharya
- Alexey Simonov
- Shefali Sharma
- Yasushi Shoji (Space Cubics)

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

#### Upcoming Deadlines
- **(Sept 15-17)** Xen Project Summit (@Xilinx, San Jose, CA.) -> [Link](https://xenproject.org/resources/xen-summit/)

#### Recently Past Deadlines
- **(August 25-27)** Open Source Summit EU 2025 [link](https://events.linuxfoundation.org/open-source-summit-europe/)
  - [SGL Talk](https://osseu2025.sched.com/event/25VnF/space-grade-linux-building-a-safer-open-source-future-for-space-systems-ramon-roche-linux-foundation)
- Flight Software Workshop, Submission Deadline 24th of February, Event: March 24th - 27th. [link](https://flightsoftware.org/)
- ELC NA 2025 (and safety critical conference) (June 23-25, Denver)
- ELC EU 2025 (and safety critical conference, and Embedded Linux Conference) (Aug 25-27, Amsterdam)
- SmallSat Salt Lake City, Utah (Aug 10-13, SLC)
- AMD Space Day  (Aug 19, San Jose, CA.)

---

# Events coming up
- Rob Woolley talking about space topics at ROSCON
- Ramon doing a PX4 workshop at ROSCON
- Ramon doing a Keynote on SGL at OSSJ in December

# Technical Topics

- OSS EU + ELCE 25 Review
- Linux under Radiation Environments Research
- Open PRs
- Roadmap follow-up

## OSS EU + ELCE 25 Review

The SGL talk at ELCE had a packed room and was well received with coverage by LWN, and lots of folks who reached out after the talk.
  - [Slides](https://osseu2025.sched.com/event/25VnF/space-grade-linux-building-a-safer-open-source-future-for-space-systems-ramon-roche-linux-foundation)
  - [Youtube Video](https://www.youtube.com/watch?v=jfFPlaVtTDY)
  - [LWN Article](https://lwn.net/Articles/1036168/)


Audience was well-engaged. Tim has people to follow up with, regarding QEMU fault injection and Linux in small sats.


## Linux under Radiation Environments Research

Aditya Bhattacharya PhD Researcher at The Interdisciplinary Centre for Security, Reliability and Trust (SnT) at the University of Luxemburg will be sharing his work on faul toleratance of Linux under Radiation, sharing their research and some of his future plans on failure injection under QEMU.

Presentation: Linux boot failures under proton irradiation

Big policy is to reboot machines to return machines to service.  But under radiation, booting is not reliable.  This effort focused specifically on the boot process and how radiation affects it.

NXP IMX 8M module hardware - tested with a few different distros.  Had different footprints, but similar contents.

Beam targetted the SOC, RAM and Flash.  Obviously saw a lot of errors.  We monitored power during boot to detect patterns.  Peaks at certain times can be correlated to boot activities.

We categorized faults, and looked for root causes.  Errors are caused very early on in the boot process (at firmware, device tree, etc.)  There were also errors in the EXT4 filesystem, caused by error cascade from earlier failures.

Tracked some EXT4 errors down to the controller - end result being failure to mount the filesystem.

ECC was not initialized during the kernel core phase, so errors in memory in that phase bled through to later phases.  E.g. bad pointer doesn't show up until use later.

Since then, have been trying to simulate these errors using QEMU fault injection.

Tim: Beam is order of magnitude more radiation than in orbit.  Can you estimate MTBF in orbit from results?  Aditya: We didn't do enough iterations to get MTBF data.


Why did you use protons instead of (say) heavy ions.  Adiya: Because that's the facility we had access to.

Can you talk about your plans for fault injection?
Aditya: Idea is to create a system to allow testing mitigation policies.  Can fault injection be used to simulate boot failures?  Plan to use QEMU with a plugin.

Not sure if random faults in memory will simulate boot environment well.

Some plugins already exist. But nothing looked like it would provide simulation Aditya desires. Is writing his own to control where bit flips are introduced.

QEMU fault injection was discussed.  MIT student has a thesis covering radiation simulation, and including something called "Hailburst" as a fault injection system.  See https://dspace.mit.edu/bitstream/handle/1721.1/144731/Skeggs-cela-meng-eecs-2022-thesis.pdf?sequence=1 and https://github.com/celskeggs/qemu

Tim: if ECC is started early (like in firmware), should this help the kernel get through it's boot?  Aditya: I expect so.  Yasushi: it takes time to set up ECC bits, during which time you are susceptible.  But doing it early still helps (narrows the window of susceptibility).  If controller takes hits, then results might be wrong even if memory is not corrupted.  ???: It might be worth re-probing hardware on failures, in case faults are transient.

Michael: another researcher was looking at radiation testing - focused on per-die effects.

Does SGL have a github repo?  - yes  Ramon: We're working on setting up CI with QEMU and fault injection.  Github repo: https://github.com/elisa-tech/meta-sgl

Yocto is used for building a custom distro, but also can build the firmware.  If a mitigation

Was the cache disabled?  No.  If there is no ECC on the cache, it may be better to disable it and take the performance hit.  This was done for some computers on the ISS.

Yasushi: "Has anyone considered running Linux using XIP"
- Seems like general answer is "no", but has some interest. Has been done in the past, but no one knew of recent efforts to resurrect

Yasushi: "Anyone considered injecting SEU's into a softcore proc implemented in an FPGA?"
- Michael M: "Yes, quite a bit of research here"
    - Andy Wilson to provide papers: https://scholarsarchive.byu.edu/etd/10892/

Are the faults injected uniformly (randomly) through memory, or using some targetted strategy? Aditya: I wanted to create something like a "hit map" of places to target, that would improve the simulation fidelity.

Andrew Wilson:  Here are some papers on soft core fault injection: https://scholarsarchive.byu.edu/etd/10892/
And another reference:  https://github.com/openhwgroup/cva6 and this project: https://blog.yosyshq.com/p/tamara-towards-a-triple-modular-redundancy-pass-for-yosys/

Ramon: Anyone want to work on ECC support / radiation hardening in the SGL repository?  It may be a hardware-specific problem.  ECC turn-on tends to be done by the zero-stage bootloader (very early)

Scrubbing requires a low-level kernel driver or modified memory controller, and a known-good copy of the memory (not good for dynamic RAM in active use).

Discussion about getting in-orbit data for radiation faults.  Most companies don't share.  Can use ECC fault counts as a crude radiation measurement.  Would be even better to correlate faults to satellite position and space weather.  At least one group turned on extra resilience during transiting the SAA.

Paper on "Strategies for Selective and Adaptive Resilience in Reconfigurable Space Systems and Apps" - https://d-scholarship.pitt.edu/40370/1/sabogals_etdPitt2021.pdf

It's an interesting possibility to trade compute speed, or extra power, or starting up alternate instances, as a robustness measure in the face of anticipated radiation increases.

Some vendors have custom EDAC drivers: Example: https://xilinx-wiki.atlassian.net/wiki/spaces/A/pages/1165066456/Linux+Versal+EDAC+Driver

Not sure if DISTRO configs can map down to kernel configs, and what we would want to include in the SGL repo config for this.  There's CONFIG_EDAC, but is there anything more specific?

Is scrubbing a kernel thing or something outside the kernel?

