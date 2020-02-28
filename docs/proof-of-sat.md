---
id: proof-of-sat
title: Technical Overview of the Proof of Satellite Software Engine
sidebar_label: Technical Overview of the Proof of Satellite Software Engine
---

## III.Technical Overview of the Proof of Satellite Software Engine

The technical problem to which the Proof of Satellite software engine (“PofSat”) is addressed is proving a satellite’s orbital characteristics from individual observations that are not alone trustworthy. By leveraging the immutable characteristics of “on-chain” transactions, the PofSat engine is designed to be a substantially autonomous, decentralized capability, which can produce useful results without central moderation.

A satellite’s orbit can only be perturbed by a limited number of phenomena, generally listed in order of effect, from greatest to least: <small>1</small>

1. The launch vehicle, or final transfer or insertion stage of the rocket (often called rocket boosters, of which many remain in orbit)
2. The satellite’s own propulsion system, or in the future, effects of third-party orbital transfer or satellite servicing
3. Collision with an object or debris particle in orbit
4. Drag effects from the Earth’s atmosphere (most prevalent at lower orbits, typically below 1,000km in altitude)
5. Gravitation effects related to the non-spherical nature of the Earth’s gravitational field, the Moon, other planets, etc.
6. Solar wind and other space weather effects

The Proof of Satellite engine leverages two features of Earth orbiting objects:

1. The satellite orbits behave according to physics (Newton’s Laws), and thusly must be “in-family” with prior observations.
2. Satellites positions and orbits are (theoretically) observable by anyone who knows where or how to look

Because of this, public trust ina prediction of where the satellite will be, according to the physics of orbital mechanics, can besuccessively verified by observations that the satellite is behaving (orbiting) as predicted. New observations have the potential to improve confidence in the orbit predictionas well as confirm prior estimates of it for purposes of assessing the performance of algorithms, observers and specific techniques contributing to these estimates.

### III.A.Confidence Factors

Beyond leveraging orbital mechanics and successive observations of a satellite from multiple points on Earth, the initial release will utilize the following confidence factors to automatically sort orbit predictions in the catalog into six confidence levels. Unlike the publicly-available SSA data from the U.S. Government—which discloses neither sensor data nor algorithms, citing national security reasons—the factors and evolving algorithms for weighting them in the TruSat catalog will always be transparent. By providing the confidence data and supplying the code which determines it via open-source, TruSat data users receive a confidence assessment, and also the means of understanding how the system reached that assessment. The factors incorporated in these types of algorithmic ranks are anticipated to be subjects of future community governance activities, when the platform is able to accommodate on-chain governance to elect specific versions of new algorithms.

Confidence in the orbit of a particular satellite or space object is influenced by the following factors:

- **A)** Time -Newer observations generally increase confidence. As the data ages, the confidence naturally decays from the influence of perturbing effects on the satellite’s orbit.
- **B)** Diversity of Observers: Confidence increases with multiple observations of a satellite, and increases to its highest level when there is geographic and nationaldiversity in the observers.
- **C)** Performance history of the Observer: Observers who have consistently provided good results can advance the confidence of a satellite orbit more quickly than unknown, or inconsistent observers. (see User Rank, below)
- **D)** Traceability, Transparency of the raw data: Raw and derived observation data is cryptographically hashed,and demonstrated to (continue to) exist, and traceable to the orbit determination result. Removal of, or compromise to this data will have a negative effect on the confidence of the satellite orbit.

Based upon these factors, PofSat will automatically sort satellites in the catalog into the following confidence levels:

- **(5)** Highest Confidence
- **(4)** High Confidence
- **(3)** Verified
- **(2)** Plausible
- **(1)** Neutral
- **(0)** Untrusted

Users of the TruSat catalog may sort satellites by confidence level for a variety of purposes.Among them, satellite observers may wish to prioritize their observations to increase confidence in relatively low-confidence predictions by submitting additional observations on satellites rated (3) or below

### III.A.1. Time -Recency of Observation

As introduced above, the confidence in a satellite’s orbit decays from the influence of perturbing effects on the satellite’s orbit, as well as limitations in the chosen models used to propagate and communicate future predictions of the satellite’s orbit. For the initial version of this algorithm, we are implementing the SGP4/SDP4/SGP8 <small>2</small> algorithms which are optimized for results in the vicinity of the time epoch for which they are produced.

