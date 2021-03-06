---
id: overview
title: Overview
sidebar_label: TruSat Overview
---

To view the TruSat white paper in PDF form, you can read and download it [here](https://trusat-assets.s3.amazonaws.com/TruSat+White+Paper_v3.0.pdf).

## Introduction

TruSat is an experimental open source, open-sensor system for creating a trusted record of satellite orbits. TruSat is primarily designed to enable the assessment of satellite operations in light of space sustainability standards. Space sustainability is about preserving the use of outer space, and all of its socioeconomic benefits, for present and future generations.

<small>See the United Nations' [Guidelines for the Long-term Sustainability of Outer Space Activities](https://www.unoosa.org/res/oosadoc/data/documents/2018/aac_1052018crp/aac_1052018crp_20_0_html/AC105_2018_CRP20E.pdf)</small>

As a practical matter, this means mitigating orbital debris, which can render orbits around Earth unusable for generations. Amid projections of a tenfold or more increase in the number of satellites in low Earth orbit (“LEO”), avoiding collisions between satellites is an increasingly urgent focus for space sustainability, and enlightened satellite operators, governments, and civil society are working to defineguidelines, best practices, andstandards for sustainable orbital operations. A crucial gap in these efforts is the absence of an open, widely-trusted source of data about the orbital position of satellites accessible for use in assessing compliance withthesesustainability standards. <small>1</small>

To fill this data gap, the TruSat System is designed to enable the emerging space sustainability community to “task” a global network of citizen satellite observers to track satellites of interest, utilizing ubiquitous consumer hardware, and to assemble observations from around the planet into a trusted record of orbital positions suitable for measuring orbital behavior against sustainability standards. The TruSat System comprises three elements:

- Software for prioritizing satellite observations, assisting amateur satellite observers, and processing observations into orbital predictions;
- Observers who make and report satellite observations; and
- An interface with the space sustainability communityfor aligning the System’s satellite observation priorities with sustainability priorities.

## Space Sustainability
[This section](space-sustainability) surveys the space sustainability landscape and situates TruSat within it. It describes an externality in the liability framework for space that leaves the incentives of satellite operators misaligned with the common interest in the long-term sustainability of spaceflight. On the one hand, satellite operators are not generally made to internalize the costs of collisions in orbit. On the other, many sustainability measures—such as maneuvers to avoid a potential collision or for end-of-life disposal—entail a cost to the operator, in terms of the operational life of the satellite. Faced with a probabilistic collision warning, an operator’s incentives may point to rolling the dice rather than maneuvering.

Growing concern about space sustainability by the general public and regulators alike, coupled with the emergence of measurable, verifiable standards for sustainable satellite operations, could raise the costs to operators of unsustainable operations, bringing their incentives more in line with the long-term sustainability of outer space. However, the efficacy of sustainability standards depends on independent assessment of satellite operators’ conformity with them. This assessment function, in turn, requires a freely available source of orbital positiondata trusted by all involved. This element is missing. The trustworthiness of space situational awareness (“SSA”) data collected and publicly shared by a government has been widely questioned on account of national interests sometimes at odds with full transparency about satellite positions, and that governments, for national security reasons, neither share the full extent of their SSA data nor the sensor data or algorithms underlying it that would enable independent assessments of its accuracy. The business interests of commercial SSA data providers, which sell SSA data and analysis to satellite operators, raise similar questions about whether their data would be trusted by all parties, particularly in matters concerning present or prospective customers.

TruSat is architected for trust. Whereas trust in existing sources of SSA data depend on trust in the humans and institutions in the loop—that the orbital prediction reflects a competent analysis of the sensor data, free of any institutional interests—TruSat substitutes transparent, verifiable algorithms for institutional input. While humans are involved in generating the initial satellite observation data fed into the System, TruSat’s Proof of Satellite software engine is entirely automated, leaving no room for tampering. <small>1</small>

Unlike existing sources of SSA data, the entirety of the algorithms that translates individual satellite observations into an orbital prediction with a confidence assessment—the confidence factors applied, and their weighting—are transparent, enabling any orbital prediction to be reverse-engineered. Built atop the Ethereum blockchain, TruSat will periodically check its file and data integrity against tamper-evident blockchain records, ensuring that the algorithms in effect at any given time are those approved by the TruSat Community. Additional verifiability of TruSat’s orbital predictions comes courtesy of nature: any person may physically observe a satellite in the TruSat catalog to verify the accuracy of the orbital prediction.


## How TruSat works
[This section](proof-of-sat) provides a detailed technical overview of the Proof of Satellite software engine, illuminating the engineering challenges of creating an orbital location system that is open and permissionless (anyone may feed data into the system), and automated (the system evaluates and weights data, rather than a human administrator), and how each is addressed in the initial release. This section surveys foreseeable attack vectors—from malicious attempts to subvert the system by submitting false observations, to simple mistaken observations—and how the application of confidence factors mitigate each attack vector. Section III likewise explains how the same confidence factors are applied to provide a confidence assessment for each orbital prediction. These confidence factors and the algorithms applying and weighting them will be the subject of ongoing tuning and revision by the TruSat Open Source Community.

<small>2. For a discussion of how TruSat mitigates efforts to tamper with orbital predictions by submitting false observations, see Section III.C: Mitigating Attack Vectors</small>
