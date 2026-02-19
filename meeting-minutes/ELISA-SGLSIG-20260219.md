![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 19 February, 2026

# Agenda

- Roll Call
- Brief Notices
- Announcements
  - Foundation Membership Outreach
- Technical Topics
  - Call for Maintainers
  - Repository Progress Update
  - PR Review
- Open Discussion / AOB
- Closing

---

# Roll Call

## Attended this meeting

- Ramon Roche (Dronecode Foundation)
- Matt Weber (The Boeing Company)
- Yasushi SHOJI (Space Cubics)
- Leonidas Kosmidis (Barcelona Supercomputing Center)
- Philip Balister (OpenEmbedded)
- Michael Mahoney (Wind River)

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

- **Feb 25** AvioSE 2026, Bern -> [link](https://aviose-workshop.github.io/)
  - Co-located with Systems Engineering Workshop: [link](https://se2026.inf.unibe.ch/en/workshops/aviose/)
- **Mar 23-26** Flight Software Workshop, Laurel, MD [link](https://flightsoftware.org/)
  - Use case and safety levels (Matt W)
  - Post quantum crypto (Leonidas) - (RISC-V crypto focused)
- **June 8-12** RISC-V Summit Europe Bologna, Italy
  - Call for abstracts: https://riscv-europe.org/summit/2026/call-for-contrib
  - Call for academic/university demos: https://riscv-europe.org/summit/2026/call-for-demos
  - Deadline **March 2nd**
  - Special session for RISC-V in Space to be announced, looking for speakers
- **Aug 03-07** IEEE SMC-IT/SCC IEEE International Conference on Space Mission Challenges for Information Technology (SMC-IT)
17th International Conference on Space Computing (SCC) https://2026.smcit-scc.space/ in Pasadena, California, US
    - **Deadline Paper: April 4, 2026**
- **Sept 13-17** ICAS (International Council of Aeronautical Sciences) Congress in Sydney, Australia -> [Link](https://icas2026.com/)
- **Sept 13-17** DASC (Digital Avionics Systems Conference) Congress in Orlando, USA -> [Link](https://dasconline.org/2026/)
- **NASA SPARK** submissions -> [link](https://spark.nasa.gov/)

---

# Announcements

## Foundation Membership Outreach

We are in the process of establishing SGL as a standalone Linux Foundation project and are looking for organizations who would like to be part of that from the start.

If your organization is involved in space systems and you think there could be a fit, we would welcome a short 1:1 conversation to share more about what founding membership looks like and answer any questions. No commitment required at this stage.

If you are interested, please reach out to Ramon Roche at rroche@contractor.linuxfoundation.org or feel free to mention it during today's round table.

---

# Technical Topics

## Call for Maintainers

The project is gaining momentum and the PR queue is growing. To keep things moving, we are looking for community members who would be willing to take on a maintainer role in the meta-sgl repository.

In practice this means helping review incoming pull requests and keeping documentation in good shape. In return, we would grant merge permissions on the repository.

This is a discussion point. If you are already following the repo closely and would be interested, we would love to hear from you today.

---

## Repository Progress Update

Good activity on the repository since the last meeting. The team has been expanding SpaceROS support across multiple architectures and cleaning up the kas configuration structure. A contribution guide is also in progress, which is a good sign for onboarding new contributors.

## Release & Roadmap

### Roadmap Discussion

We are looking for help defining the technical roadmap for meta-sgl, we would like to collect feature requests so we can create an initial roadmap for releases and more accurately predict a release schedule.

**TODO:** Reach out to the mailing list, capture by email, I will clean up and post an issue tracker in the repo, we will finally discuss and assign contributors on the next call.

## PR Review

### Open

| # | Title | Author | Status |
|---|-------|--------|--------|
| [#36](https://github.com/elisa-tech/meta-sgl/pull/36) | docs: Add contribution guide for documentation | Matthias Schmitz | Open |
| [#35](https://github.com/elisa-tech/meta-sgl/pull/35) | Reuse base kas BeagleV-Fire configuration for SpaceROS variant | Aleksandar Nikolic | Open |
| [#34](https://github.com/elisa-tech/meta-sgl/pull/34) | Add kas configuration to build SGL with SpaceROS for qemuriscv64 | Matthias Schmitz | Open |
| [#33](https://github.com/elisa-tech/meta-sgl/pull/33) | Add kas QEMU + SpaceROS support for riscv and arm64 | Aleksandar Nikolic | Open |
| [#32](https://github.com/elisa-tech/meta-sgl/pull/32) | kas: Add kas configuration for qemux86-64 | Aleksandar Nikolic | Open |
| [#30](https://github.com/elisa-tech/meta-sgl/pull/30) | meta-sgl-core: add zeroconf networking as optional image feature | Ramon Roche | Open |
| [#8](https://github.com/elisa-tech/meta-sgl/pull/8) | meta-sgl-core: add zero-conf networking to image (original) | Dillon Wells | Open |

**Summaries:**

- **#36** Starter contribution guide addressing issue #6. Helps lower the barrier for new contributors documenting their work.
- **#35** Refactors the BeagleV-Fire SpaceROS kas config to reuse the base machine configuration, reducing duplication.
- **#34** Adds a kas configuration to build SGL with SpaceROS on a RISC-V QEMU target. Pairs with #33.
- **#33** Adds QEMU kas manifests for SpaceROS on riscv and arm64. Partially addresses issue #27.
- **#32** Adds kas support for qemux86-64, broadening the set of targets you can build against locally.
- **#30** Extracts the zeroconf feature from #8 into a cleaner optional image feature, usable via `OPTIONAL_FEATURES`. Closes #8 once merged.
- **#8** Original zeroconf + SSH PR from Dillon Wells. Superseded in scope by #30 but still open.

### Merged since last meeting (Jan 15)

| # | Title | Author | Status |
|---|-------|--------|--------|
| [#31](https://github.com/elisa-tech/meta-sgl/pull/31) | Little documentation fixes | Matthias Schmitz | Merged |
| [#29](https://github.com/elisa-tech/meta-sgl/pull/29) | ci: build spaceros | Ramon Roche | Merged |
| [#26](https://github.com/elisa-tech/meta-sgl/pull/26) | Add Space ROS 2025.10 support | Rob Woolley | Merged |
| [#25](https://github.com/elisa-tech/meta-sgl/pull/25) | Update BeagleV-Fire support for Scarthgap | Rob Woolley | Merged |
| [#24](https://github.com/elisa-tech/meta-sgl/pull/24) | Update kas configurations | Rob Woolley | Merged |
| [#23](https://github.com/elisa-tech/meta-sgl/pull/23) | Update Scarthgap to 5.0.14 | Rob Woolley | Merged |
| [#22](https://github.com/elisa-tech/meta-sgl/pull/22) | Update Kirkstone to 4.0.32 | Rob Woolley | Merged |
| [#21](https://github.com/elisa-tech/meta-sgl/pull/21) | kas: Use the upstream meta-sgl git repository | Rob Woolley | Merged |

**Summaries:**

- **#31** Documentation and QEMU command line cleanup; fixes a drive conflict error message on startup.
- **#29** CI now builds SpaceROS on BeagleV-Fire. Credit to Rob Woolley.
- **#26** Adds SpaceROS Jazzy 2025.10 support with meta-ros, clang, and a new Scarthgap + SpaceROS kas config for BeagleV-Fire.
- **#25** Updates BeagleV-Fire BSP to use the new meta-mchp layers for Scarthgap, replacing the old meta-polarfire ones.
- **#24** Replaces the deprecated `excluded` keyword with `disabled` and fixes `LICENSE_FLAGS_ACCEPTED` override handling.
- **#23** Updates Scarthgap to 5.0.14 and adds meta-clang layer support.
- **#22** Updates Kirkstone to 4.0.32, fixes BeagleV-Fire BSP references for Kirkstone compatibility.
- **#21** Points kas at the upstream elisa-tech/meta-sgl repository instead of a personal fork.

---

# Open Discussion / AOB

## Contribution Guidelines

Matthew raised an issue about clarifying contribution guidelines and maybe checking for cross-license issues.

https://github.com/elisa-tech/wg-aerospace/blob/main/Contributing.md

https://github.com/elisa-tech/wg-aerospace/blob/main/.github/workflows/license-check.yml

https://github.com/elisa-tech/wg-aerospace/blob/main/REUSE.toml

**TODO:** This one is a really nice first contribution candidate
- Implement
- Document!

## meta-virtualization

There was a brief discussion of the potential to include the meta-virtualization package. Bruce recently gave a talk at OpenEmbedded 2026 in Brussels.

- [Link to talk details](https://pretalx.com/openembedded-workshop-2026-2025/talk/ZGLVF7/)
- [Mailing List](https://lists.yoctoproject.org/g/meta-virtualization)
- [Source Code](https://git.yoctoproject.org/meta-virtualization)

---

# Closing

## Action Items

Located in [GitHub Issues](https://github.com/elisa-tech/sig-sgl/issues)

- **TODO**: start roadmap discussion to mailing list
- **TODO**: review sgl arm64/riscv PR
- **TODO**: document contribution guidelines

## Next Meeting

-