Excluding spacecraft maneuvers from perturbations, orbit knowledge of objects in Low Earth Orbit (LEO) will generally degrade more quickly than objects farther away from the atmospheric and non-spherical gravitational perturbations induced by the Earth itself. As a result, a “High Earth Orbit” object could have orbit knowledge that is more accurate than a low Earth orbit object, with the same time having passed since each of their most recent observations.

For the initial version, the weight factor on “time” will be determined empirically.

### III.A.2. Observer Diversity

The PofSatengine depends on access to the physical coordinates from which observations are made, provided directly by the user. The combination of the “angles only” measurements of a satellite, and the location from where they were made are necessary inputs in using these measurements to determine a revised orbit estimate. This cannot be achieved without access to both pieces of data.

As is often the case with measurements of physical properties, a “longer baseline” over which to make these measurements increasesthe precision of the measurement. Two measurements on opposite sides of the Earth can provide more insight into the orbit than two closely-spaced measurements from Amsterdam are able to. Alternatively, observations of an object by a single observed spaced by a complete orbit provide a higher-fidelity observation, but do not provide diversity in data source which builds additional trust.

In addition to a geographic diversity of observations ability to improve the accuracy of an orbit prediction, when taking into account potential Attack Vectors (described later in this document) on the PofSat engine, we can also benefit from any knowledge of “National Diversity” or more generically, allegiance to a particular faction.

Theoretically, if all the observers in Amsterdam were to conspire to make predictions which benefited themselves, and increased their rank or perpetuate a version of the catalog for their own objectives, we would be motivated to incorporate and provide weight to observations which were linked to allegiance to Amsterdam, or were distinct from it. While to first order, it may seem sufficient to apply this weighting based on these users’ geographic coordinates, their ability to acquire observations in remote locales (say, through telescope-for-rent services such as iTelescope, Slooh, or Lightbuckets <small>3</small>) could easily evade this weighting. To be able to implement this type of “faction diversity” may require some amount of Know-Your-Customer efforts (KYC) in order to gain third party confidence of the identity and affiliations of an observer, and as a result is scoped for implementation later in the roadmap.

### III.A.3.User Rank

Certain efficiencies can be realized by taking into account the performance history of an observer, and an assumed desire onthat user’s part to obtain a positive ranking within the system, and for the system to provide a beneficial result for the community. The ultimate outcome in evaluating a user’s relative ranking is how their observations relate to verifiable accurate results as observed, and subsequently contributed by other users.

If User A contributes an observation resulting in subsequent observations from other users being more accurate, then User A’s rank increments positively.

If User A contributes an observationresulting in divergence from subsequent observations, then User A’s rank decrements.

Taking into account every contributing user into the system allows for varying weights (both positive and negative) to be applied to observations from known users as appropriate for the available data. In the use-case thus far, observations are made in short batches, and observations by multiple users do not typically overlap within these batches. This provides an opportunity to update the estimate on a user-by-user, observation-batch-by-observation-batch cadence to simplify an initial approach. Due to the immutability of the dataset and its history provided by blockchain, users will not be able to hack the ranking records, but can only influence their own rank by submitting observations which are positively verified by other users.

For the v0.1 release, the specific factors contributing to initial rank are being established, but they are expected to include aspects of:

1. Total number of validated observations contributed
2. Longevity of contributions
3. An empirically-derived weighting factor for #1 and #2 to add weight for users who have contributed recently (this prevents legacy users from having undue influence if they aren’t continuing contributors)
4. A factor relating to inclusion/exclusion of a user’s observations increasing/decreasing the residuals of other users’ observations

The end result of applying user-rank into observation weighting is two-fold:

1. The effect a user’s contribution has on the estimate of an object’s orbit, and
2. The speed at which object confidence is elevated per each new observation (low rank users have little-to-no effect, while high-rank observers may allow graduation to the next confidence level immediately)

This rank is anticipated to be updated for every batch of new observations submitted by the user, with the opportunity to update the associated TLE estimates at the same moment.

Details of the user rank algorithm are being finalized for the 0.1release of the PofSat engine, and will be fully detailed in a 0.1release of this whitepaper, along with the source code on GIT.

As described in the roadmap at Section V, successive releases will introduce extrinsic incentives for observing satellites.

### III.A.4. Observation Trace-ability and Audit

