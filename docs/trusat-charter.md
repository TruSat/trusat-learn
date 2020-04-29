---
id: governance
title: TruSat Charter 
sidebar_label: Governance (TruSat Charter)
---
Epoch 2.0
## Introduction

TruSat is an open source, citizen-powered system for creating an independent record of satellite orbits in service of the long-term sustainability of outer space activities.  TruSat is developed and maintained by a global open source community of volunteers.  In addition to developing the TruSat Software, this global community of contributors:

- Chart the future of TruSat;
- Make and report satellite observations;
- Design hardware and software tools to make satellite observation more accessible; and
- Author documentation and other content that enable participation by a diverse range of contributors, and  translate them into multiple languages.

The TruSat Charter governs how TruSat’s open source community makes decisions, from strategic decisions about the direction of the project to the review and acceptance of contributions.  TruSat is a meritocratic, consensus-based community project. Anyone with an interest in the project can join the community, contribute to the project design and participate in the decision making process. This Charter describes how that participation takes place and how to set about earning merit within the project community.  The governance provisions are based upon the [OSS Watch meritocratic governance model](http://oss-watch.ac.uk/resources/meritocraticgovernancevoting), under [Creative Commons License: Attribution Share Alike 3.0](https://creativecommons.org/licenses/by-sa/3.0/us/).

This Epoch 2.0 iteration of the TruSat Charter marks a transition from a project managed by ConsenSys Space to a decentralized project managed by its volunteer contributors.  ([See Project History](trusat-project-history.md)).  The Charter will be continuously revised as the community learns and grows.

## Quick Reference

- **[The TruSat Guiding Principles](trusat-charter#section-1-trusat-guiding-principles)**: the twin aims of the project—developing tools to preserve the long-term sustainability of spaceflight, and creating opportunities for direct participation in space endeavors—and the principles that guide the community in pursuing these aims. 

- **[Roles and Responsibilities](trusat-charter#section-2--roles-and-responsibilities)**: TruSat is governed by its global community of Contributors, who supply the ideas and labor to maintain and improve TruSat.  All Contributors have a voice in decisions, and decisions are taken by consensus to the extent practicable.  Some Contributors take on additional project management responsibilities or earn Committer status, by virtue of a sustained record of excellent contributions.  

    Accordingly, the community utilizes a streamlined review process for contributions from Committers.   

    - **Contributors:** Community members who contribute in concrete ways to the project. Anyone can become a contributor, and contributions can take many forms, from software development, to writing and translating documentation, to observing satellites in the night sky. Ready to become a Contributor? Follow [this link](https://discord.gg/E2Hc9v) to join the TruSat Community in the Discord messaging app and introduce yourself in the #new-contributors channel.
    - **Committer:**  Committers are Contributors trusted with a streamlined contribution review process and binding votes by virtue of their demonstrated familiarity with and commitment to the project.
    - **Project Management Committee (PMC):** The project management committee has additional responsibilities to ensure the smooth running of the project. PMC members are expected to review code contributions, participate in strategic planning, approve changes to the governance model and manage the copyrights within the project outputs.
    - **PMC Chair:** The PMC Chair is the elected facilitator responsible for ensuring project governance in accordance with this Charter.

- **[Planning, Coordination & Approval](trusat-charter#section-3-planning-coordination--approval)**:  In general, Contributors are invited to build whatever they believe would enhance TruSat, with only such community review and approval as necessary to preserve the trust of TruSat users (whether data providers or end users).  
    - The simplest path to contribution is to work on an open Issue, which can be found in the “To Do” column of the TruSat Project in GitHub.  Issues are tasks the community has already prioritized, and the Project view in GitHub integrates open Issues across all of the TruSat repositories.  

    - Have a vision for something beyond the current open Issues? Fantastic! The [TruSat Roadmap](roadmap.md), which sets forth the functionality and programs the community aspires to develop in the long run, is a good place to begin.  Many important items in the Roadmap haven’t yet been prioritized as issues because the community has not yet had Contributors with the expertise and inclination to build them.  But don’t feel limited to the Roadmap; the community has not thought of everything.

    - If you have an idea for a new feature or initiative and you’re willing to lead its creation, make a Proposal by creating a new issue in the appropriate TruSat repository on GitHub with [Proposal] in the title (example: [Proposal]: creating educational materials for teachers). You may find collaborators through the community discussion that follows. [(See Section 3)](trusat-charter#section-3-planning-coordination--approval).

    - If you have an idea for a new feature or initiative that you’re not in a position to create, please share it in the Ideas thread of Discuss.TruSat.org.

- **[Discussion & Voting](trusat-charter#section-4-discussion-and-voting)**: Community review of Proposals generally operates according to “lazy consensus,” meaning that a Proposal is presumed to have the support of the community unless a concern is voiced within a specified time period (72 hours for most decisions).  The community endeavors to resolve concerns through discussion and revision, as appropriate.  Where a vote is needed ([see Section 4.D](trusat-charter#4d-when-is-a-vote-required)), all Contributors are invited to vote, but only the votes of Committers and PMC members are binding on the outcome.  As detailed in [Section 4.B](trusat-charter#4b-voting), it is the responsibility of Committers and PMC members to follow up on concerns expressed by other Contributors and weigh them in their votes. 

  Open Source License: Each component of the TruSat software is presently licensed under the [Apache V2.0 license](https://www.apache.org/licenses/LICENSE-2.0 ), and all contributions and submissions to TruSat shall be under the terms and conditions of this license.  In the future, the community may consider licensing components under different open source licenses to the extent necessary to integrate open source software elements licensed under more restrictive licenses.   



## Section 1: TruSat Guiding Principles

**A. Space Sustainability Mission**:  TruSat exists to promote the long-term sustainability of outer space activities.  At present, this takes the form of creating a trusted record of satellite orbits suitable for assessing satellite operations against emerging best practices and standards for responsible orbital operations.    

**B. Openness**: TruSat is an open-sensor system in that any person or entity may contribute satellite observation data without permission.  The resulting orbital position data should be publicly available and freely accessible without restriction.  

**C. Transparency**: The TruSat System is transparent in that the algorithms for processing satellite observations into an orbit prediction are freely accessible (e.g,. source code in the TruSat software repos, narrative explanation in White Paper).  TruSat Community governance will remain transparent by publishing the governance arrangements in effect in the TruSat Charter, accessible at TruSat.org.

**D. Open Source licensing**: The TruSat Software is made available under [open source licenses](trusat-charter#5a--trusat-software-and-documentation-licensed-under-apache-v20).  All Contributions must be compliant with [the applicable open source license](trusat-charter#5b-all-contributions-to-trusat-shall-be-made-under-apache-v20-license).  Other projects are invited and encouraged to utilize TruSat code consistent with the applicable license terms. 

**E. Democratizing and Diversifying Space Endeavors**: The community strives to create new opportunities for global public participation in space endeavors, and reduce barriers to participation, by developing software, hardware, and documentation that makes satellite tracking as accessible to as many people as possible.  A globally diverse community of citizen satellite trackers is both a means to making TruSat and its outputs more robust and reliable, and also an end that motivates the community.


## Section 2:  Roles and Responsibilities
### 2.A. Contributors
Contributors are community members who contribute in concrete ways to the project. Anyone can become a contributor, and contributions can take many forms. There is no expectation of commitment to the project, no specific skill requirements and no selection process. 

In addition to their actions as users, contributors may also find themselves doing one or more of the following:
 - supporting new users (existing users are often the best people to support new users)
 - reporting bugs
 - identifying requirements
 - providing graphics and web design
 - programming
 - assisting with project infrastructure
 - writing documentation
 - fixing bugs

As contributors gain experience and familiarity with the project and demonstrate their commitment, they may being nominated for committership.

### 2.B. Committers
Committers are community members who have shown that they are committed to the continued development of the project through ongoing engagement with the community. Committership allows contributors to more efficiently contribute to the project by shifting and streamlining community review of their contributions.   The key difference between a Committer and a contributor is when this approval is sought from the community. A Committer seeks approval after the contribution is made, rather than before.  Committers may also cast “binding” votes, as explained in [Section 4.B](trusat-charter#4b-voting).

Anyone can become a Committer; there are no special requirements, other than to have shown a willingness and ability to participate in the project as a team player. Typically, a potential committer will need to show that they have an understanding of the project, its objectives and its strategy. They will also have provided valuable contributions to the project over a period of time. New Committers can be nominated by any existing Committer. Once they have been nominated, there will be a vote by the Project Management Committee.  Commitership is a privilege, not a right. That privilege must be earned and once earned it can be removed by the PMC ([see Section 4.D](trusat-charter#4d-when-is-a-vote-required)) in extreme circumstances. However, under normal circumstances committership exists for as long as the committer wishes to continue engaging with the project.
A committer who shows an above-average level of contribution to the project, particularly with respect to its strategic direction and long-term health, may be nominated to become a member of the PMC. This role is described below.

### 2.C. Project Management Committee (PMC)
The Project Management Committee consists of Contributors with a demonstrated commitment and additional responsibilities for the smooth running of the project. PMC members are expected to review code and other contributions, participate in strategic planning, approve changes to the governance model and manage the copyrights within the project outputs.
Members of the PMC do not have significant authority over other members of the community, although it is the PMC that votes on new Committers. It also makes decisions when community consensus cannot be reached ([See Section 4](trusat-charter#section-4-discussion-and-voting)). In addition, the PMC utilizes a private Discord channel for sensitive issues, such as votes for new committers and legal matters that cannot be discussed in public. This private channel is not used for project management or planning.

Membership of the PMC is by invitation from the existing PMC members. A nomination will result in discussion and then a vote by the existing PMC members ([Section 4.D](trusat-charter#4d-when-is-a-vote-required))

### 2.D. PMC Chair
The PMC Chair is a single individual, voted for by the PMC members. Once someone has been appointed Chair, they remain in that role until they choose to retire, or the PMC casts a two-thirds majority vote to remove them. The PMC Chair has no additional authority over other members of the PMC: the role is one of coordinator and facilitator. The Chair is also expected to ensure that all governance processes are adhered to, and has the casting vote when the project fails to reach consensus.

## Section 3: Planning, Coordination & Approval

 In general, Contributors are invited to build whatever they believe would enhance TruSat, with only such community review and approval as necessary to preserve the trust of TruSat users (whether data providers or end users).  This section explains how work is prioritized, contributed, and reviewed.  

### 3.A. Contributions to Open Issues

The simplest path to contribution is to work on an open Issue, which can be found in the “To Do” column of the [TruSat Project in GitHub](https://github.com/orgs/TruSat/projects).  Issues are tasks the community has already prioritized, and the Project view in GitHub integrates open Issues across all of the TruSat repositories.  Contributors may submit their work on an Issue for community review and integration by opening a pull request in GitHub (see documentation in the [TruSat GitHub](https://github.com/TruSat/trusat-frontend) for instructions on pull requests, and the review process for Committers).

This section references the three primary communications tools utilized by the TruSat Community:
- [TruSat Project in GitHub]((https://github.com/orgs/TruSat/projects)), which shows the status of near-term priorities (in the form of Issues), and supports discussion specific to Issues.
- [Discuss.TruSat.org](https://discuss.trusat.org/), which serves as the general community forum for everything from sharing tips on satellite observations to ideas for new features and uses of TruSat.
The [TruSat Discord](https://discord.gg/9f98pAA) messaging app, used for collaboration.  

### 3.B. Ideas and Proposals for New Areas of Work
TruSat welcomes ideas and proposals for work beyond the current open Issues? The [TruSat Roadmap](roadmap.md), which sets forth the functionality and programs the community aspires to develop in the long run, is a good place to begin.  Many important items in the Roadmap haven’t yet been prioritized as issues because the community has not yet had Contributors with the expertise and inclination to build them.  But don’t feel limited to the Roadmap; the community has not thought of everything.
### 3.B.1. Proposals
If you have an idea for a new feature or initiative and you’re willing to lead its creation, make a Proposal by creating a new issue in the appropriate TruSat repository on GitHub with **[Proposal]** in the title (example: **[Proposal]**: creating educational materials for teachers).  You may find collaborators through the community discussion that follows. ([See section 4](trusat-charter#section-4-discussion-and-voting)).
### 3.B.2. Ideas
If you have an idea for a new feature or initiative that you’re not in a position to create, please share it in the Ideas thread of [Discuss.TruSat.org](https://discuss.trusat.org/).  If community members wish to implement the idea in the near term, it may turn into a Proposal.  If the community likes the idea but is not in a position to implement it in the near term, it may be added to the Roadmap.

## Section 4: Discussion and Voting

Decisions about the future of the project are made through discussion with all members of the community, from the newest user to the most experienced PMC member. All non-sensitive project management discussion takes place in [Discuss.TruSat.org](https://discuss.trusat.org/).  In order to ensure that the project is not bogged down by endless discussion and continual voting, the project operates a policy of lazy consensus: proposals are considered to have the acceptance of the community if no concerns are expressed within a specified period. This allows the majority of decisions to be made without resorting to a formal vote.

### 4.A. Lazy consensus
Decision making typically involves the following steps:
- Proposal
- Discussion
- Vote (if consensus is not reached through discussion)
- Decision

For lazy consensus to be effective, it is necessary to allow at least 72 hours before assuming that there are no objections to the proposal. This requirement ensures that everyone is given enough time to read, digest and respond to the proposal. This time period is chosen so as to be as inclusive as possible of all participants, regardless of their location and time commitments.

Not all decisions can be made using lazy consensus. Issues such as those affecting the strategic direction or legal standing of the project must gain explicit approval in the form of a vote. Every member of the community is encouraged to express their opinions in all discussion and all votes. However, only project Committers and PMC members have binding votes for the purposes of decision making..

### 4.B. Voting
If a formal vote on a proposal is called (signaled simply by a PMC member creating a thread in Discuss.TruSat.org  with ‘**[VOTE]**’ in the subject line), all Contributors may express an opinion and vote. They do this by replying to the thread with the following vote and information:
- +1 ‘yes’, ‘agree’: also willing to help bring about the proposed action
- +0 ‘yes’, ‘agree’: not willing or able to help bring about the proposed action
- -0 ‘no’, ‘disagree’: but will not oppose the action’s going forward
- -1 ‘no’, ‘disagree’: opposes the action’s going forward and must propose an alternative action to address the issue (or a justification for not addressing the issue)

To abstain from the vote, participants simply do not respond to the email. However, it can be more helpful to cast a ‘+0’ or ‘-0’ than to abstain, since this allows the team to gauge the general feeling of the community if the proposal should be controversial.

Every member of the community, from interested user to the most active developer, has a vote. The project encourages all members to express their opinions in all discussion and all votes.
However, only Committers and PMC members have binding votes for the purposes of decision making.  It is therefore the responsibility of Committers and PMC members to ensure that the opinions of all community members are considered.  While not all Contributors may have a binding vote, a well-justified ‘-1’ from a non-committer must be considered by the community, and if appropriate, supported by a binding ‘-1’.

A ‘-1’ can also indicate a veto, depending on the type of vote and who is using it. Someone without a binding vote cannot veto a proposal, so in their case a -1 would simply indicate an objection.

When a vote receives a ‘-1’, it is the responsibility of the community as a whole to address the objection. Such discussion will continue until the objection is either rescinded, overruled (in the case of a non-binding veto) or the proposal itself is altered in order to achieve consensus (possibly by withdrawing it altogether). In the rare circumstance that consensus cannot be achieved, the PMC will decide the forward course of action.

In summary:
- Those who don’t agree with the proposal and think they have a better idea should vote -1 and defend their counter-proposal.
- Those who don’t agree but don’t have a better idea should vote -0.
- Those who agree but will not actively assist in implementing the proposal should vote +0.
- Those who agree and will actively assist in implementing the proposal should vote +1.

### 4.C. Types Of Approval
Different actions require different types of approval, ranging from lazy consensus to a majority decision by the PMC. These are summarized in the table below. The section after the table describes which type of approval should be used in common situations.

| **Type** | **Description** | **Duration** |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
| Lazy consensus | An action with lazy consensus is implicitly allowed, unless a binding -1 vote is received.  Depending on the type of action, a vote will then be called.  Note that even though a binding -1 is required to prevent the action, all community members are encouraged to cast a -1 vote with supporting argument.  Committers are expected to evaluate the argument and, if necessary, support it with a binding -1. | N/A |
| Lazy majority | A lazy majority vote requires more binding +1 votes than binding -1 votes. | 72 hours |
| Consensus approval | Consensus approval requires three binding +1 votes and no binding -1 votes. | 72 hours |
| Unanimous consensus | All of the binding votes that are cast are to be +1 and there can be no binding vetoes (-1). | 120 hours |
| 2/3 majority | Some strategic actions require a 2/3 majority of PMC members; in addition, 2/3 of the binding votes cast must be +1.  Such actions typically affect the foundation of the project (e.g. adopting a new codebase to replace an existing product). | 120 hours |

### 4.D. When Is A Vote Required?
Every effort is made to allow the majority of decisions to be taken through lazy consensus. That is, simply stating one’s intentions is assumed to be enough to proceed, unless an objection is raised. However, some activities require a more formal approval process in order to ensure fully transparent decision making. The table below describes some of the actions that will require a vote. It also identifies which type of vote should be called.

| **Action** | **Description** | **Approval Type** |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
| Release plan | Defines the timetable and actions for a release. A release plan cannot be vetoed (hence lazy majority). | Lazy majority |
| Product release | When a release of one of the project’s products is ready, a vote is required to accept the release as an official release of the project. A release cannot be vetoed (hence lazy majority). | Lazy majority |
| New committer | A new committer has been proposed. | Consensus approval of the PMC |
| New PMC member | A new PMC member has been proposed. | Consensus approval of the community |
| Committer removal | When removal of commit privileges is sought. | Unanimous consensus of the PMC |
| PMC member removal | When removal of PMC membership is sought. | Unanimous consensus of the community |

## Section 5: Open Source Licenses

### 5.A  TruSat Software and Documentation Licensed under Apache V2.0 
Each component of the TruSat software and documentation are presently licensed under the [Apache V2.0 license](https://www.apache.org/licenses/LICENSE-2.0 ) (the “License”).

### 5.B All Contributions to TruSat Shall be Made Under Apache V2.0 License.
In accordance with Section 5 of the License, any contribution intentionally submitted for inclusion in TruSat shall be under the terms and conditions of the License, without additional terms or conditions.

### 5.C Other Open Source Licenses
In the future, the community may consider licensing components under different open source licenses to the extent necessary to integrate open source software elements licensed under more restrictive licenses.   




