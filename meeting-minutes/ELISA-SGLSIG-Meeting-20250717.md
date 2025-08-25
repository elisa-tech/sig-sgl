![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 17 July, 2025

# Agenda

- Roll Call
- Brief Notices
- Announcements
- Technical Topics
- Closing

---

# Roll Call

## Attended this meeting

- Ramon Roche (Dronecode Foundation)
- Yasushi SHOJI (Space Cubics)
- Paul Greenwood (Vorago Technologies)
- Tim Bird (Sony)
- Douglas Schilling Landgraf (Red Hat)
- Michael Monaghan (NASA Goddard Space Flight Center)
- Alexey Simonov (Technology Innovation Institute, UAE)
- Ivan Perez (KBR @ NASA Ames Research Center)
- Michael Epley (Red Hat)
- Matt Weber (Boeing)
- Carole Garrison (NASA Langley Center)
- Paul Mani(Collins Aerospace)
- Rob Woolley (Wind River)
## Attended recently in the past

- Christopher Heistand
- Dongshik Won (TelePIX, KAIST)
- Douglas Landgraf (Red Hat)
- Gabriele Paoloni (Red Hat)
- Kate Stewart (LF)
- Lukas Mazl (Technical University of Liberec)
- Manuel Betran (Boeing)
- Paul Greenwood (Vorago Technolgies)
- Michael Krasnyk (The Exploration Company)
- Michael Mahoney (Wind River)
- Panos Kalorog (NRB)
- Tony James (Red Hat)
- Michael Epley (Red Hat)
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

- [Mailing List Sign-up](https://lists.elisa.tech/g/space-grade-linux)

## SGL Workshop

https://directory.elisa.tech/workshops/index.html

## Upcoming Events

#### Upcoming Deadlines
- Space Mission Challenges for Information Technology / Space Computing Conference (July 28th). [link](https://2025.smcit-scc.space/)
- Korea Meetup - ELISA Project + Dronecode [link](https://elisa.tech/event/elisa-project-dronecode-foundation-meetup/)
- Open Source Summit EU 2025 [link](https://events.linuxfoundation.org/open-source-summit-europe/)
  - [SGL Talk](https://osseu2025.sched.com/event/25VnF/space-grade-linux-building-a-safer-open-source-future-for-space-systems-ramon-roche-linux-foundation)
- AMD Space Day (August 19, 2025) Registration (San Jose, CA.) -> [link](https://www.feedback.amd.com/se/5A1E27D22E92B566)
  - AMD Space lounge access required [link](https://account.amd.com/en/forms/registration/space.html)
  - Free Registration - Centered around AMD Versal
- SmallSat Salt Lake City, Utah (August 10-13) -> [link](https://smallsat.org/)
    - Flash Talk by Andrew Wilson (Monday)
    - Is anyone hosting a side chat room for Linux in Space? (was done in past)

#### Recently Past Deadlines
- Flight Software Workshop, Submission Deadline 24th of February, Event: March 24th - 27th. [link](https://flightsoftware.org/)
- ELC NA 2025 (and safety critical conference) (June 23-25, Denver)
- ELC EU 2025 (and safety critical conference) (Aug 25-27, Amsterdam)

---

# Technical Topics

* SHREC Linux for Space
* minimal / core images (zero-conf PR)
* Roadmap follow-up
  * SBOM's
  * User Space Layers
  * Docs
* Chat platform follow-up

## SHREC Linux for Space

The team behind SHREC is working on a hardened Linux for high performance computing, they are doing a lot of work for fault tolerant.

Here is a presentation describing projects that BYU is working on this year for SHREC: https://www.nsf-shrec.org/sites/default/files/2025/B1-25.pdf   It includes patches to the Linux kernel for fault detection as well as radiation testing, Linux on an AMD VERSAL (FPGA), characterization of faults, etc.

* It would be great if we could have them join our calls
* We should figure out what sort of changes / patches they have for the kernel

https://iucrc.nsf.gov/centers/space-high-performance-and-resilient-computing/

## minimal / core images

**Questions**
Do we want to start defining image recipes for SGL?
* core
* minimal
* container: [discussion here](https://github.com/elisa-tech/meta-sgl/issues/9)
* full/world: everything

zero-conf, is that something that we see as a runtime feature or development?
Discussion follow-up in the PR, basically we want to support this as a feature in the image

Global CDN caching from yocto project
- https://sstate.yoctoproject.org/
- (M Weber) Looking for any specific on use beyond [Yocto sstate docs](https://wiki.yoctoproject.org/wiki/Enable_sstate_cache)

## ELISA Discord Server

[Join us!](https://chat.elisa.tech)

## Meta-SGL: Proposed Roadmap

1. Skeleton Layer
2. CI/CD pipeline
3. Documentation
4. SBOMs
5. Footprint Tracking/Analysis

### Footprint Tracking / Analysis
We likely want to optimize and we need to track the footprint. We want observe how the configuration affects the footprint of the device.

Target Footprint: ?
Document why we are making the decision for this footprint.

### SBOMs
We need observability into what makes to each build, licenses, and all.

- SBOM Yocto Docs: https://docs.yoctoproject.org/dev-manual/sbom.html

### Documentation
In this meeting, we started working on a github issue to document all of the needs for docs, the [issue can be found here](https://github.com/elisa-tech/meta-sgl/issues/6).

- How to build locally
    - [Link to current docs](https://github.com/elisa-tech/meta-sgl/tree/main/kas)
    - BeagleV-Fire
    - QEMU RISC-V 64
    - add the list of other possible platforms as suggestions for contributions
- How to flash your hardware
- How to work with SGL

### User Space Layers
What's already out there in the wild
* [meta-ros](https://github.com/ros/meta-ros)
* meta-spaceros
  * **TODO**: Cyril / Alexey
* [meta-cfecfs](https://github.com/jphickey/yocto-meta-cfecfs)
* meta-fprime
* meta-px4


## TODO

* Follow-up on TODOS's from docs github issue
* Get meta-spaceros working (Cyril/Alexey)