In the post v0.1roadmap for TruSat will be the ability to accommodate the raw data (position observations of satellites) fusing a facility like IPFS <small>4</small> to store it in a distributed and immutable fashion. Semi-automated open source image object identification and observation reporting capabilities already exist, in projects such as sattools <small>5</small> and stvid <small>6</small>, and incorporation of these code-bases and the storage of the raw data in IPFS could allow for third-party verification and machine-learning assistance of verification of observations, as well as contributing to better results as a result of an increasingly large training dataset. Separately, itprovides an opportunity for non-observing laypersons to contribute to the effort merely by volunteering to serve as an IPFS node for the TruSat data, similar in style to how “SETI-at-Home” and now the Berkeley Open Infrastructure for Network Computing (BOINC) application allows individuals to donate their spare computing sources towards scientific computation pursuits.

Workflows which include a raw astrometry dataset also provide for the opportunity to extract additional information such as object visualmagnitude and variability, which may relate to certain sustainability factors.

Further discussion of the utility of utility of Traceability and auditable data will be discussed in the section relating to Attack Vectors below.

### III.A.5. Object Priority

TruSat’s mechanisms for prioritizing specific objects for priority observation are central to its utility as a sustainability tool. To-date, the amateur satellite observation community has loosely coordinated observations by email threads, often in connection with new launches of interesting payloads, or with objects that have been a subject of conversation in the community. While TruSat welcomes satellite observations made according to the personal interests and priorities of its observers, itintroduces new functionality for communicating the System’s highest priorities for observation to its user community, and incentivizing observation of those objects.

Two mechanisms for prioritizing observations are presently contemplated: (1) manual inputs from the space sustainability community (initially via the TruSat Partners) to align observation priorities with that communities data needs; and (2) automated prioritization to increase confidence in orbital predictions.

#### III.A.5.a. TruSat Missions: Manual Inputs from Space Sustainability Community

TruSat’s Mission functionality, which will be introduced for testing in the v0.2 release later in Q4 2019,enables space sustainability advocates to task the TruSat system to obtain data needed for sustainability applications. For example:

- To verify a satellite operator’s claim to have placed a satellite in a disposal orbit, in conformity with a sustainability standard.
- To record the tracks of two satellites that are the subject of a conjunction alert.
- To assist in the identification of satellites following a launch of multiple small satellites.

Whereas in the v0.2release such taskings will be facilitatedby the TruSatPartners, pursuant to the procedures prescribed in the TruSat Charter, the TruSat roadmap contemplates a progressive decentralization of the Mission tasking function, in step with the migration to Ethereum mainnet, including the possibility of voting by the broader community of satellite observers.

Each manual tasking creates a Mission: a satellite prioritized for sustainability purposes, with a brief explanation of the significance of the Mission. From this context, individual satellite observers may choose whether or not to participate in the Mission by observing the specified satellite. Whereas the v0.2release will depend on the intrinsic motivation of observers to contribute to space sustainability ends, subsequent releases may introduce extrinsic motivators, including digital “mission patches” unique to each mission, and other inducements appealing to observer’s sporting sensibilities including possible use token-staked bounties which could carry monetary/marketplace value.

#### III.A.5.b. Automated Prioritization

Separate and apart from “TruSat Missions” functionality, TruSat automatically identifies priorities for observation to increase the confidence of orbital predictions. Below are several factors that TruSat will utilize in developing a priority of an object

- Algorithmically, the Proof of Satellite engine depends on continued observations to address the natural decay in confidence by the passage of time. If the time-since-last-update has passed a threshold for a particular orbit regime or object class, the engine will increment the priority of the object.
- If more geographic diversity is needed to elevate the Object Confidence to the next level, the Object Priority will be incremented.
- If an object has few or no observations by high-ranked users, that object will be prioritized for those users.

TruSat will be able to provide a list of priority-interest objects on a global perspective, as well as provide a priority list which is customized for a specific user’s location, rank andcapability (such as inferred or specified limiting magnitude sensitivity).

Details of the Object Priority algorithm are being finalized for the 0.1 release of the PofSat engine, and will be fully detailed in the source code in the TruSat software repository and in accompanying documentation.

## III.B. Confidence Factors Applied

The scenarios that follow serve to illustrate how the confidence factors are applied by the Proof of Satellite engine to mediate its best estimate of objective orbital truth.

