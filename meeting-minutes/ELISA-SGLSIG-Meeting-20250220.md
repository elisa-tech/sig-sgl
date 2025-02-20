![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 20 February 2025

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
- Matt Weber (Boeing), briefly
- Ivan Perez (KBR @ NASA Ames Research Center)
- Martin Halle (TUHH)
- Andrew E Wilson (L3Harris, BYU, FPGA Zealot)
- Tim Bird (Sony)
- Paul Greenwood (Vorago Technologies)
- Martin Halle (TUHH)
- Christopher Heistand
- Macarena Sagredo (Accenture)
- Gabriele Paoloni (Red Hat)
- Rob Woolley (Wind River)
- Douglas Landgraf (Red Hat)
- Michael Krasnyk (The Exploration Company)
- Dongshik Won (TelePIX, KAIST)
- Panos Kalorog (NRB)
- Lukas Mazl (Technical University of Liberec)
- Manuel Betran (Boeing)
- Dillon Wells (CesiumAstro)
- Michael Monaghan (NASA Goddard)
- Douglas Landgraf (Red Hat)

## Attended recently in the past

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

#### Upcoming Deadlines
- ELC NA 2025 (and safety critical conference) (June 23-25, Denver)
[CFP link](https://events.linuxfoundation.org/open-source-summit-north-america/program/cfp) (CFP deadline Feb 17)
- ELC EU 2025 (and safety critical conference) (Aug 25-27, Amsterdam)
- Space Mission Challenges for Information Technology / Space Computing Conference (March 3rd). [link](https://2025.smcit-scc.space/)
- Flight Software Workshop, Submission Deadline 24th of February, Event: March 24th - 27th. [link](https://flightsoftware.org/)

---

# Technical Topics

- Presentation of Douglas Landgraf (Red Hat) on Space Grade Linux
  - Held on NASA workshop
  - Effort from all vendors to have ALL in ONE ready to go Space distro
  - Resources, sources, tools etc. on Github (like API, sources... in Python, C++)
  - Demonstrated a use-case based on example: Rocket Launch Simulator
  - General vendor neutral, vendor specific topics can be included
  - Examples available from NASA, Boeing, ...
  - Explanation of proposed solution / structure
    - Host, Quality Manager ...
  - Excessive examples of standards (livestream, flight telemetry...)
  - Explanation of how it works behind the scenes
  - Link: https://github.com/containers/space-grade-linux
  - Will be converted to Yocto
  - Looking for Testers, Quality Engineers, Documentation...
  - Live-demonstration
  - Link: https://docs.google.com/presentation/d/1ae7vnGsdiTpSaU9KDC1dJsDZHHj62h7jxQBywagFTFw/edit#slide=id.g32d2de1bbcc_0_0
- Discussion on presentation
  - Linux is used in Space already (Space/X and StarLink was mentioned), unclear to what safety level
    - References:
      - https://x.com/elonmusk/status/198579161382649857
      - https://aviationweek.com/dragons-radiation-tolerant-design
      - https://space.stackexchange.com/questions/9243/what-computer-and-software-is-used-by-the-falcon-9
      - https://www.reddit.com/r/spacex/comments/ncj4vz/we_are_the_spacex_software_team_ask_us_anything/
      - Recipes and slides: https://pretalx.com/yocto-project-summit-2024-12/talk/WDNMHW/
  - Question, why Yocto, containers
    - Containers can run with Yocto builds
    - [Reference: "Building a Containerized System with the Yocto Project"](https://www.youtube.com/watch?v=aYm6ncWt7JY)
  - Discussion on fprime vs. cfs

## Meta-SQL: Next Steps

- Starting with minimal kernel/profile that is already posted (Matt Weber...)?
- Is Yocto distro probably too complex for high DAL S/W?
- (...to be addressed further soon...)

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
