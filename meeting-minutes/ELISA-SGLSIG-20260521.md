![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 21 May, 2026

# Agenda

- Roll Call
- Brief Notices
- Announcements
  - Foundation Update
  - Upcoming Events
- **Guest Presentation (30 min): CNES / KOSMOS Flight Software - Simon Corbin (CNES)**
  - KOSMOS framework overview
  - Why Linux? Use cases (SESAM, LORA, swarms) and challenges
  - Q&A and discussion: where SGL fits in CNES's Linux roadmap
- Technical Topics
  - Roadmap Discussion (continued)
  - PR Review
- Action Items Review
- Open Discussion / AOB
- Closing

---

# Roll Call

## Attended this meeting

- Name - Affiliation

## Attended recently in the past

- Alexey Simonov (TII)
- Brian Kempa
- Christopher Heistand
- Cyril Jean (Microchip)
- Dongshik Won (TelePIX, KAIST)
- Dhruv Sharma
- Douglas Landgraf (Red Hat)
- Gabriele Paoloni (Red Hat)
- Hans Weggeman (Wind River)
- Haoda Wang "Harry" (Columbia University)
- Hugo Cornelis (Mind OSS)
- Ivan Perez (KBR @ NASA Ames Research Center)
- Jan-Simon Moeller (AGL)
- Joe Speed (Ampere)
- Juan Solano
- Kate Stewart (LF)
- Leonidas Kosmidis (Barcelona Supercomputing Center)
- Lukas Mazl (Technical University of Liberec)
- Manuel Beltran (Boeing)
- Martin Halle (TUHH)
- Matt Weber (The Boeing Company)
- Michael Krasnyk (The Exploration Company)
- Michael Mahoney (Wind River)
- Michael Monaghan
- Michael Starch (JPL)
- Naga (Timesys/Lynx)
- Panos Kalorog (NRB)
- Paul Greenwood (Vorago Technologies)
- Pedro Roque (Caltech)
- Philip Balister (OpenEmbedded)
- Ramon Roche (Dronecode Foundation)
- Rob Woolley (Wind River)
- Ryo Takakura
- Shefali Sharma
- Tim Bird (Sony)
- Tony James (Red Hat)
- Tyler Kwolek
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

## Upcoming Events

- **May 27-28** Embedded Recipes, Nice France -> [link](https://embedded-recipes.org/2026/)
- **May 29** Yocto Project Summit, Nice, France -> [link](https://pretalx.com/yocto-embedded-recipes-2026/)
- **June 8-12** RISC-V Summit Europe, Bologna, Italy
  - Special session for RISC-V in Space
- **June 9-11** ELISA Workshop London at Canonical -> [link](https://elisa.tech/event/elisa-workshop-london-2026/)
- **June 23** ELISA Seminar: AvioNix - Infrastructure as Code for Linux in Avionics
- **Aug 03-07** IEEE SMC-IT/SCC in Pasadena, California, US -> [link](https://2026.smcit-scc.space/)
- **Sept 13-17** ICAS Congress in Sydney, Australia -> [link](https://icas2026.com/)
- **Sept 13-17** DASC Congress in Orlando, USA -> [link](https://dasconline.org/2026/)
  - Our AeroWG paper got accepted
- **Oct 2026** High Integrity Systems Conference [Link](https://www.his-conference.co.uk/)
- **NASA SPARK** submissions -> [link](https://spark.nasa.gov/)

---

# Announcements

## Foundation Update

SGL standalone LF project formation continues. Technical Charter finalized April 14; CONTRIBUTING.md and MAINTAINERS.md merged to meta-sgl (#50). Founding member outreach ongoing across NA, EU and Japan. If your organization wants to be part of the inaugural group, please reach out to Ramon at rroche@linuxfoundation.org.

## Other

- KP Labs (Marcin Drobik) also offered to present on ECSS compliance for Linux-based systems - propose scheduling for the June or July SIG meeting given today's CNES slot.

---

# Guest Presentation: CNES / KOSMOS Flight Software (30 min)

**Speaker:** Simon Corbin, Embedded Linux team, CNES (Flight Software Division, Toulouse)
**Deck:** SGL_SIG_May_CNES_KOSMOS.pdf

Topics:

1. **KOSMOS framework overview**
   - CNES generic flight software framework, ECSS-B qualified
   - Time and space partitioning on XNG hypervisor (Fentiss) + LithOS RTOS
   - Flight heritage: ANGELS, Eyesat, SWOT, JUICE (MAJIS), SVOM (ECLAIRs, MXT), MMX (IDEFIX, Rolbox), MERLIN, Kineis (x25), SWARM
2. **Why Linux? New use cases driving the need**
   - SESAM: Python-based AI for on-board telemetry anomaly detection
   - LORA: Lunar Operation Robotic Assistant (ROS-based)
   - Satellite swarms / constellations (inter-sat comms, OTA, cyber)
3. **How CNES plans to address it - 3 steps**
   - Step 1: Yocto-based Linux partition in KOSMOS using XNG BSP layer (relying on poky, and potentially SGL)
   - Step 2: Application Manager - "smartphone in orbit", dynamic app load
   - Step 3: Full Linux-based flight software (Merlin Kooshmanian PhD: multi-policy hierarchical scheduling for containerized space apps)
4. **Open challenges / where SGL can help**
   - Minimal Yocto distribution definition (what's "minimal", which configs, bloat avoidance)
   - Reliability tuning: systemd vs applicative services; when to use PREEMPT-RT
   - Filesystem choice under tight RAM (initramfs / ext4 / squashfs on NAND)
   - KAS for reproducibility
   - Custom layers: KOSMOS layer (PUS services 1/3/5/17/140, monitoring signals, app execution)
   - Isolation between distribution generation and application code development
   - Maintainability: project layout on GitHub/GitLab, delegating Yocto vs app work to different teams
   - Asks: "Are there NASA/ESA initiatives on Linux-for-space standards?" / European coordination angle

Discussion: where does SGL fit in CNES's Linux roadmap, and which of these challenges should the roadmap explicitly address?

---

# Technical Topics

## Roadmap Discussion (continued)

Carrying over from April 16. RFC thread still open on the mailing list. Use Simon's challenge list to stress-test the current priorities (Minimal System Layer, PREEMPT-RT characterization, KAS reproducibility, filesystem options).

Open follow-ups from last meeting:
- Boeing/AMD Xen functional safety + space workload example - status from Matthew Weber
- Minimal System Layer proposal draft
- stress-ng partition stress/analysis scope
- CI-to-hardware plan

## PR Review

### Open

| # | Title | Author | Status |
|---|-------|--------|--------|
| [#56](https://github.com/elisa-tech/meta-sgl/pull/56) | kas: remove kirkstone support | Aleksandar Nikolic | Open |
| [#52](https://github.com/elisa-tech/meta-sgl/pull/52) | Add zeroconf-networking to Space Grade Linux | Rob Woolley | Open |
| [#51](https://github.com/elisa-tech/meta-sgl/pull/51) | docs: relicense from CC-BY-SA-4.0 to CC-BY-4.0 | Ramon Roche | Open |
| [#47](https://github.com/elisa-tech/meta-sgl/pull/47) | kas: add QEMU SpaceROS (jazzy-2025.10) for x86-64 build target | Aleksandar Nikolic | Open |
| [#44](https://github.com/elisa-tech/meta-sgl/pull/44) | scripts: add sgl-telemetry-collect for EDAC and system data | - | Draft |
| [#43](https://github.com/elisa-tech/meta-sgl/pull/43) | kas: Add Space ROS Jazzy 2026.01 | Rob Woolley | Open |

### Merged since last meeting (Apr 16)

| # | Title | Author | Status |
|---|-------|--------|--------|
| [#50](https://github.com/elisa-tech/meta-sgl/pull/50) | docs: add CONTRIBUTING.md and MAINTAINERS.md | Ramon Roche | Merged |
| [#45](https://github.com/elisa-tech/meta-sgl/pull/45) | ci: upload build artifacts from CI runs | - | Merged |

---

# Action Items Review (from Apr 16)

- Matt Weber follow-up on Space workload example for roadmap - status?
- FTRFS / ZFS evaluation - any updates from the group?
- Doc relicensing chase (Matthias Schmitz, Celeste) - status (PR #51 open)
- Minimal System Layer proposal - draft started?
- stress-ng partition stress/analysis scope - owner?
- CI-to-hardware plan - owner?
- Open PR reviews on #47, #43, #30 (#30 superseded by #52)

---

# Open Discussion / AOB

- KP Labs presentation slot - propose June 18 or July
- European coordination angle from CNES - how do we want to engage ESA more formally?

---

# Closing

## Action Items

Located in [GitHub Issues](https://github.com/elisa-tech/sig-sgl/issues)

## Next Meeting

- June 18, 2026