In a traditional curated catalog, expert administrators can review the data as it relates to observer performance for data consistency, technical biases, and other concerns which may influence the final result. That administrator can exercise judgment in “if and how” to incorporate data into their prediction results. TruSat removes any such administrator from the loop, substituting algorithmic applications of confidence factors as follows.

The scenarios in this section illustrate how the TruSat confidence factors are applied to curate data from good faith, competent visual observations in their intended use. The scenarios at Section 1.D.3. illustrate how the same confidence factors may serve to mitigate potential attack vectors, from erroneous observations to malicious attempts to undermine the accuracy of orbital data in the TruSat catalog.

Use Case Summary:

- New observation of a (3) Verified object
- Operator data for a (4) High Confidence object
- New (divergent/poor quality) observation for an object
- Uncorrelated object observation from a well-ranked user
- Uncorrelated object observation from a low-ranked user
- Previously unknown object
- New observation of a low-confidence object
- New low-ranked observation of a “verified” object

### III.B.1. Verified Object (3), New Observation

Situation: A demonstrated consistent TruSat user looks for an object ranked “(3) Verified” and is able to find it based on the orbit prediction. She submits one or more observations with the object’s observed location and time. Her observation correlates well with prior observations. She is also located a large distance from other reporting observers, and the object now has observations from three countries over 24 hours.

Resolution: The new observation is used to refine the orbit prediction, object is upgraded to “(4) High Confidence”, and put (lower) in the priority queue for other users to routinely update and maintain confidence.

### III.B.2. High Confidence Object (4), New Data from Operator

Situation: A wallet (blockchain-secured account credentials) associated with the operator of a satellite provides its own tracking and telemetry data based on on-board GPS measurements for a “(3) Verified” or higher object. Their data correlates well with other users’ observations.

Resolution: The new observation data is used to refine the orbit prediction with increased weighting, object is upgraded to “(5) Highest Confidence”, and put (lowest) in the priority queue.

### III.B.3. Plausible or Higher Object (2+), New (poor quality) Observation

Situation: A new TruSat user submits an observation which appears to correlate to a catalog satellite. However, (as yet) unknown to the system, the user’s clock was wrong, their GPS position was off, or there was otherwise an error in their data which caused the orbit to be made less accurate.

Resolution: The new observation data is used to refine the orbit prediction, object is upgraded to “(3) Verified”, and put in the priority queue for other users to continue to verify and increaseconfidence. However, subsequent observations reveal this data as an “outlier”, and its weight in future orbit determinations is reduced, and the user confidence is adjusted lower as a result of the poor quality observation.

There is an opportunity in statistical analyses of observations to provide user feedback based on certain observables -in this case, a persistent bias in their observations and potential remedies to correct it. TruSat also provides a new capability for a user to see their observations along-side other users’ observations for direct feedback on their performance relative to other users observing the same object.

### III.B.4. Known Object not in TruSat Catalog, New Observer:

Situation: A new TruSat user contributes data which cannot beautomatically correlated with an object currently in the database via user-specified NORAD number and/or International Designation. The designation however is on-record with the Celestrak SATCAT which TruSat periodically incorporates.

Resolution: The object is included in the catalog, confidence level is set to “(1) Neutral” and object is flagged for follow-up by other observers.

### III.B.5. Known Object not in TruSat Catalog, High Performing Observer

Situation: A well-ranked TruSat user contributes datawhich cannot be automatically correlated with an object currently in the database via user-specified NORAD number and/or International Designation. The designation however is on-record with the Celestrak SATCAT which TruSat periodically incorporates.

Resolution: The object is included in the catalog, confidence level set to “(2) Plausible” and object is flagged for follow-up by other observers.

### III.B.6. Previously unknown object:

Situation: A TruSat user contributes data which cannot be automatically correlated with an object currently in the database based on orbital characteristics derived from 2 or more observation data points, using an “analyst” designation to represent its unidentified (UNID) status.

Resolution: The object is included in the catalog, assigned a unique (hexidecimal) catalog number, recorded at a “(1) Neutral” confidence level and is flagged for followup by other observers.

### III.B.7. Unverified (1) or Plausible Object (2), New Observation

Situation: A well-ranked TruSat user looks for an object ranked “(1) Neutral” or “(2) Plausible”, is able to find it based on the orbit prediction and submits an observation.

