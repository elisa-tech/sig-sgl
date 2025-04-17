![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 17 April 2025

---

# Agenda

- Roll Call
- Brief Notices
- Announcements
- Technical Topics
- Closing

---

# Roll Call

## Attended this meeting

- Ramon Roche (LF)
- Matt Weber (Boeing)
- Ivan Perez (KBR @ NASA Ames Research Center)
- Martin Halle (TUHH)
- Andrew E Wilson (L3Harris, BYU, FPGA Zealot)
- Tim Bird (Sony)
- Paul Greenwood (Vorago Technologies)
- Macarena Sagredo (Accenture)
- Rob Woolley (Wind River)
- Michael Monaghan (NASA Goddard)
- Pedro Roque (KTH, Sweden, incoming CalTech Postdoc)
- Yasushi SHOJI (Space Cubics, libcsp)
- Cyril Jean (Microchip Technology Inc.)
- Philip Balister (OpenEmbedded)
- Shefali Sharma
- Trevor Woerner
- Walt Miner
- Alexey Simonov

## Attended recently in the past

- Dongshik Won (TelePIX, KAIST)
- Manuel Betran (Boeing)
- Dillon Wells (CesiumAstro)
- Gabriele Paoloni (Red Hat)
- Christopher Heistand
- Panos Kalorog (NRB)
- Lukas Mazl (Technical University of Liberec)
- Michael Krasnyk (The Exploration Company)
- Douglas Landgraf (Red Hat)
- Kate Stewart (LF)
- Tony James (Red Hat)
- Michael Mahoney (Wind River)

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

#### Recently Past Deadlines
- SmallSat Abstract (Feb 4th) [link](https://smallsat.org/conference/submit-an-abstract/)
    - Sumbitted abstract on Fault Tolerant FPGA SDR (Andrew E Wilson)
- RISC-V in Space Abstract (Feb 7th -> 19th) [link](https://www.risc-v.space/wp/#content-1)
    - Submitted abstract on Fault Tolerant RISC-V Linux SoC (Andrew E Wilson)
    - [Link to Materials/Videos](https://www.risc-v.space/wp/front_page/conference-material/)
- Flight Software Workshop, Submission Deadline 24th of February, Event: March 24th - 27th. [link](https://flightsoftware.org/)
- ELC NA 2025 (and safety critical conference) (June 23-25, Denver)
- ELC EU 2025 (and safety critical conference) (Aug 25-27, Amsterdam)

#### Upcoming Deadlines
- Space Mission Challenges for Information Technology / Space Computing Conference (July 28th). [link](https://2025.smcit-scc.space/)

---

# Technical Topics

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

## Meta-SGL: Next Steps

- CI/CD pipeline
- user space application layers

## Hardware Platforms

**Options discussed on the last call**
- [BeagleV-Fire](https://www.beagleboard.org/boards/beaglev-fire): [Yocto BSP](https://github.com/polarfire-soc/meta-polarfire-soc-yocto-bsp), MIT license
    - Same FPGA/Processor Vendor as PIC64 with RISC-V Processors
- AMD-Xilinx FPGA board (MPSoC and/or Versal Edge)
  - MPSoC -> Ultrazed, ZUboard
    - [Ultrazed](https://www.avnet.com/wps/portal/us/products/avnet-boards/avnet-board-families/ultrazed/ultrazed-eg/ultrazed-eg-board-family)
    - [ZUboard](https://www.avnet.com/wps/portal/us/products/avnet-boards/avnet-board-families/zuboard-1cg/?srsltid=AfmBOoo2JoUZsKKZVOMvH0LJShops-f-UlY_SCLrdeeLEMxNxQrx07X7)
    - Mercury ECC SOM [Enclustra](https://www.enclustra.com/en/products/system-on-chip-modules/mercury-xu5/)
  - Versal Edge -> Avnet, Trenz, iWave SoM
    - [Avnet](https://www.avnet.com/wps/portal/us/products/avnet-boards/avnet-board-families/versal-ve2302/ve2302-som/?srsltid=AfmBOopEJol7hrED5jBBWSXRNPkcsidMXzNfIcyWiv4WgjL1UiXO1mEV)
    - [Trenz](https://shop.trenz-electronic.de/en/TE0955-01-EGBE32-A-AMD-Versal-AI-Edge-SoM-with-VE2302-device-4-x-5.6-cm)
    - [iWave](https://www.iwavesystems.com/product/versal-ai-edge-system-on-module/)
- Raspberry Pi compute module
    - [CM5](https://www.raspberrypi.com/products/compute-module-5/)
- Jetson Family
    - [Jetson Orin Nano Super](https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-orin/nano-super-developer-kit/)
- Other ISAs
  - x86
  - SPARC - LEON5
      - [GR740-mini](https://www.gaisler.com/products/gr740-mini)
  - PowerPC - RAD5500

**Some Requirements:**
- Radiation Performance
- ECC DDR
  - DDR4 ADDR/CMD parity
- Rad-Tolerant bootrom
  - MRAM
- FPGA SOCs
- Quad Core ARM-like
  - Real-time processors like R5s
- 2GB RAM (minimum)
- IO
  - UARTs, I2Cs
  - High-speed, standard networking (for ground development)


## TODO

- Ask for program and videos of RISC-V in Space event @Ramon
  - https://www.risc-v.space/wp/front_page/conference-material/
