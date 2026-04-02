![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 2 April, 2026

# Agenda

- Roll Call
- Brief Notices
- Announcements
  - Foundation Update
  - Upcoming Events
- Technical Topics
  - CI Update
  - PR Review
  - Roadmap Discussion
  - Call for Maintainers
- Action Items Review
- Open Discussion / AOB
- Closing

---

# Roll Call

## Attended this meeting

-

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

- **Apr 4** IEEE SMC-IT/SCC paper deadline
- **June 8-12** RISC-V Summit Europe, Bologna, Italy
  - Special session for RISC-V in Space
- **Aug 03-07** IEEE SMC-IT/SCC in Pasadena, California, US -> [link](https://2026.smcit-scc.space/)
- **Sept 13-17** ICAS Congress in Sydney, Australia -> [link](https://icas2026.com/)
- **Sept 13-17** DASC Congress in Orlando, USA -> [link](https://dasconline.org/2026/)
- **NASA SPARK** submissions -> [link](https://spark.nasa.gov/)

---

# Announcements

## Foundation Update

We are in the process of establishing SGL as a standalone Linux Foundation project and are looking for organizations who would like to be part of that from the start.

If your organization is involved in space systems and you think there could be a fit, we would welcome a short 1:1 conversation to share more about what founding membership looks like and answer any questions. No commitment required at this stage.

If you are interested, please reach out to Ramon Roche at rroche@linuxfoundation.org or feel free to mention it during today's round table.

---

# Technical Topics

## CI Update

Significant CI improvements since the last meeting. Full documentation at https://sgl.elisa.tech/contribute.html

- **#42** (merged): Added RunsOn named runner configurations for consistent CI runner profiles
- **#41** (merged): Refactored all CI build logic into a single reusable workflow (`build-sgl.yml`). Each target workflow is now ~17 lines instead of ~73, making it trivial to add new build targets. Also added QEMU SpaceROS (ARM64, RISC-V) and x86-64 build targets. Supersedes and closes #32 and #33, based on work by @alenik22.

## PR Review

### Open

| # | Title | Author | Status |
|---|-------|--------|--------|
| [#30](https://github.com/elisa-tech/meta-sgl/pull/30) | meta-sgl-core: add zeroconf networking as optional image feature | Ramon Roche | Open |

### Merged since last meeting (Feb 19)

| # | Title | Author | Status |
|---|-------|--------|--------|
| [#42](https://github.com/elisa-tech/meta-sgl/pull/42) | ci: add RunsOn named runner configurations | Ramon Roche | Merged |
| [#41](https://github.com/elisa-tech/meta-sgl/pull/41) | ci: refactor CI into reusable workflow and add QEMU SpaceROS + x86-64 targets | Ramon Roche | Merged |
| [#36](https://github.com/elisa-tech/meta-sgl/pull/36) | docs: Add contribution guide for documentation | Matthias Schmitz | Merged |
| [#35](https://github.com/elisa-tech/meta-sgl/pull/35) | Reuse base kas BeagleV-Fire configuration for SpaceROS variant | Aleksandar Nikolic | Merged |

### Closed

| # | Title | Author | Notes |
|---|-------|--------|-------|
| [#33](https://github.com/elisa-tech/meta-sgl/pull/33) | Add kas QEMU + SpaceROS support for riscv and arm64 | Aleksandar Nikolic | Superseded by #41 |
| [#32](https://github.com/elisa-tech/meta-sgl/pull/32) | kas: Add kas configuration for qemux86-64 | Aleksandar Nikolic | Superseded by #41 |
| [#8](https://github.com/elisa-tech/meta-sgl/pull/8) | meta-sgl-core: add zero-conf networking to image | Dillon Wells | Superseded by #30 |

## Roadmap Discussion

RFC sent to the mailing list today to collect community input on priorities. See the mailing list thread: **[RFC] SGL Technical Roadmap - We need your input**

Looking for feedback on:
1. Features or capabilities that would make SGL useful for your work today
2. Hardware platform priorities
3. User space frameworks or libraries needed
4. Willingness to contribute or maintain specific areas

QEMU fault injection (Radshield collaboration): looking for folks interested in joining a dedicated working session or alternate group call to move this forward.

## Call for Maintainers

Continuing from last meeting. The PR queue is growing and we need community members willing to take on maintainer roles (PR review, documentation). Merge permissions granted in return.

---

# Action Items Review (from Feb 19)

- ~~Start roadmap discussion on mailing list~~ - done (sent today)
- ~~Review SGL arm64/riscv PRs~~ - done (absorbed into #41, merged)
- ~~Document contribution guidelines~~ - done (#36 merged)

---

# Open Discussion / AOB



---

# Closing

## Action Items

Located in [GitHub Issues](https://github.com/elisa-tech/sig-sgl/issues)

## Next Meeting

-
