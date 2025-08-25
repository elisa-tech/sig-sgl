![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 21 August, 2025

# Agenda

- Roll Call
- Brief Notices
- Announcements
- Technical Topics
  - Github CI
  - Open PRs
  - Documentation update
  - Roadmap follow-up
- Closing

---

# Roll Call

## Attended this meeting

- Ramon Roche (Dronecode Foundation)
- Matt Weber(Boeing)
- Andrew Wilson (L3Harris)
- Dillon Wells (CesiumAstro)
- Yasushi SHOJI (Space Cubics)
- Alexey Simonov (Technoloy Innovation Institute, UAE)
- Rob Woolley (Wind River)
- Cyril Jean (Microchip)
- Tomas Novotny (VZLU AEROSPACE (formerly Czech Aerospace Research Centre))
- Philip Balister (OpenEmbedded, OpenSDR)
- Garrett Smith (BYU)
- Tim Bird (Sony)
- Ivan Perez (KBR @ NASA Ames Research Center)
- Macarena Sagredo (Accenture)

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
- **(October 31)** Korea Meetup - ELISA Project + Dronecode [link](https://elisa.tech/event/elisa-project-dronecode-foundation-meetup/)
- **(August 25-27)** Open Source Summit EU 2025 [link](https://events.linuxfoundation.org/open-source-summit-europe/)
  - [SGL Talk](https://osseu2025.sched.com/event/25VnF/space-grade-linux-building-a-safer-open-source-future-for-space-systems-ramon-roche-linux-foundation)
- **(Sept 15-17)** Xen Project Summit (@Xilinx, San Jose, CA.) -> [Link](https://xenproject.org/resources/xen-summit/)


#### Recently Past Deadlines
- Flight Software Workshop, Submission Deadline 24th of February, Event: March 24th - 27th. [link](https://flightsoftware.org/)
- ELC NA 2025 (and safety critical conference) (June 23-25, Denver)
- ELC EU 2025 (and safety critical conference, and Embedded Linux Conference) (Aug 25-27, Amsterdam)
- SmallSat Salt Lake City, Utah (Aug 10-13, SLC)
- AMD Space Day  (Aug 19, San Jose, CA.)

---

# Technical Topics

* Github CI
* Github PRs discussion
* Roadmap follow-up
* Documentation

## Github CI


## Garret Smith @ BYU Brigham young university
**Working on Radiation Testing Linux**

* Mainly working with FPGA's
* have been doing radiation testing, using Xilinx (AMD Versal)
* Have done bare metal testing, but also looking at Linux-based testing
* Most recent tests involved a Linux image on the Versal
* Are going through test data now
    * Seeing primarily hardware errors
        * Cores just fall over, which causes full system failure
* Mitigations or changes
    * Turning on cache ECCs helped
    * They did flush caches in the most recent tests
* QEMU fault injection?
  * Hasn't worked around emulating, has spent more time working with the hardware directly
  * Some hardware has fault injection support
* Results (with analysis so far)
  * Do see bitflips, but with ECC on and scrubbing, lots of errors get corrected
  * Don't see bitflips in DDR - hit main chip and not DDR
  * Currently see failure SEU - see processor hangs, which is difficult to diagnose
  * Have not done DDR EDAC stuff yet; some OCM EDAC
      * Linux reports errors, but doesn't correct; had to patch driver to actually issue correction in OCM
  * 
Andrew Wilson
  * Also tested Linux on TMR Soft RISC-V processors
  * They did use Versal PCIe with a PolarFire RootComplex, but not with rad tests related with Linux

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
* [meta-spaceros]
  * **TODO**: Cyril / Alexey
* [meta-cfs](https://github.com/jphickey/yocto-meta-cfecfs)
* meta-fprime
    * there is some work by Kelly Williams. it is in this repo, but it is not 'fprime on yocto' yet
        * https://github.com/BroncoSpace-Lab/fprime-scales-ref
        * 
* meta-px4