Resolution: The new observation is used to refine the orbit prediction, and is upgraded to “(3) Verified”, and put in the priority queue for other users to continue to verify and increase confidence.

**_Caveat -An observer can’t verify their own observation. If they discovered it, and later (a day, a week) observe it again, the orbit is refined, but the ranking remains “(2) Plausible” until a third party observes it._**

### III.B.8 New low-ranked observation of a Verified (3) object

Situation: A low-ranked TruSat user submits an object of a verified object. This object may have previously held a higher confidence ranking, but was demoted by the system after passage of too much time.

Resolution: The new observation is used to refine the orbit prediction, but the Object Confidence ranking is not upgraded. The Object is flagged for follow-up by well-ranked users. Note that if this TruSat user once held a higher rank, but was demoted for confirmed inaccurate observations, or the passage of time, the use of well-ranked observers to confirm their observations will assist in increasing their rank.

In the TruSat roadmap, several of these use case may be “upgraded” with the use of source image data from the observation, allowing for third-party or automated confirmation of user observation analyses, and faster escalation of object confidence, or more specific diagnosis of opportunities for improved accuracy in the observations.

Details of the Object Confidence algorithm are being finalized for the 0.1release of the PofSat engine, and will be fully detailed in the source code in the TruSat software repository and in accompanying documentation.

## III.C. Mitigating Attack Vectors

As a decentralized, automated system, the PofSat engine must protect itself against attack vectors ranging from erroneous observations from naïve or inexperienced users to malicious attempts to exploit the open and permission-less nature of the catalog in order to disrupt service, or to skew or corrupt the data.

The following are potential attack vectors, and mechanisms available in the system architecture to mitigate or neutralize these attacks on the TruSat catalog.

List of Attack Vectors currently contemplated:

- Single incorrect positive confirmation of a verified object
- Single falsified observation of an object
- Coordinated false reporting on an Object (Positive result)
- Coordinated false reporting on an Object (Negative result)
- Code injection attacks on server
- User Phishing or account take-over attacks
- DDOS attacks

### III.C.1.Single Incorrect (or Falsified) Observation of a Verified Object

Situation: A user “falsely reports” an observation. They could do so by making up an observation from scratch, or by submitting a modified version of an observation from another user or attempting to submit another user’s observation as their own.

Resolution: The TruSat engine fingerprints all observations on parameters that can uniquely identify observation parameters which directly affect the orbital estimate and would simply “reject” a duplicate observation. This is also protection against accidental re-submission by a user, or an attempt to increase the weight of an observation by submitting it multiple times. The TruSat engine performs a similarly designed fingerprint check against externally-sourced TLEs, in order to prevent duplicate entries, and this feature could also be applied to audit submission of unauthorized 3rd party TLEs for which TruSat has been able to fingerprint the source files.

For observations that are not “identical” to observations already in the system, several checks are applied. For example: After the object is verified to exist in the catalog by NORAD number checks, it is then evaluated for a “nearness” check to the most-recently predicted orbit position for that observation. This check evaluates the fit on location (time across the trajectory), cross-track error, and if multiple observations are available, angular rate. An object in the right location, moving at a plausible rate would fail this test if its direction of travel diverged beyond a threshold. Similarly, if an object is headed in the correct direction, but moving outside a threshold of angular velocity, or deviating too far from its along-track location, the observation would not be correlated with the catalog object on file.

Options from this point would be to simply discard the object, flag the user in an appropriate way, or potentially, put the object into a flow for evaluation as an independent, new object. A demotion of the user rank for observation errors (wrong object specified, observation otherwise flawed) would disincentivize submitting flawed data.

In the TruSatroadmap, incorporation of user-submitted raw-data would help provide more option paths for an object which does not plausibly-map to an existing catalog object; although, then defense against “deep fake observations” would need to be developed.

### III.C.2.Single Falsified Observation of a New Object

Situation: A TruSat user “falsely reports” an observation. They could do so by making up an observation from scratch or by submitting an existing observation but change the object number they are reporting against.

This could be from malicious intent (intent to poison data) or a user who is reporting an observation with no correlation to reality, or arbitrary correlation to the expected result.

Resolution: As previously described, a user who attempts to submit an object which may correlate to a different object would have the system rejecting the observation due to its lack of plausible correlation. For a user reporting a “new object” several mitigating actions are available:

