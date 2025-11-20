![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 20 November, 2025

# Agenda

- Roll Call
- Brief Notices
- Announcements
    - OSS Japan
- Technical Topics
  - First hardware demo of SGL + SpaceROS
  - Intent to Form SGL Project
  - Project Goals and 2026 Plans
- Closing

---

# Roll Call

## Attended this meeting

- Ramon Roche (Dronecode Foundation)
- Yasushi SHOJI (Space Cubics)
- Matt Weber (The Boeing Company)
- Tim Bird (Sony)
- Pedro Roque (Caltech)
- Ivan Perez (KBR @ NASA Ames Research Center)
- Leonida Kosmidis
- Philip Balister (OpenEmbedded)
- Juan Solano
- Rob Woolley (Wind River)
- Paul Greenwood (Vorago Technologies)
- Michael Starch (JPL)
- Shefali Sharma
- Joe Speed (Ampere)
- Michael Monaghan
- Manuel Beltran (Boeing)
- Naga (Timesys/Lynx)
- Dhruv Sharma

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
- Paul Greenwood (Vorago Technologies)
- Matt Weber (The Boeing Company)

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
## Upcoming Events
- **Dec 8-10** Open Source Summit Japan 2025, Tokyo [link](https://events.linuxfoundation.org/open-source-summit-japan/)
  - SGL Keynote
- **Nov 18-19** ELISA Workshop [Link](https://elisa.tech/event/elisa-workshop-munich-2025/)
  - [Registration](https://czw--04.na1.hs-sales-engage.com/Ctc/RI+23284/cZw--04/JkM2-6qcW6N1vHY6lZ3mXW8p3-sx1rYFMdW10ST4Y3QSmknW3wHFgK19hk9nW8X5DFJ7qmp-rW4-Xwxc12wZrMW6Gm3hc9h-h8yW6HQ1yt3WZvSPW6PFDGB5H8wlRW5Th7Dk4tlLMMW85bf8V8hnbH-VMdFwK6cKWzbW5V1Ssj8bxY-9VXYLzr33jv2sW33Wjbz2CQhC_W7cVF864W7hVrW8RCJpT6FkSLgW4Tw3v3879vSWN43KBFCqxfM7W41Y-GJ5Z-qrKW8PV0Bb7QDKqmW5KlR0S7PXgbGW3KQ8Y55-YrbCf5cx88004)
- **Dec 11-13** : Linux Plumbers Conference 2025, in Tokyo -> [Link](https://lpc.events/)
  - Free Virtual LIVE stream during the event or $50 for interactive
  - [Topics](#oss-japan-lfg)
- **Jan 27-29** Core Flight System Symposium LMI Headquarters, in Tysons, VA -> [Link](https://etd.gsfc.nasa.gov/capabilities/core-flight-system/events/)
- **Feb 25** AvioSE 2026, Bern -> [link](https://aviose-workshop.github.io/)
  - **Call for papers until: Dec 01, 2025**
  - Co-located with Systems Engineering Workshop: [link](https://se2026.inf.unibe.ch/en/workshops/aviose/)
- **Mar 23-26** Flight Software Workshop, Laurel, MD [link](https://flightsoftware.org/)
  - **Submission Deadline December 4**
- NASA SPARK submissions -> [link](https://spark.nasa.gov/)

#### Recently Past Deadlines
- **Oct 27-29** ROSCon 2025 Singapore [link](https://roscon.ros.org/2025/)
  - Rob Woolley talking about space topics
  - Ramon doing a full day PX4 workshop
- **Nov 4-5** OSS Korea -> [Link](https://elisa.tech/event/open-source-summit-seoul-south-korea-2025/)
  - [DO-330 Qualification of Enhanced LLVM Structural Coverage Tool - Minji Park & Seojin Kim](https://www.youtube.com/watch?v=0JQLazypIHQ)
  - [Introduction and Consideration of Temporal Partitioning in Avionics With Open... - H. Kim & G. Kwon](https://www.youtube.com/watch?v=B9nwghDGDeI)

---

# Announcements

## OSS Japan LFG

**SGL Keynote** -> https://sched.co/2AEx7

**Linux Plumbers Content**

[Safe Systems Linux Microconference](https://elisa.tech/blog/2025/11/18/elisa-project-at-linux-plumbers-conference-tokyo-japan-2025/)

[Measuring Test Coverage of Kernel Object Code](https://lpc.events/event/19/contributions/2071/)

---

# Technical Topics

- First hardware demo of SGL + SpaceROS
- Intent to Form SGL Project
- Project Goals and 2026 Plans

## First Hardware demo of SGL + SpaceROS

Rob has a branch with changes and will push to meta-ros layer with instructions for meta-sgl soon - https://github.com/robwoolley/meta-ros/tree/spaceros-preview

**Next up is CFS work**
**Note from Mat:** cFS example build (minimal Linux system with a SDK is used to directly build cFS and a simple demo app) - https://github.com/elisa-tech/wg-aerospace/blob/main/demos/docs/Build-cFS.md

**Recap Blog Post** -> https://elisa.tech/blog/2025/11/13/robotics-and-space-grade-linux-at-roscon-2025-singapore/

**Link to video** -> https://vimeo.com/1136204579

<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/1136204579?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write; encrypted-media; web-share" referrerpolicy="strict-origin-when-cross-origin" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Transforming Robotics with Auto Bots from Outer Space"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

## Intent to Form SGL Project

### UEFI standard boot flow

- Single Generic ARM64 kernel img (boots on multiple hardware SoC)
- Package feed to support chip specific kernel modules
- Package feed to support adding to a minimal OS with mission/product dependencies
- Yocto could build base images and distro feed
- SOAFEE might have base images that could be used and extended with an additional meta-sgl specific package feed
- Doesn't address early boot or aspects of rigor outside of standardizing OS boot and making filesystem composition scalable (not board specific build from source)
- Not sure if RISCV has a similar approach? (All the parts beyond EDK2)
- Open source UEFI EDK2 supports many architectures and is used in space https://github.com/tianocore/edk2

**Ref:**
- [UEFI bootflow and ARM system ready]( https://uefi.org/sites/default/files/resources/Arm%20SystemReady%20and%20the%20UEFI%20Firmware%20Ecosystem.pdf)
- [U-Boot UEFI](https://docs.u-boot.org/en/latest/develop/uefi/uefi.html)
- **Joe Speed:** https://www.soafee.io is ~150 automotive companies developing open source functionally safe containers & hypervisors. A rather large retailer is working with it for warehouse robotics. And it is yocto based.
- HPSC discussion - https://www.nasa.gov/game-changing-development-projects/high-performance-spaceflight-computing-hpsc/
- HPSC Vendors - https://www.microchip.com/en-us/products/microprocessors/64-bit-mpus/pic64-hpsc/ecosystem
- [System Ready program](https://www.arm.com/architecture/system-architectures/systemready-compliance-program)
- arm dev kits 32 to 128 core used for arm software dev/test by automakers, embedded devs, and some space companies on [Newegg](https://www.newegg.com/p/pl?d=altrad8ud-1l2t+BUNDLE) and [ADLINK](https://www.ipi.wiki/products/com-hpc-ampere-altra). Newegg has 128 core for $2k black friday. System76 makes this arm desktop used by some space folks http://system76.com/arm made in US and TAA compliant. Linus Torvalds' arm desktop is similar so upstream support is good.

## Project Goals and 2026 Plans

* Agree on list of packages publish to 

## Formation Survey

https://linuxfoundation.research.net/r/sgl_interest_survey

## OSS Japan
- Meetup after Ramon's keynote on Wednesday
