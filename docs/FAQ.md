---
id: FAQ
title: F.A.Q.
sidebar_label: F.A.Q.
---

## What Problems is TruSat Designed to Solve?

### What is space sustainability?

Space sustainability is about preserving the use of outer space, and all of its socioeconomic benefits, for present and future generations. The primary threat to the long-term usability of space is Earth-orbital debris: non-functional spacecraft, pieces of spacecraft discarded in the course of space missions, and fragments from collisions between spacecraft, and from spacecraft destroyed by weapons tests. While outer space is infinitely large, the orbital positions around Earth suitable for the myriad space applications on which we depend are finite and increasingly congested.

Global public awareness and concern about space sustainability is rising with the deployment of the first of thousands of satellites comprising so-called “mega-constellations” to provide broadband internet service from low Earth orbit (“LEO”). To put these constellations in perspective, the satellites planned for deployment by just three companies would add as approximately 46,000 satellites to the LEO environment in the 2025-2030 time horizon; roughly a 25X increase above the present population of operational satellites. As LEO grows increasingly congested, so grows the risk not only of collisions—between operational satellites or debris—but also catastrophic, cascading chains of collisions rendering vital swaths of Earth orbits unusable for generations.

### How does satellite tracking relate to space sustainability?

There is no air traffic control-like authority directing this growing space traffic. Enlightened satellite operators, governments, and civil society are coming together to define guidelines and standards for sustainable orbital operations. The efficacy of such standards will depend accountability for adhering to them. However, independent assessment of satellite operations against sustainability standards requires a freely-accessible, globally trusted record of satellites orbital positions. TruSat is designed to fill this gap.

### Don’t governments and companies already track objects in space?

A handful of national governments track objects in space for national security purposes, and make a portion of their data publicly available. While these government programs are vital, they are not suited for independent assessment of compliance with space sustainability standards. Because a single national government controls the data, whose creation is neither transparent nor verifiable, it is not always trusted as a source of truth by all involved in space sustainability applications.

## How TruSat Works

### What is TruSat?

TruSat is an open source, citizen-powered system for creating a trusted record of satellite orbits in service of the long-term sustainability of outer space. This TruSat System comprises two main elements: satellite observers, who make and report satellite observations, and TruSat software that autonomously processes observations of a satellite from multiple points around Earth into an orbit prediction and confidence assessment of that prediction. Space sustainability advocates may task the TruSat System to observe satellites of interest for sustainability purposes, and utilize the resulting data.

The TruSat system is developed and maintained by the TruSat Open Source Community. In addition to developing the TruSat Software, this global community of contributors provide valuable input on feature roadmaps, author documentation and other content that enable a diverse range of contributors, and translate them into multiple languages.

### Who uses TruSat’s record of satellite orbits?

TruSat’s data is openly available without restriction to anyone who chooses to use it. TruSat is designed to provide space sustainability advocates data suitable for assessing satellite operations against emerging standards for responsible orbital operations Spacecraft operators, NGOs, and Research Institutions often use this type of data to support their operations and research about objects in space.

### Why should anyone trust TruSat’s record of satellite orbits

TruSat is architected for trust. Whereas trust in existing sources of SSA data depend on trust in the humans and institutions in the loop—that the orbital prediction reflects a competent analysis of the sensor data, free of any institutional interests—TruSat substitutes transparent, verifiable algorithms for institutional input. While humans are involved in generating the initial satellite observation data fed into the System, TruSat’s Proof of Satellite software engine is entirely automated, leaving no room for tampering. Unlike existing sources of SSA data, the entirety of the algorithms that translates individual satellite observations into an orbital prediction with a confidence assessment—the confidence factors applied, and their weighting—are transparent, enabling any orbital prediction to be reverse-engineered. Built atop the Ethereum blockchain, TruSat will periodically check its file and data integrity against tamper-evident blockchain records, ensuring that the algorithms in effect at any given time are those approved by the TruSat Community. Additional verifiability of TruSat’s orbital predictions comes courtesy of nature: any person may physically observe a satellite in the TruSat catalog to verify the accuracy of the orbital prediction.

### Why a citizen-powered system?

The diversity of observations of a satellite (by geography, nationality, etc.) help to promote trust in the resulting data.