- **A)** The object is entered into the catalog with a “(1) Neutral” confidence and flagged per-usual for follow-up.
- **B)** Submission of “new” objects could be restricted to autonomously high-ranked users, or further restricted to users which have passed TruSat community KYC verifications. In this case, the object could be entered into the catalog with an “(0) Untrusted” Object Confidence, but still available for followup -with the designation implying a note of warning to those performing followup.

In either of these cases, well-meaning observers would be unable to verify this object, and their attempts could be logged in the system as “not seen” data points, which could be applied to demote the object’s confidence.

Ill-meaning users could provide follow-up “fake” confirmations, but lacking an independent well-ranked user’s positive confirmation, the object would never escalate above the “(3) Verified” object confidence, and a certain threshold of “not seen” observation could prevent it from reaching this status.

If an Ill-meaning user were to make a number of valid observations of catalog objects for the purpose of gaining enough rank in the system to submit observations for “fake” objects, then they have provided value to the system in the process of doing so. In this case, the positive increments on rank could be offset by significantly larger consequences for rank detriment which would prevent this from happening at a large scale. Limitations on the number of objects a user could verify per time-increment could also be applied to rate-limit this adverse effects. Similar considerations for “51% attacks” in blockchain networks contemplate the value-add that is provided by needing to substantially and positively contribute to the system infrastructure before one gains the capability to “attack it” and then have a rational interest against a self-attack.

Here too, using TruSat’s anticipated roadmap capability of submitting photographic evidence of the observation could increase the challenge of falsifying observations, while increasing the need to protect against falsified image records.

As mentioned previously, geographic diversity and KYC checks on origin or faction could provide unrelated limits to the reach of these nefarious activities.

### III.C.3.Coordinated False Reporting on an Object (Positive)

Situation: Extending the case in I.D.3.b to a coordinated effort by multiple users to create a record for an object which does not exist, multiple TruSat users submit self-consistent observations for a fictitious object, or alternatively, self-consistent observations for an existing object in an attempt to skew TruSat’s estimate of its orbit.

Resolution: Here again, as described in the previous case, the low rank of the ill-intended TruSat users would prevent a new object from achieving an Object Confidence greater than “(2) Unverified”. If one ormore of them made TruSat contributions in order to achieve rank, their benefit to the system may ultimately outweigh their detrimental (temporary) effects on the system.

A more insidious case is with an attempt to skew the orbit knowledge of an existing object (a known military satellite operated by a dictator regime) by exploiting the open source nature of the project, and estimating the type of observation necessary to (a) pass the correlation and plausibility tests, but (b) result in the observation being worse than would be possible with genuine/accurate data.

Here, the user rank of these nefarious users would have low weight along-side the higher weight observations from well-established users, and the nefarious observations would get successively demoted in user-rank to a weight of zero. This “arms race” could be kept up with perpetual new accounts being established, and perpetual skewed observations being provided, but these patterns may start to present themselves in detectable ways.

Here again, supplying source observation data in image format would increase the difficulty in achieving a “fake.”

### III.C.4. Coordinated False Reporting on an Object (Negative)

Situation: This case concerns itself with a ill-intended TruSat user trying to achieve an object being “demoted” from the catalog by submitting poor or negative observation records.

Resolution: In addition to the normal feedback loop from sourcing user rank in the promotion or demotion of object confidence, in this case, any positive confirmation by a well-ranking positive-intent user would quickly re-introduce the demoted object into the catalog. Communications and coordination by the community and these positive representatives in the community could highlight the object as a priority observation target, and the system design could continue to keep the object in the catalog.

### III.C.5 Code injection attacks on server

Situation: Leveraging the open-source repositories of the TruSat project, the user infiltrates the operating code and incorporates their malicious version in the operating PofSat engine.

Resolution: The approved/validated code-base would be file-checksummed and logged on the Ethereum blockchain, and would immediately fail a consistency check. The system would automatically roll back to the validated release, or shutdown and notify TruSat Partners to intervene.

As we implement the TruSat roadmap, vulnerability to this type of attack will decrease, as it will become more decentralized, and the attacks would need to take place on a large fraction of the nodes in the system.

### III.C.6. User Phishing or account take-over attacks

Situation: Someone with ill-intent attempts to acquire access to a well-ranked user in order to achieve actions only possible with higher-ranking users.

