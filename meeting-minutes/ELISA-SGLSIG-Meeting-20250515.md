![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 15 May, 2025

# Agenda

- Roll Call
- Brief Notices
- Announcements
- Technical Topics
- Closing

---

# Roll Call

## Attended this meeting

- Ramon Roche (Dronecode Project, Inc.)
- Alexey Simonov (TII)
- Dillon Wells (CesiumAstro)
- Eric Smith
- Ivan Perez (KBR @ NASA Ames Research Center)
- Martin Halle (TUHH)
- Matt Weber (Boeing)
- Pedro Roque
- Rob Woolley (Wind River System, Inc.)
- Shefali Sharma
- Thomas Novotny (VZLU AEROSPACE)
- Trevor Woerner
- Virgil (Paul) Greenwood (Vorago Technologies)
- Yasushi SHOJI (Space Cubics)
- Philip Balister

## Attended recently in the past

- Christopher Heistand
- Dongshik Won (TelePIX, KAIST)
- Douglas Landgraf (Red Hat)
- Gabriele Paoloni (Red Hat)
- Kate Stewart (LF)
- Lukas Mazl (Technical University of Liberec)
- Manuel Betran (Boeing)
- Michael Krasnyk (The Exploration Company)
- Michael Mahoney (Wind River)
- Panos Kalorog (NRB)
- Tony James (Red Hat)

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

- **Verify your meeting invites only have a https://zoom-lfx.platform.linuxfoundation.org link.  If needed, you can signup at [link](https://zoom-lfx.platform.linuxfoundation.org/meetings/elisa-project?view=week) for the new invite.**

- [Mailing List Sign-up](https://lists.elisa.tech/g/space-grade-linux)

## SGL Workshop

https://directory.elisa.tech/workshops/index.html

## Upcoming Events

#### Upcoming Deadlines
- Space Mission Challenges for Information Technology / Space Computing Conference (July 28th). [link](https://2025.smcit-scc.space/)

#### Recently Past Deadlines
- SmallSat Abstract (Feb 4th) [link](https://smallsat.org/conference/submit-an-abstract/)
    - Sumbitted abstract on Fault Tolerant FPGA SDR (Andrew E Wilson)
- RISC-V in Space Abstract (Feb 7th -> 19th) [link](https://www.risc-v.space/wp/#content-1)
    - Submitted abstract on Fault Tolerant RISC-V Linux SoC (Andrew E Wilson)
    - [Link to Materials/Videos](https://www.risc-v.space/wp/front_page/conference-material/)
- Flight Software Workshop, Submission Deadline 24th of February, Event: March 24th - 27th. [link](https://flightsoftware.org/)
- ELC NA 2025 (and safety critical conference) (June 23-25, Denver)
- ELC EU 2025 (and safety critical conference) (Aug 25-27, Amsterdam)

---

# Technical Topics

## Survey on State-of-the-Art Operating Systems in Avionics, Targeting Open-Source Operating Systems

> "Historically, operating systems used for critical system applications in aerospace, such as commercial airplanes and satellites, and outer space, have been restricted to real-time commercial OSes.
> 
> Although commercial OS used in this domain deliver both commercial support, real-time performance, and a high level of assurance, they also
carry with them a number of limitations. Generally, a real-time commercial OS is prohibitively expensive for smaller organizations, educational institutions, and teams working on initial prototypes. Not having full source and artifact access limits teams' ability to fix and extend a system, innovate, and mature technology. Using a commercial OS also requires a mature organization that has purchasing/contracting agility for rapid development and the ability to incorporate the OS artifacts for the level of certification required.
> 
> This paper presents a collaborative survey, conducted under the umbrella of the ELISA foundation (Enabling Linux in Safety Critical Applications), on state-of-the-art use of Linux in aircraft, spacecraft, or vehicles operating in similar constrained environments. The paper outlines the current state of the eco-system used in industry, and the relationships between systems, service history, and regulatory standards. While the paper's focus is on Linux in particular, other operating
systems that are Unix-like or within a partition hosted by some kind of
hypervisor are investigated for comparison as well."

**Link to Whitepaper**
https://github.com/elisa-tech/wg-aerospace/blob/main/docs/20250509_ELISA_AeroWG_Whitepaper.pdf

## meta-sgl first pull request

From the group that submitted the PR:
> Distribution: Whatever is the LTS, right now Scarthgap
Hardware: QEMU + BeagleV-Fire
Name: SGL for now, we will bring this up with the larger group
> 
> We also agreed on multiple layers on the github repo following the AGL example, with meta-sgl-core being the one we will be focusing on initially
> 
> Lastly, we will be using kas for layer management.

https://github.com/elisa-tech/meta-sgl/pull/2

* repo vs kas?: kas ✅
* Hardware?: BeagleV-Fire / QEMU ✅
* Yocto release?: Scarthgap / two distro approach: tiny + systmd-based
  * tiny: minimal with bare minimum requirements (poky or poky-tiny)
  * systemd-based: more robust version (poky-altcfg)
* meta-sgl-core?:

**AGL systemd service management example**: https://docs.automotivelinux.org/en/salmon/#06_Component_Documentation/Application_Framework/01_Introduction/#service-management


## Meta-SGL: Proposed Roadmap

1. Skeleton Layer
2. CI/CD pipeline
3. Documentation
4. SBOMs
5. Footprint Tracking/Analysis

### SBOMs

We need observability into what makes to each build, licenses, and all.

### Documentation
- How to build locally
    - BeagleV-Fire
    - QEMU RISC-V 64
    - add the list of other possible platforms as suggestions for contributions
- How to flash your hardware
- How to work with SGL

## TODO

@Ramon: kickoff docs based on the [github actions PR](https://github.com/elisa-tech/meta-sgl/blob/380bd4a5758528a883bb0b75bac505ac4e15bf9e/.github/workflows/test_build_qemu_arm64.yml)

@Ramon: look into flattening commit history from PR and then merge.

@Ivan: Ping Michael regarding cFS layer.

@Rob: send a proposal for an image with all known utilities