TruSat is also designed to provide opportunities for concerned citizens to make concrete, measurable contributions to the long-term sustainability of outer space.

## Using the TruSat Prototype

### How do I track satellites?

This [tutorial](https://learn.trusat.org/docs/guide) will walk you through it.

### What does “prototype” mean in the context of TruSat?

The version 0.1 TruSat software released on October 21, 2019 is an engineering prototype intended for testing and refining core elements for generating orbit predictions from observations of a satellite from multiple points around Earth. This early prototype has only a fraction of TruSat’s planned features and functionality. Notably absent in this first release are features for easing the process of making and submitting satellite observations; it relies on a relatively manual workflow for formatting observation data for submission. 

### Where is the smartphone app for tracking satellites?

The smartphone app depicted in the TruSat video is a representation of how accessible and seamless we aim to make the process of making and reporting satellite observations. We are exploring several avenues of utilizing ubiquitous consumer devices to automate and simplify the process as much as possible, including smartphone apps and features for automatically extracting Initial Orbit Determination data from digital photographs. ConsenSys Space is planning to host hackathons to build many of these features. Whether you want to share your ideas for these features or help to build them, we hope you’ll [join the TruSat Community](https://trusat.org/join).

In the meantime, several smartphone apps such as SkyView offer augmented reality features that take much of the manual work out of finding a satellite in the night sky. [See how you can use a smartphone app to find satellites here](https://learn.trusat.org/docs/guide).

### What equipment do I need to observe a satellite?

While many satellites are visible to the naked eye in locations without much light pollution, a pair of binoculars and accurate clock will enable you to reliably observe and track satellites. As explained in these [instructional materials](https://learn.trusat.org/docs/guide), a range of smartphone apps and online resources will tell you when and where in the sky to look, based on your location. If you have a digital SLR camera and tripod, you can use it to make satellite observations, as explained here.

### What is the secret that was emailed to me when I created an account?

In TruSat the identity of users is verified by a unique address found in their Ethereum wallet. You can see your address by hovering over your name in your profile page. When you sign up with an email and password, the following process happens under the hood:

- An Ethereum wallet is created for you in your browser (TruSat never has access to your wallet)
- The wallet is then encrypted with the password you provided to create a unique "Secret"
- This secret is emailed to you

In future when you need to sign in again you must verify that you are the owner of the Ethereum address tied to your identity by providing two things:

- The secret
- The password (now used to decrypt your wallet)

Therefore it is vital that you take care to store your secret and password somewhere safe. If you wish to protect your identity (wallet) in a more secure way, perhaps you can consider the browser plugin [MetaMask](https://metamask.io/). See your settings page for a handy guide on how to migrate away from the email/password/secret login flow to a more streamlined and secure one-click login via MetaMask.

## Building TruSat’s Future

### What does the TruSat roadmap look like?

Features and functionality that ease the process of making and submitting satellite observations, making TruSat accessible to the broadest-possible range of participants, are a key priority in the roadmap.

TruSat’s algorithms for calculating orbits and confidence assessments will be continuously refined by TruSat’s open source community.

The TruSat roadmap contemplates a progressive decentralization of the TruSat system and its governance, in connection with a migration to Ethereum mainnet. Migration to Ethereum mainnet will enable a range of enhancements to security, trust architecture, and the introduction of extrinsic incentives for participation.

### How can I contribute to TruSat other than by making satellite observations?

TruSat depends on the diverse skillsets of its global Open Source Community, from developing new software features to creating content in multiple languages to enable people around the world to participate and contribute. To learn more about these opportunities, please [join the Community](https://trusat.org/join).

[Visit here](https://learn.trusat.org/docs/participate#3-support-the-mission)to  explore how to contribute.


### How does TruSat make money?

As the TruSat.org domain signifies, TruSat is designed to generate a global public good rather than profit.

### How is TruSat governed?

The [TruSat Charter](https://trusat.org/charter) specifies the governance arrangements for the TruSat System and Open Source Community. The Charter will be regularly revised to meet the governance needs of the Community and to give effect to its Guiding Principles. Each version of the Charter is identified by an Epoch: a period measured in time or milestones in which that version is in effect.


Have any other questions? Please bring them to the [Help Desk thread topic of the TruSat Forum](https://discuss.trusat.org/t/trusat-help-desk/15/30)