Resolution: The implementation of public/private key cryptography, and the security provided by an Ethereum-wallet for TruSat access make this type of attack increasingly more challenging to achieve. Even if an ill-intended individual were able to obtain access to one or more wallets through a vulnerability, their ability to implement sustained detrimental actions would be mitigated by the safeguards already discussed.

To obtain the private keys of the user, the attacker would need to perform an attack that can access user’s local storage, gain access to their email and password, or perform a standard phishing attack. To guard against unauthorized access to local storage, users will be encouraged to switch their account management to Metamask. Finally, a phishing attack can be performed by tricking a user that they are in a safe environment when providing their credentials, this can be addressed by using a unique identifier that the user can check against in order to verify they are safe. Once switched to an established, trusted, environment such as a phone application or decentralized platform, this should no longer be a concern. All the key management will be performed by the user and their device without exposing anything externally.

### III.C.7. DDOS attacks

Situation: Ill-intended parties attempt to deny availability of the TruSat service by overwhelming its servers.

Resolution: In the initial release, which relies on Web 2 services, this exists as a vulnerability. Upon transitioning more fully into an Ethereum mainnet solution later in our roadmap, TruSat looks to decentralize the catalog itself, as well as the server processes which interact and add data to the system.

## III.D. Data Inputs and Outputs

With its v0.1 release, TruSat will securely store visual position observations, which are fed into the Proof of Satellite engine to generate satellite ephemeris, to be distributed in the two-line element (“TLE”) format. To support the workflow, the catalog will also contain basic contextual information retrieved from public sources <small>7</small> as well as information required to uniquely identify user accounts, their observation locations, and user performance data to support the automated generation of satellite ephemeris from updated observations.

In its initial release, TruSat will accept observations in IOD, UK or RDE Positional Observation reporting formats <small>8</small>, although the “COSPARsite” identifying the user observation location in these records will still need to be coordinated through the Seesat-L mailing list until alternative standards can be vetted and established.

Early in our post-initial-release roadmap we anticipate being able to accept TLEs from satellite operators and operator derived state vectors with associated documentation on coordinate frame and time reference. Should the experiment of TruSat be successful, we anticipate being able to expand observations to includeradio-doppler measurements such as those made by the SatNOGS <small>9</small> network.

Future releases may place greater weight on observations that are accompanied with their raw observation data, to allow third-party verification of the observation result. Other developments in the roadmap are anticipated to enable basic information about the object’s optical properties, including visual magnitude, and related measurements. Additionally, an active community of radio-frequency observers of satellite may provide for additional opportunities to verify satellite orbits, provide data about their RF emissions, or provide insight into objects which cannot be visually measured.

TruSat will not pull data direction from Space-Track.org or any other source that imposes restrictions on use of the data.

Predictions in the catalog will be represented in Two Line Element (TLE) <small>10</small> sets, the defacto standard by which the parameters describing a satellite orbit can be shared. The format, originally developed during the punch-cardera of computing, is a fixed-field, fixed width partially encoded format for storage efficiency, and has been produced by NORAD for most objects since its establishment. A TLE can be used by the SGP family of orbit propagators to provide reasonably accurate position and velocity of a satellite for a given time. As a TLE is an approximation of the orbit, they are designed to be most accurate near an “epoch” (akin to a manufacture date), and become progressively less reliable the farther away from this date the estimate is used, owing to atmospheric effects, gravitational and other small perturbation, and the approximations of the SGP model itself.

Because of their ubiquitous use, TruSat project will produce predictions in compliance with this standard, and be prepared to follow, and potentially lead in efforts to modernize the format and its use.

## III.E. Tuning the Proof of Satellite Engine

For visual position observations, TruSatis building on the 25 years of publicly available work from the all-volunteer SeeSat Visual Satellite Observer organization <small>11</small>. The SeeSat website contains extensive information about the hobby of visual satellite observation, including techniques for finding faint objects, making positional observations, as well as characterizing the visual brightness and time-varying visual properties. The SeeSat community is notable for distributing TLEs for satellites which are not available in the public US STRATCOM satellite catalog, typically classified satellites, operated by the United States and its allies.

