![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 18 June, 2026

# Agenda

- Roll Call
- Brief Notices
- Announcements
  - Foundation Update
  - ELISA Workshop London Recap
  - Upcoming Events
- Mailing List Highlights
- Technical Topics
  - Guest Talk: KP Labs - Linux-Based Systems for Space & ECSS Compliance
  - Aerospace WG Cross-Over: SGL Hardware Targets & cFS Demo Build
  - Roadmap Discussion (continued)
  - PR Review
- Action Items Review
- Open Discussion / AOB
- Closing

---

# Roll Call

## Attended this meeting

-

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

- **Aug 03-07** IEEE SMC-IT/SCC in Pasadena, California, US -> [link](https://2026.smcit-scc.space/)
- **Sept 13-17** ICAS Congress in Sydney, Australia -> [link](https://icas2026.com/)
- **Sept 13-17** DASC Congress in Orlando, USA -> [link](https://dasconline.org/2026/)
  - Our AeroWG paper got accepted
- **Oct 2026** High Integrity Systems Conference [Link](https://www.his-conference.co.uk/)
- **NASA SPARK** submissions -> [link](https://spark.nasa.gov/)

---

# Announcements

## Foundation Update

SGL continues its move toward becoming a standalone Linux Foundation project. Founding member outreach is ongoing and the response remains encouraging.

If your organization is interested in being part of the inaugural group of founding members, now is the time to start that conversation. Founding members will be recognized at launch and benefit from the visibility that comes with it. This is open to organizations of any size, and there is no commitment required to explore the opportunity.

Even if you are just exploring, please reach out to Ramon directly at rroche@linuxfoundation.org. We are happy to have a confidential 1:1 to answer questions and share more about what founding membership involves.

## ELISA Workshop London Recap

The ELISA Workshop took place June 9-11 in London at Canonical's office near Tower Bridge. Boeing and AMD presented their Xen functional safety work covering aerospace, mixed criticality, and mixed function. Quick recap of takeaways relevant to SGL.

---

# Mailing List Highlights

-

---

# Technical Topics

## Guest Talk: KP Labs - Linux-Based Systems for Space & ECSS Compliance

Guest presentation from KP Labs. Maciej Nowak presenting, on behalf of Marcin Drobik (Head of Flight Software Engineering). KP Labs shares their experience developing Linux-based systems for space and their perspective on ECSS compliance for Linux-based systems.

This connects to the ECSS compliance guidance theme that surfaced as a top priority in the roadmap RFC feedback, where multiple organizations flagged the lack of clear guidance on how Linux-based systems should be approached within ECSS standards.

## Aerospace WG Cross-Over: SGL Hardware Targets & cFS Demo Build

Agenda item requested by Matt Weber (Boeing, ELISA Aerospace WG Chair) following the Aerospace WG use case demo call.

- SGL hardware targets and adding an AeroWG cFS demo build
- Thesis ideas around a minimal kernel + SGL hardware targets; discuss proposal and timeline for thesis work
- Reference: [wg-aerospace PR #225](https://github.com/elisa-tech/wg-aerospace/pull/225/changes)
- cFS build docs: https://github.com/elisa-tech/wg-aerospace/blob/main/demos/docs/Build-cFS.md

## Roadmap Discussion (continued)

Continuing the roadmap RFC. The thread remains open for additional input.

**Proposals for Roadmap:**
* Minimal System Layer, stripped down and usable out of the box
  * Documenting what's in the build, and why.
  * Run a hello world example, and trace down. Workload Tracing for the Linux Kernel (covers full kernel + userspace view)
    * See https://www.kernel.org/doc/html//v6.9/admin-guide/workload-tracing.html
    * [ELISA Subsystem trace research](https://github.com/elisa-tech/ELISA-White-Papers/blob/master/Processes/Discovering_Linux_kernel_subsystems_used_by_a_workload.md)
  * Aerospace is working a minimal practice activity with docs, [background here on end user goals](https://github.com/elisa-tech/wg-aerospace/issues/168#issuecomment-4183867886)
* Stress and do analysis on partitions on workloads, with [stress-ng](https://github.com/ColinIanKing/stress-ng)
* CI all the way to hardware, make sure we are verifying hardware runs builds
* cFS info: https://github.com/elisa-tech/wg-aerospace/blob/main/demos/docs/Build-cFS.md

## PR Review

### Open

| # | Title | Author | Status |
|---|-------|--------|--------|
| [#47](https://github.com/elisa-tech/meta-sgl/pull/47) | kas: add QEMU SpaceROS (jazzy-2025.10) for x86-64 build target | Aleksandar Nikolic | Open |
| [#43](https://github.com/elisa-tech/meta-sgl/pull/43) | kas: Add Space ROS Jazzy 2026.01 | Rob Woolley | Open |
| [#30](https://github.com/elisa-tech/meta-sgl/pull/30) | meta-sgl-core: add zeroconf networking as optional image feature | Ramon Roche | Open |

---

# Action Items Review (from Apr 16)

- Ramon: follow up with Matt Weber on adding a Space workload example to the roadmap
- Group: evaluate FTRFS and ZFS for SGL inclusion, including licensing implications and hardware fault-tolerance baseline assumptions
- Ramon: chase remaining doc relicensing approvals (CC-BY-SA-4.0 -> CC-BY-4.0) from Matthias Schmitz and Celeste
- Roadmap: draft Minimal System Layer proposal, documenting what's in the build and why
- Roadmap: scope partition stress/analysis work using stress-ng
- Roadmap: define plan for CI all the way to hardware (verify builds run on target)

---

# Open Discussion / AOB

-

---

# Closing

## Action Items

-

Tracked in [GitHub Issues](https://github.com/elisa-tech/sig-sgl/issues)

## Next Meeting

-
