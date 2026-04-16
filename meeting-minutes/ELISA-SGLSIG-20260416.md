![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 16 April, 2026

# Agenda

- Roll Call
- Brief Notices
- Announcements
  - Foundation Update
  - ELISA Workshop London - Call for Speakers
  - Upcoming Events
- Mailing List Highlights
  - Fault-Tolerant Filesystems: FTRFS and ZFS in Space
  - Roadmap RFC Feedback Summary
- Technical Topics
  - Roadmap Discussion (continued)
  - Doc Relicensing Update (CC-BY-SA-4.0 to CC-BY-4.0)
  - PR Review
- Action Items Review
- Open Discussion / AOB
- Closing

---

# Roll Call

## Attended this meeting

- Tim Bird (Sony)
- Alexey Simonov (TII)
- Matt Weber (Boeing)
- Jan-Simon Moeller (AGL)
- Philip Balister (OpenEmbedded)
- Pedro Roque
- Ramon Roche (LF)
- Shafai Sharma
- Rob Wooley (Wind River)
- Brian Kempa

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

- ELISA Project meetings involve participation by industry competitors, and it is the intention of the Linux Foundation to conduct all of its activities in accordance with applicable antitrust and competition laws. It is therefore extremely important that attendees adendas, and be aware of, and not participate in, any activities that are prohibited under applicable US state, federal, or foreign antitrust and competition laws.
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

- **May 18-20** Open Source Summit North America -> [link](https://events.linuxfoundation.org/open-source-summit-north-america/)
- **May 27-28** Embedded Recipes, Nice France -> [link](https://embedded-recipes.org/2026/)
- **May 29** Yocto Project Summit, Nice, France -> [link](https://pretalx.com/yocto-embedded-recipes-2026/)
- **June 8-12** RISC-V Summit Europe, Bologna, Italy
  - Special session for RISC-V in Space
- **June 9-11** ELISA Workshop London at Canonical -> [link](https://elisa.tech/event/elisa-workshop-london-2026/)
  - CFP open until April 30: https://forms.gle/btaErWe5JuJFwPoG8
- **Aug 03-07** IEEE SMC-IT/SCC in Pasadena, California, US -> [link](https://2026.smcit-scc.space/)
- **Sept 13-17** ICAS Congress in Sydney, Australia -> [link](https://icas2026.com/)
- **Sept 13-17** DASC Congress in Orlando, USA -> [link](https://dasconline.org/2026/)
  - Our AeroWG paper got accepted
- **Oct 2026** High Integrity Systems Conference [Link](https://www.his-conference.co.uk/)
- **NASA SPARK** submissions -> [link](https://spark.nasa.gov/)

---

# Announcements

## Foundation Update

SGL is moving toward becoming a standalone Linux Foundation project. We have begun outreach to companies and space agencies about founding membership, and the response so far has been very encouraging.

If your organization is interested in being part of the inaugural group of founding members, now is the time to start that conversation. Founding members will be recognized at launch and benefit from the visibility that comes with it. This is open to organizations of any size, and there is no commitment required to explore the opportunity.

Even if you are just exploring, please reach out to Ramon directly at rroche@linuxfoundation.org. We are happy to have a confidential 1:1 to answer questions and share more about what founding membership involves.

## ELISA Workshop London - Call for Speakers

The next ELISA Workshop is June 9-11 in London at Canonical's office near Tower Bridge. 2.5-day in-person event, free to attend. CFP open until April 30.

We are particularly looking for talks from the European space community (ESA, CNES, DLR).

---

# Mailing List Highlights

## Fault-Tolerant Filesystems: FTRFS and ZFS in Space

Yasushi shared an LKML RFC for [FTRFS](https://lore.kernel.org/lkml/20260413142357.515792-1-aurelien@hackers.camp/) - a new filesystem designed for radiation-intensive environments.

Phaedrus Leeds (Aerospace Corporation) responded with their experience flying ZFS on Linux on a CubeSat (Nvidia Jetson TX2 NX). ZFS provides checksums, data duplication, and transparent repair for both metadata and content. [FSW 2024 talk](https://www.youtube.com/watch?v=IowV952Jx-8).

Tim Bird suggested SGL should consider ZFS integration (with licensing caveats around upstream acceptance).

**Discussion**: should SGL evaluate both FTRFS and ZFS for inclusion? What are the licensing implications?

**FTRFS**: Interesting approach seems technically sound, however the main justification seems to be its auditable, one question from the group was "Are auditors looking for auditable filesystems?"  (Is auditing just the filesystem sufficient, or does the entire OS need auditing?)

**ZFS**: In the talk they demo with a Jetson, however commercial versions don't ship with ECC, is ZFS good enough on its own?

What hardware fault tolerance should we assume as a baseline?  Recent disk controllers are doing more fault tolerance.

## Roadmap RFC Feedback Summary

The roadmap RFC sent after the April 2 meeting has generated good engagement on the mailing list. Several community members responded with priorities and offers to contribute. Key themes emerging from the feedback:

- **QEMU fault injection**: strong interest, contributors willing to commit time
- **RAUC / OTA updates**: community experience with RAUC + hawkBit, including non-standard partitioning schemes (Golden/Main vs A/B)
- **ECSS compliance guidance**: multiple organizations flagged the lack of clear guidance on how Linux-based systems should be approached within ECSS standards
- **EDAC/ECC**: interest in FPGA-based implementations for memory scrubbing
- **Immutable OS / container-based deployment**: recurring interest
- **Zephyr RTOS integration**: interest from multiple parties
- **Space networking**: CCSDS File Delivery Protocol (CFDP), Delay-Tolerant Networking (DTN), SpaceWire, libcsp
- **Ground systems**: experience with Yamcs
- **AMD/Xilinx Zynq platform support**: demand for Zynq7000, UltraScale+, and Versal targets
- **Real-time capabilities**: characterization of PREEMPT-RT performance (latency, jitter)
- **Reproducibility**: KAS-based build guarantees
- **cFS integration**: existing experience in the community

The RFC thread is still open. If you have not responded yet, please do so on the mailing list.

---

# Technical Topics

## Roadmap Discussion (continued)

Continuing the roadmap RFC from last meeting. Good engagement on the mailing list since then (see highlights above). The RFC thread is still open for additional input.

Boeing and AMD are doing a Xen functional safety, on Aerospace, mixed criticality, mixed function talk at the ELISA London workshop

**TODO:** follow up with Matthew weber, maybe add a Space workload example

**Proposals for Roadmap:**
* Minimal System Layer, stripped down and usable out of the box
  * Documenting whats in the build, and why.
  * Run a hello world example, and trace down. Look up Workload Tracing for the Linux Kernel. (covers full kernel + userspace view)
    * See https://www.kernel.org/doc/html//v6.9/admin-guide/workload-tracing.html
    * [ELISA Subsystem trace research](https://github.com/elisa-tech/ELISA-White-Papers/blob/master/Processes/Discovering_Linux_kernel_subsystems_used_by_a_workload.md)
  * Aerospace is working a minimal practice activity with docs, [background here on end user goals](https://github.com/elisa-tech/wg-aerospace/issues/168#issuecomment-4183867886)
* Stress and do analysis on partitions on workloads, with [stress-ng](https://github.com/ColinIanKing/stress-ng)
* CI all the way to hardware, make sure we are verifying hardware runs builds
* cFS info: https://github.com/elisa-tech/wg-aerospace/blob/main/demos/docs/Build-cFS.md

## Doc Relicensing Update

Relicensing meta-sgl documentation from CC-BY-SA-4.0 to CC-BY-4.0. Approval emails sent to contributors. Alexey Simonov approved. Waiting on responses from Matthias Schmitz and Celeste.

## PR Review

### Open

| # | Title | Author | Status |
|---|-------|--------|--------|
| [#47](https://github.com/elisa-tech/meta-sgl/pull/47) | kas: add QEMU SpaceROS (jazzy-2025.10) for x86-64 build target | Aleksandar Nikolic | Open |
| [#43](https://github.com/elisa-tech/meta-sgl/pull/43) | kas: Add Space ROS Jazzy 2026.01 | Rob Woolley | Open |
| [#30](https://github.com/elisa-tech/meta-sgl/pull/30) | meta-sgl-core: add zeroconf networking as optional image feature | Ramon Roche | Open |

---

# Action Items Review (from Apr 2)

- Roadmap RFC sent to mailing list - done (responses coming in)
- Add Pedro and Ivan as maintainers - done

---

# Open Discussion / AOB

**Embedded Recipes LFG**

Reach out to Philip if you are going! He's buying drinks.

---

# Closing

## Action Items

- Ramon: follow up with Matt Weber on adding a Space workload example to the roadmap
- Group: evaluate FTRFS and ZFS for SGL inclusion, including licensing implications and hardware fault-tolerance baseline assumptions
- Ramon: chase remaining doc relicensing approvals (CC-BY-SA-4.0 -> CC-BY-4.0) from Matthias Schmitz and Celeste
- Roadmap: draft Minimal System Layer proposal, documenting what's in the build and why; prototype a hello-world workload trace using kernel workload tracing docs and ELISA subsystem trace research
- Roadmap: scope partition stress/analysis work using stress-ng
- Roadmap: define plan for CI all the way to hardware (verify builds run on target)
- Reviewers needed on open PRs: [#47](https://github.com/elisa-tech/meta-sgl/pull/47), [#43](https://github.com/elisa-tech/meta-sgl/pull/43), [#30](https://github.com/elisa-tech/meta-sgl/pull/30)

Tracked in [GitHub Issues](https://github.com/elisa-tech/sig-sgl/issues)

## Next Meeting

-