The archive of SeeSat data supplied a rich source of data to “train” and tune the Proof of Satellite engine ahead of its initial release. For 25 years, SeeSatusers have distributed their visual position observations in one of three machine-readable positional observation reporting formats. <small>12</small> The ConsenSys Space team has recovered and organized nearly 400,000 individual observations contributed by this community since December, 1998. Each of the observation data points include information about the apparent sky-location of a known satellite, and the time the observation was made. Additionally, reference information is available about the observer, their location, and the ability to describe observing conditions and the estimated accuracy of the measurement.

This data corpus was an invaluable resource in testing algorithms to support the Proof of Satellite engine, as well as explore UI/UX features to support and grow the community making these observations. Starting TruSat with a “25 year history” of user performance is also a benefit which we hope can continue to serve the Seesat community.

In our initial release, TruSat and its technical advisors will be making choices about the specific algorithm implementations, but we hope that by the 3rd major release of the system, we will be able to transition to a decentralized governance system of the algorithm modules.

ConsenSys Space will continue to tune the Proof of Satellite engine following the initial release, and will make all algorithms publicly available.

## III.F. Open Source Algorithm Updates

TruSatis being architected and implemented in an open and modular way. We anticipate that there are likely “better” ways to achieve each portion of the TruSat engine than we are initially implementing, and there will likely be innovations realized by innovators and contributors throughout the world over time. In addition to supplying data to TruSat, we anticipate the possibility of network users/members to supply “pull requests” for engine algorithm updates. This could be as small as a suggested tuning of a variable, to as complex as a complete rewrite of a particular part of the process.

We hope that the system can allow for the open dataset and open source to be used to demonstrate to the community how their proposed change can improve the system, by demonstrating the potential result on actual data from the system. Furthermore, we anticipate that these types of “upgrades” would be high-value contributions worth of “bounties” that are conceived of the system, allowing individuals or organizations to derive benefits and incentives from the system in ways other than by providing observations.

We anticipate the first opportunity to implement options such as these would present themselves in the second stage of our roadmap, when we are transitioning on EthereumMainNet, and can take advantage of the security of the “store of value” functionality provided by Ethereum.

## III.G. Identity and Privacy

Privacy by default is a core design choice made in architecting the TruSat software. In the default settings, an Ethereum address and some observation history data will be the only information about a contributor viewable by other users of the System. Contributors will have the option to reveal more information, including their username and location (e.g., “India” or “San Francisco, USA”) , as well as the option to remove their identity and observation contributions entirely from the network.

To account for a satellite observation, the Proof of Satellite engine must first verify the contributors ownership of an ethereum address, then process the a high-resolution (meters level) position of location from which the observation was made. TruSat utilizes the same public key cryptography used to verify ownership and control of cryptocurrency to verify ownership and control of an observer identity. If an individual wishes to use a different Ethereum address for every contribution or instead to “persist” the same address over time, they will have the option to do so. Using different addresses is likely to result in their observations having less influence on the catalog contents than if they were to choose a persistent identity. These design choices are in step with the long-term goal for the network to be fully decentralized. Ethereum wallets will be a key component of those future plans and early adopters of TruSat will be able to take their first steps toward that end by starting with a more self-sovereign identity.


<small>1. Over time we may expect the space economy to provide an additional perturbation in this list - in the form of “satellite servicing” vehicles, or “another satellite” which would probably exist between #1 and #2 in importance. The Space Shuttle, and the Russian Soyuz and Progress modules have contributed to the reboosting of the MIR Space Station, the International Space Station, and other satellites, such as the Hubble Space Telescope, so far in the history of space exploration.</small>

<small>2. https://www.celestrak.com/publications/AIAA/2006-6753/</small>

<small>3. https://www.universetoday.com/93764/roboscopes-real-armchair-astronomy/</small>

<small>4. https://ipfs.io/</small>

<small>5. https://github.com/cbassa/sattools</small>

<small>6. https://github.com/cbassa/stvid</small>

<small>7. Celestrak.com Satellite Catalog (SATCAT) https://www.celestrak.com/satcat/satcat-format.php and the Union of Concerned Scientists (UCS) Satellite Database https://www.ucsusa.org/nuclear-weapons/space-weapons/satellite- database.</small>

<small>8. http://www.satobs.org/position/posn_formats.html</small>

<small>9. Open Source global network of satellite ground-stations https://satnogs.org/</small>

<small>10. https://en.wikipedia.org/wiki/Two-line_element_set</small>

<small>11. SeeSat Website: http://www.satobs.org/</small>

<small>12. http://www.satobs.org/position/posn_formats.html</small>