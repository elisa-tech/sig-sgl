![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 15 January, 2026

# Agenda

- Roll Call
- Brief Notices
- Announcements
- Technical Topics
  - Guest Presentation: Radshield - Software Radiation Protection (Haoda Wang, Columbia University)
  - OSS Japan Tokyo Recap
  - Foundation Launch Update
  - NASA Collaboration Update
  - Project Collaboration on GitHub
- Open Discussion / AOB
- Closing

---

# Roll Call

## Attended this meeting

- Ramon Roche (Dronecode Foundation)
- Matt Weber (The Boeing Company)
- Philip Balister (OpenEmbedded)
- Tim Bird (Sony)
- Cyril Jean (Microchip)
- Michael Mahoney (Wind River)
- Paul Greenwood (Vorago Technologies)
- Leonidas Kosmidis (Barcelona Supercomputing Center)
- Hugo Cornelis (Mind OSS)
- Ivan Perez (KBR @ NASA Ames Research Center)
- Martin Halle (TUHH)
- Tyler Kwolek
- Shefali Sharma
- Pedro Roque (Caltech)
- Ryo Takakura
- Hans Weggeman (Wind River)
- Rob Wooley (Wind River)
- Naga (Timesys/Lynx)
- Haoda Wang "Harry" (Columbia University)
- Yasushi SHOJI (Space Cubics)
- Alexey Simonov

## Attended recently in the past

- Alexey Simonov
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
- Tony James (Red Hat)
- Tim Bird (Sony)
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

- **Jan 27-29** Core Flight System Symposium LMI Headquarters, in Tysons, VA -> [Link](https://etd.gsfc.nasa.gov/capabilities/core-flight-system/events/)
- **Jan 31 - Feb 1st** FOSDEM -> [link](https://fosdem.org/2026/)
- **Feb 2** OpenEmbedded Workshop -> [link](https://pretalx.com/openembedded-workshop-2026-2025/schedule/)
- **Feb 25** AvioSE 2026, Bern -> [link](https://aviose-workshop.github.io/)
  - Co-located with Systems Engineering Workshop: [link](https://se2026.inf.unibe.ch/en/workshops/aviose/)
- **Mar 23-26** Flight Software Workshop, Laurel, MD [link](https://flightsoftware.org/)
  - Use case and safety levels (Matt W)
  - Post quantum crypto (Leonidas) - (RISC-V crypto focused)
- **Aug 03-07** IEEE SMC-IT/SCC IEEE International Conference on Space Mission Challenges for Information Technology (SMC-IT)
17th International Conference on Space Computing (SCC) https://2026.smcit-scc.space/ in Pasadena, California, US
    - **Deadline Paper: April 4, 2026**
- **Sept 13-17** ICAS (International Council of Aeronautical Sciences) Congress in Sydney,Australia -> [Link](https://icas2026.com/)
- **Sept 13-17** DASC (Digital Avionics Systems Conference) Congress in Orlando,USA -> [Link](https://dasconline.org/2026/)
  - **ACTION: ABSTRACTS DUE Jan 31st** - [Link](https://dasconline.org/2026/author-instructions-for-papers-and-panels)
- NASA SPARK submissions -> [link](https://spark.nasa.gov/)

---

# Announcements

## RISC-V in Space

(From Leonidas)

- There is a space-focused SIG call -- "Capture requirements relevant to space"
- If you are interested, join the mailing list: https://lists.riscv.org/g/sig-space/messages
- You can become a member as individuals (it's free) or through your organization if they are already a member (there is a membership fee, with exception for open source organizations, but you need to apply for them)
- Once you are a member, you can join the weekly calls (unlike ELISA, the calls are only open to members).
- The first call will be on January 8,2026
- There are also TG/WG/SIGs for Functional Safety, Automotive, Post Quantum Crypto etc which might be interesting for ELISA Aerospace Group.
- Feel free to join the corresponding mailing lists and join the calls. Call calendar: https://tech.riscv.org/calendar/
- SIG Space Proposal of Work: https://riscv.atlassian.net/wiki/spaces/SPC/pages/543719540/Space+SIG+PoW

---

# Technical Topics

## Guest Presentation: Radshield - Software Radiation Protection

**Presenter:** Haoda Wang (Columbia University)
Published at ASPLOS '26, collaboration with JPL/NASA and Aptos Orbital.
**ILD (Idle Latchup Detector)**
Software-based detection of Single-Event Latchups (SELs) using OS-visible performance counters during system quiescence. Achieved 0% false negative rate and 0.02% false positive rate in 960 hours of testing. Uses lightweight ML model to detect micro-SELs that increase current by as little as 0.07A, which traditional threshold-based approaches miss.
**EMR (Efficient Modular Redundancy)**
Protection against Single-Event Upsets (SEUs) through parallel execution with intelligent cache management. 1.4-35.5× more power-efficient than traditional Triple Modular Redundancy (3-MR). Deployed on Mars rover and LEO SmallSats.
**QEMU Fault Injector:** github.com/radshield/qemu-hce
**Q&A / Discussion**
Positive reception from attendees with active Q&A. Haoda has agreed to help integrate Radshield's QEMU-based fault injection tooling with SGL CI infrastructure, enabling automated radiation fault testing for the project.


---

## OSS Japan Tokyo Recap

https://www.youtube.com/watch?v=dmx6K8TdlbI

Ramon presented the SGL keynote at OSS Japan in December 2025. Met with several Japanese companies who were very receptive to the project. The timing and fit seemed right for their needs.

Beyond the technical project itself, there's a clear need for a home for the space developer community. SGL can serve as that gathering point.

---

## Foundation Launch Update
The Linux Foundation is actively working on the paperwork and outreach needed to establish SGL as a standalone project. Efforts are underway to form the initial pool of founding members to host and sustain the project.

**Current focus areas:**

* Expected financial and resource commitments
* Governance structure
* Defining immediate technical goals for SGL

If you work with a company involved in space systems or are responsible for a space-focused group within your organization, we encourage you to reach out about becoming a founding member. Founding members will have a seat at the table in shaping the direction of this project from day one.

**Contact:** Ramon Roche (rroche@contractor.linuxfoundation.org)


---

## NASA Collaboration Update

NASA engineers have been actively collaborating through the SGL mailing list. There are several open threads with ongoing technical discussions that would benefit from broader community input.
If you haven't already, take a look at the recent mailing list activity and contribute where you can. Community participation helps move these conversations forward.
Mailing list: https://lists.elisa.tech/g/space-grade-linux/

---

## Project Collaboration on GitHub

Active development on meta-sgl over the past few weeks with contributions from Philip Balister and Rob Woolley:

| PR | Title | Author | Summary |
|----|-------|--------|---------|
| [#20](https://github.com/elisa-tech/meta-sgl/pull/20) | Add Whinlatter to layer.conf | Philip Balister | Adds support for the latest Yocto Project release (Whinlatter) |
| [#21](https://github.com/elisa-tech/meta-sgl/pull/21) | Use upstream meta-sgl repository | Rob Woolley | Updates KAS configuration to pull from elisa-tech/meta-sgl instead of personal fork |
| [#22](https://github.com/elisa-tech/meta-sgl/pull/22) | Update Kirkstone to 4.0.32 | Rob Woolley | Updates Kirkstone LTS to latest release, fixes BeagleV-Fire BSP references for Kirkstone compatibility |
| [#23](https://github.com/elisa-tech/meta-sgl/pull/23) | Update Scarthgap to 5.0.14 | Rob Woolley | Updates Scarthgap to latest release, adds meta-clang layer support |

Thanks to Philip and Rob for keeping the layer current and build-ready.


---

# Open Discussion / AOB



---

# Closing

## Action Items

- 

## Next Meeting

-