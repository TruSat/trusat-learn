---
id: roadmap
title: Roadmap
sidebar_label: Roadmap
---

## V. TruSat Roadmap

The initial v0.1 software release is alimitedprototype for testing and refining the Proof of Satellite software engine.The very-near term roadmap will complete implementation of the initial concept feature-set, and address known-limitations (described below) including refinements to the automation, confidence, priority and user-performance algorithms. The v0.2 release later in Q4 2019 will add Mission tasking and other functionality.Subsequent releases will introduce features designed toenable the systemto scale, by easing the process of making and reporting satellite observations, and progressing to a fully decentralized system.The roadmap for these subsequent releases may evolve with user-community feedback introducingnew ideas, and focus development priorities.

### V.A. Known limitations of initial release

As a prototype, the v0.1 release is far from feature-complete, and has several traditional solutions to common problems, allowing the team to focus on developing and demonstration core innovations in the TruSat system. The initial release relies on a central web server on an AWS instance, as well as a central relational database for storing TruSat data. Whereas subsequent releases will further implement TruSat’s decentralized, autonomous architecture, the ConsenSys Space will retain control over the network during alpha testing. The v0.1 release will utilize email-opt-in techniques for verification of identity. The v0.1 release likewise utilizes some relatively dated and simplistic orbital dynamics code, on the theory that utilizing open-source code bases could accelerate the deployment of a basic prototype and accelerate the point at which the community can help to evolve the code base with state-of-the-art algorithms.

### V.B.Future Features to Scale Global Contributor Network

The following features and functions are tentatively planned to scale the global network of citizen satellite observers by making it easier and more enjoyable to make and report satellite observations. This roadmap will evolve based on user-community input.

- Features that ease the process ofmaking and submitting satellite observations, such as:
  - A smartphone app that assists an observer in orienting her binoculars at the right point in the sky, and enables her to time the satellite and directly submit an IOD to the system with the press ofa single button.
  - A smartphone app leveraging the improved low-light camera capabilities of contemporary phones (e.g,. Pixel 4 and iPhone 11) to place the entiresatellite tracking workflow on a single screen.
  - A web app interface enabling satellite observers to directly input the basic observation parameters (time and location), dispensing with the need to utilize third party software to calculate and format an IOD for submission.
  - Automated generation of observation “station.”
  - Translation of interfaces and documentation into multiple languages.
  - Integrating radio observations (e.g, “satnogs”).
  - Automated image processing and IOD extraction from digital images
- Much of what is needed to integrate automated IOD extraction from digital camera images appears to be available in Cees Bassa’s sattools/stvid open-source code):
- Receive image frame from registered user (known location)
- (Repeat) Plate-solving
- Perform feature detection of image / image series, looking for known/expected objects based on user capability profile
- Optionally, perform further algorithmic exploration of unidentified objects (UNIDs)
- Extract position / time information, or verify efficacy of user-provided IOD/UK/RDE-formatted position observation for each IOD
- Cross-Correlate existence of IOD object, with database state vectors (TLE, or more detailed internal format
- Direct tasking of motorized, software-enabled consumer telescopes or scriptable robotic observatories
- Beyond software: grants of satellite observing hardware in service of greater geographic and socioeconomic diversity of satellite observers.

- In addition to making satellite tracking easier, a number of featuresare contemplated to make the experience more fun and meaningful. Among the possibilities are:
  - Missions linking observations to concrete sustainability outcomes.
  - “Adopt-a-satellite”: assign a satellite to observers around the world, who are responsible for tracking it.
  - “Don’t-brake-the-chain”campaigns and badges.
  - Community-combinedor “team”goals: goals thatrequire multiple users to collaborate to achieve an outcome (e.g., track deployment of new microsat cluster launches, communications constellation deployments)

### V.C. Web3 Functionality Roadmap

In its initial prototype releases, TruSatwill implement three features of blockchain functionality.

- **A.** User identity via wallet-based login, and the associated Web3 onboarding opportunity.
- **B.** Registering of “authenticated” versions of code and algorithm base in the runtime code.
- **C.** Periodic consistency checking of tamper evidence by comparing with blockchain checkpoints for code-base and data-base.

After implementing these basic features, and demonstrating the broader utility and value of the PofSAT engine, a transition to Ethereum mainnet will enable more advanced features:

- 1. On-chain transactions for (up to) every observation block, and associated TLE prediction update.
- 2. On-chain stores of value (reputation, incentives, NFTs, etc.).
- 3. State-channel object storage (TLEs, algorithms, meta-data, etc.).

#### V.C.1. Decentralizing the System and its Governance

- Migrating to Ethereum Mainnet for decision democracy(e.g., for feature priority).
- Decentralized system for “tasking” the network (i.e., prioritizing satellites for observation).
- Decentralized governance of Proof of Satellite Engine upgrades.
- Decentralized moderation of general TruSat codebase.
- Community moderated “graduating” privileges of contributors.
- A system for distributing rewards/incentives to contributors (see next section).

#### V.C.2. Implementing On-Chain Incentives

In its initial releases, TruSatdepends on participation (i.e., satellite observations) by individuals motivated by a concern for space sustainability and a desire to be a part of the solution; and individuals who enjoy the “sport” of spotting satellites.

- Relies on limited suited of Web2.0 mechanisms for enhancing the experience of sporting and sustainability-minded users (e.g., analytics and rankings, campaigns linked to sustainability objectives).
- Migrating to Ethereum Mainnet will enable TruSat to implement a fuller set of incentives for participation, including, potentially, distribution of value created by the network to its data contributors.
  - There has never been a tool quite like this, and ascertaining how it is used is part of the experiment. This will inform the universe of possibilities and design of incentive structures for future releases, including potentially a token model.
- Initial release is also dependent on the interests of the TruSat Partners in continuing to operate and develop this sustainability tool. Plan for release on Mainnet is to supply incentives for decentralized maintenance of this tool.

Initially, bug reports and feature requests will be tracked and managed at:[https://github.com/trusat/](https://github.com/trusat/)
