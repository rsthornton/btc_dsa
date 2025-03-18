
# A Deep Systems Analysis of Bitcoin

## Shingai Thornton

## Binghamton University

## March 17, 2025

## 1 Introduction

The Bitcoin network consumes more energy than many nations, boasts a market
capitalization of$2 trillion, and has spawned an entire industry of blockchain
technology along with a new academic field of cryptoeconomics. Yet, after fif-
teen years of operation, there are still fundamental questions being asked about
the mysterious technology. What is it? What does it do? Can it provide any real
value to society? Economists debate whether it is a purely speculative bubble or
digital gold as computer scientists focus on its novel technical properties while
trying to improve its scalability, security, flexibility, and privacy. Policymak-
ers scrambling to construct new laws and regulatory frameworks argue about
whether it is a bastion of financial innovation and freedom to be embraced, or
a threat to financial stability that must be controlled or eradicated.

While these domain specific perspectives are valuable and necessary, they
only capture fragments of the whole story. Trying to understand Bitcoin within
these disciplinary boundaries leads to tensions that are impossible to resolve
when confined to the lens of a single scientific domain. Bitcoin has evolved far
beyond Satoshi Nakomoto’s original vision of peer-to-peer digital cash and now
operates as a complex adaptive system whose behavior emerges from countless
interactions between software, economic incentives, and human social dynamics.
Proper understanding of Bitcoin demands a holistic analytical approach capable
of bridging traditional disciplinary divides while preserving both technical rigor
and systemic insight.

## 2 Challenges in Cryptoeconomic Analysis

Bitcoin was described in an early systematic survey of challenges facing cryp-
tocurrencies as ”a rare case where practice appears to be ahead of theory” [1].
The technology was adopted by a sizable group of early enthusiasts as real
money long before mainstream economists had spent any time attempting to


develop theoretical frameworks for reasoning about the complex dynamics of
decentralized digital currency uncontrolled by any nation state. The authors
of the survey noted that some early Bitcoin adopters dismissed the need for
theoretical foundations, arguing that it demanded attention simply because ’it
worked’. Meanwhile many academics and security researchers hesitated to en-
gage with the technology because they saw the system as being dependent on
”an unknown combination of socioeconomic factors hopelessly intractable to
model.”

Today, Bitcoin receives an abundance of attention from researchers. How-
ever, the academic community has yet to develop theoretical frameworks that
are broad, flexible, and rigorous enough to account for all of its many dimen-
sions – social, economic, and technical. Given the increasing levels of retail,
institutional, and governmental adoption of Bitcoin, this isn’t just a theoretical
problem—lack of understanding has practical consequences. Space Force offi-
cer and astronautical engineer Jason Lowery warns that over-reliance on purely
economic frameworks creates systemic analytical bias that could impact pol-
icy decisions and even national security [2]. Loweries’ novel Power Projection
Theory highlights the way Bitcoin uses physical power in the form of energy to
secure information in cyberspace, producing a compelling systemic perspective
which frames Bitcoin as a form of ”softwar”, a new means of projecting real
power into the virtual world. This unique framing of Bitcoin as a new form
of electro-cyber power projection technology invokes theories of energy-backed
money developed by Henry Ford and Nikola Tesla in the early 20th century.
Cryptoeconomic researchers who embrace the methods of complex adaptive
systems and systems engineering argue that proper analysis of cryptoeconomic
systems must span multiple disciplines: from systems engineering and computer
science to economics, political science, and ethics [3]. A unified approach to un-
derstanding cryptoeconomic systems requires treating them as complex socioe-
conomic networks defined by individual autonomous actors acting at the micro
level, economic policies embedded in software offering coordination at the meso
level, and macro-level emergent properties arising from the interactions between
these systems within the network. The structure and dynamics of blockchain
networks can not be properly understood without an explicitly interdisciplinary
perspective.
The need for deep understanding is a very practical concern in light mounting
evidence which supports their assertion that blockchain networks are ”mission-
critical and safety-critical regulatory infrastructure for autonomous agents in
untrusted economic networks.” In addition to humans, there has been a recent
surge in AI agents interacting with blockchains (Ante, 2025). As AI agents
start to interact with humanity’s economic systems in meaningful ways at scale
using blockchains, it will be even more important to develop tools for reason-
ing systemically about blockchains because those interactions are likely to have
substantial unpredictable and emergent impacts.

```
A key challenge facing interdisciplinary teams who seek to analyze and design
```

```
Figure 1: Caption
```
these systems in a scientific manner is hampered by the lack of a common lan-
guage to facilitate communication among specialists who are constrained in their
capacity to coordinate due to varying disciplinary jargon. Effectively bridging
disciplinary divides requires more than just collecting different viewpoints—it
demands developing such a common analytical language or a ”Rosetta Stone”
to bridge disciplinary divides.

## 3 Systems Approaches in Cryptoeconomics

The language of systems is well-suited to support the work of interdisiplinary
research teams. Systems science, though still in its formative stages and some-
what fragmented [4], provides theoretical frameworks and methodologies for de-
scribing general properties and principles found in systems across all scientific
domains [5]. Borne from the General System Theory movement that emerged
after World War II, as scientists who experienced the power of interdisciplinary
collaboration during wartime sought to formalize systems approaches during
peacetime, systems science offers valuable tools for cryptoeconomic analysis.
This section introduces three discipline-agnostic systems methods that have
been successfully applied in cryptoeconomic research: agent-based modeling
(ABM), system dynamics (SD), and network analysis ([6].

To support this analysis, computational implementations of both the agent-based model and system dynamics approaches have been developed. These simulations, available as open-source code on GitHub[^simulations], provide empirical validation of key concepts discussed in this paper. While the detailed implementation is beyond the scope of this paper, the simulations demonstrate how these theoretical approaches can be operationalized to explore Bitcoin's complex dynamics.

[^simulations]: https://github.com/user/BTC_DSA/simulations

### 3.1 Agent-Based Modeling

Agent-based modeling is a ”bottom-up” approach to building computer simu-
lations of complex systems. Individual agents are programmed to follow simple
behavioral rules, and complex dynamics emerge from their interactions. ABMs
have proven useful for reasoning about system-wide emergent properties that
arise from micro-level interactions, especially in situations where controlled ex-
perimentation isn’t possible, as is the case in most societal systems.


```
Figure 2: Caption
```
```
Figure 3: Caption
```
Researchers at the U.S. Argonne National Laboratory developed a gener-
alized ABM framework for modeling blockchain systems [7]. Their model de-
scribes and simulates the interactions between market agents making transac-
tions, miner agents selecting and verifying transaction blocks, and the decen-
tralized ledger of transactions. Their results illustrate how ABMs can formally
describe essential elements of blockchain functioning while providing insights
about the relationship between mining activities and energy efficiency.

A team at Protocol Labs demonstrated how ABMs can support blockchain
economy design through simulations of the Filecoin decentralized storage system
that incorporate real-world statistical data via back-testing [8][9]. Similarly,
Ethereum Foundation researchers used an ABM to study Ethereum’s proof-of-
stake consensus protocol after its historical switch from proof-of-work, helping
them reason about how initial conditions affect consensus quality and identify
specific attack vector research directions [10].

### 3.2 System Dynamics

System dynamics modeling is a ”top-down” approach to building computer sim-
ulations. Rather than starting with individual agents, the modeler begins with a
macrolevel conceptual model of relationships between system parts. The SD ap-
proach is useful for modeling systems described through quantities that change
over time. SD models excel at exploring expected outcomes in various scenar-
ios, evaluating proposed interventions, and anticipating potential negative side
effects.

One SD model aims to holistically describe Bitcoin’s supply and demand
dynamics [11] Motivated by Bitcoin’s explosive growth, the model captures var-


```
Figure 4: Caption
```
ious feedback loops and connects them to decisions made by different actor
types (chartists, fundamentalists, and transactors) based on cost-benefit analy-
ses. Calibrated to historical data, the model helps to explain Bitcoin’s historical
trajectory and informs future projections.
Another effort explored drivers of growth in bitcoin mining power and tested
the hypothesis that miners mine blocks for profit [12]. This model anticipated
that if Bitcoin prices and transaction fees remained at then-current levels, the
Bitcoin network might see a decreased hashrate following the May 2020 halving
event, implying the network was approaching ”peak hash.”

### 3.3 Network Analysis

Network analysis is an ”in-between” method for examining relationship patterns
or structures among system parts. Unlike ABM and SD approaches, it is not
simulation-based but rather a means for formally describing complex system
organization. With roots in graph theory (established by Leonhard Euler in
1735), network analysis is one of the most well-established systems approaches
for studying blockchains.

A pioneering data-driven exploration of Bitcoin used network analysis to
group Bitcoin addresses into ”super clusters” associated with distinct business
categories [13]. After clustering, researchers created a network map showing
payment relationships among categories and identifying unique transaction be-
haviors in each cluster. The analysis revealed Bitcoin’s economy had evolved
through three distinct phases: an early prototype phase with early adopters, a
growth stage populated by ”sin” enterprises (gambling, black markets), and a
maturation stage marked by progression toward ”legitimate” enterprises.

More recent network analysis through 2023 also identified three distinct evo-
lutionary periods with coherent network patterns: exploration, adaptation, and
maturity [14]). This research indicated high centralization and wealth inequal-
ity within Bitcoin’s network, suggesting potentially negative implications for
long-term sustainability.

```
Similar network analyses of Ethereum have revealed user preferences for
```

```
Figure 5: Caption
```
money transfers over smart contracts [15], classified different account types
based on transaction statistics and network structure [16], analyzed decentral-
ized application user behaviors [17], and identified network structures control-
ling evolutionary trajectories [18]. A comprehensive survey of graph approaches
provides an overview of methodologies and insights while suggesting promis-
ing research directions like multi-resolution visualization and machine learning
models to address data and model drift[19].

### 3.4 Synthesis

These cases demonstrate how systems-oriented methods help cryptoeconomic re-
searchers explore emergent properties arising from micro-level behavior (ABM),
causal relationships between macro-level variables (SD), and real-world orga-
nizational structures and dynamics (network analysis) in ways that integrate
social, economic, and technical perspectives.

To accelerate rigorous interdisciplinary systems research in cryptoeconomics,
two key issues must be addressed: accessibility and integration. These systems
methods remain largely inaccessible to non-technical specialists, with results
that aren’t widely interpretable or usable. Additionally, there’s a lack of tools
and methodologies allowing seamless integration of insights across approaches.
Ideally, researchers could shift between network, agent, and dynamical perspec-
tives within a unified analytical framework.

Recent advances in applied systems science offer promising directions for
addressing these challenges.

## 4 Deep Systems Analysis

Deep Systems Analysis (DSA) is a novel systems science method that provides
formal procedures for analyzing complex, adaptive, and evolvable systems while
bridging historical divides in systems science [20]. It synthesizes insights from


George Klir’s mathematically rigorous methods with Peter Checkland’s Soft
Systems Methodology, creating a unified framework that accommodates both
precision and the inherent uncertainty involved when dealing with human and
social complexity.

What distinguishes DSA is its intent to enforce structured, comprehensive
analysis before proceeding to modeling. By prioritizing deep understanding of
system structure, behaviors, and relationships, DSA creates a solid foundation
that makes subsequent modeling efforts—whether using agent-based modeling,
system dynamics, or network analysis—more coherent and reliable. This ap-
proach directly addresses the limitations of the methods discussed in the previ-
ous section by ensuring that models are built upon a thorough understanding
of the system rather than partial or discipline-specific perspectives.

DSA is grounded in a formal system ontology that provides a precise lan-
guage for describing systems across domains. This ”language of system” es-
tablishes a common vocabulary and syntax for representing entities, relation-
ships, and dynamics, enabling truly interdisciplinary analysis and communi-
cation. The ontological foundation ensures that analysts can represent both
technical components and social processes within the same framework.

```
The DSA process unfolds iteratively through three phases:
```
```
1.System Identification: Defining the system of interest, its purpose,
primary outputs, and boundaries
```
```
2.Environmental Analysis: Mapping key environmental entities, their
relationships with the system, and critical input/output flows
```
```
3.Recursive Decomposition: Breaking down the system into subsystems
and analyzing their interactions and interfaces
```
Following this process produces a comprehensive knowledge base spanning
raw data, graphical system maps, organizational hierarchies, and mathematical
models of system dynamics. The resulting analysis can be captured and visual-
ized using tools like BERT, an open-source software tool designed specifically for
DSA. This approach is particularly well-suited to Bitcoin, where essential prop-
erties like censorship resistance and decentralization emerge not from individual
components in isolation, but from their interactions. The following sections will
demonstrate how applying DSA to Bitcoin yields a holistic perspective while
maintaining analytical rigor.


```
Figure 6: Caption
```
## 5 DSA Phase #1 - System Identification

### 5.1 Purpose

The analysis process starts with identifying a system of interest (SOI) and de-
termining its purpose. Bitcoin, the SOI, was created to enable trustless digital
cash transactions secured through decentralized consensus. However, its emer-
gent role in the Global Financial System (GFS) has evolved far beyond simply
serving as p2p electronic cash—it now has multiple distinct and complemen-
tary functions. Individuals and corporations buy Bitcoin to act as a store of
value, or ”digital gold”. Nations leverage Bitcoin as a global settlement net-
work and neutral monetary infrastructure. Technologists view it as a general
purpose platform for building decentralized, open, and programmable digital
financial infrastructure. A systems perspective allows us to account for all of
these perspectives simultaneously.

### 5.2 Primary System Output

Systems are largely defined by their outputs; the things they work to produce
and maintain. Bitcoin’s primary product is the set of confirmed transactions
contained in blocks which make up the blockchain.

The confirmed transactions can be measured directly by hosting and inspect-
ing a local Bitcoin node, or by using a third party service designed specifically
to present blockchain data in a digestible manner. The flow of blocks can be
measured through various parameters.

```
Table 1: Confirmed Transactions Flow Parameters
Parameters Units of Measurement
Blocksize Megabyte (MB)
Transactions per block Transaction Count
Transaction Throughput Seconds
Total Value Transferred BTC
```

## 6 DSA Phase #2 - Environmental Analysis

The next step is to identify key entities in the environment that use the system’s
primary product output. Understanding the system’s purpose requires under-
standing what sort of agents receive its output and for what reasons. In the
case of Bitcoin, there are four well-defined types of users who require confirmed
transactions for different reasons. We can identify them based on their unique
patterns of activity using the methods of network science [13].

1. P2P Transactors: Focused on using Bitcoin as originally intended; to
    transfer digital value without relying on centralized intermediaries. These
    users primarily value Bitcoin’s censorship resistance and permissionless
    nature.
2. Investors: Primarily engaged in acquiring and storing Bitcoin to hold for
    the long term, treating it as a store of value and potential hedge against
    inflation. Their blockspace usage primarily consists of large value transfers
    to secure storage.
3. Traders: Mainly interested in exploiting fluctuations in the relative price
    of BTC to other currencies to create a profit. They generate consistent
    demand for blockspace through frequent transfers between exchanges and
    trading venues.
4. Developers: Use blockspace to store code or serve as inputs into sepa-
    rate blockchain systems, building unique applications and protocols. This
    includes time chain stamping and cross-chain bridge operations.

One key characteristic of the users operating in Bitcoin’s immediate envi-
ronment is that they play a dual role. They simultaneously act as sinks that
receive confirmed transactions and sources responsible for initiating transaction
requests. This creates a significant overlap between the set of users who demand
confirmed transactions and those who provide the key input of transaction re-
quests. Transaction requests can be measured through a few parameters.

```
Table 2: Transaction Requests Flow Parameters
Parameter Units of Measurement
Request acceptance rate Percentage
Total pending value BTC
Average transaction size Bytes
```
Another key input comes from contributors—a globally distributed group of
developers, researchers, and community members interested in improving how
Bitcoin functions. These contributors aggregate primarily on Github where they
coordinate improvements through several measurable channels:


1. Code contributions: Direct improvements to Bitcoin’s implementation
    through pull requests and code reviews in the reference client repository.
2. Testing and verification: Systematic testing of proposed changes, bug re-
    porting, and security auditing.
3. Documentation: Technical specifications, implementation guides, and user
    updates.
4. Bitcoin Improvement Proposals (BIPs): Formal protocol enhancement
    proposals that follow standardized processes for review and potential adop-
    tion.

The contribution flow is essential to Bitcoin’s ability to evolve while main-
taining stability. The process is deliberately conservative, with multiple stages
of peer review and testing before changes are accepted. This creates a measur-
able pipeline of improvements where contribution quality and consensus can be
tracked through metrics like pull request acceptance rates, review participation,
and testing coverage.

```
Table 3: Contributions Flow Parameters
Parameter Units of Measurement
Pull Request Rate PRs/Month
Code Merge Rate # of Accepted pull requests
BIP Submission Rate Proposals/month
Active Developers Unique contributors per month
```
Contributors interact with the system through well-defined interfaces that
enforce programming standards, documentation requirements, and testing pro-
tocols. This structured approach allows the decentralized development process
to be monitored and measured while preserving Bitcoin’s core properties.
In order to produce confirmed transactions, Bitcoin needs a constant input
of electricity. Its security model depends on a globally distributed network of
computers solving increasingly computational intensive puzzles, requiring a sig-
nificant flow of electricity to operate. While precise overall electricity usage
and internal energy flows between subsystems are complex and difficult to track
precisely, aggregate measurements enable analysis of Bitcoin’s energy-security
tradeoffs and broader environmental impact. They also provide essential metrics
for stakeholders interested in projecting future power requirements and evaluat-
ing network sustainability. Bitcoin’s energy consumption can be measured and
analyzed across several key dimensions using tools such as The University of
Cambridge’s Bitcoin Electricity Consumption Index [21].

### 6.1 Boundary Definition

Boundary definition can be one of the most difficult aspects of systems analysis,
especially when dealing with complex systems that blend human and techno-


```
Table 4: Electricity Flow Parameters
Parameter Units of Measurement Data Source
Daily power consumption TWh
Energy source mix Percentage
Geographic distribution Percentage
Energy efficiency J/hash
```
logical aspects. How do we delineate what is inside Bitcoin and what is out-
side? What, exactly, is Bitcoin?The DSA methodology guides analysts to define
boundaries by specifying what subsystems are responsible for managing inter-
actions with the environment. Since Bitcoin has been defined as a system that
produces blocks of confirmed transactions, the interfaces are subsystems that
manage flows between internal Bitcoin processes and external entities. Five key
interfaces manage Bitcoin’s boundary interactions, handling three input flows
and two output flows:

1. Input Interfaces:
2. Software Wallet: Manages incoming transaction requests from users, val-
    idating format and propagating valid requests to internal processing sys-
    tems.
3. Web Browser: Controls how external contributions of code, documenta-
    tion, and protocol improvements enter the development process.
4. Transformer: Converts external electrical power into usable energy for
    internal computational processes.
1. Output Interfaces:
2. Full Node Software: Broadcasts confirmed transactions in new blocks to
    the network, enabling external entities to verify and consume these out-
    puts.
3. Heat Dissipation: Manages the release of waste heat generated by internal
    computational processes into the environment.

Each interface implements specific protocols that govern how internal and
external systems can interact, creating measurable boundaries while enabling
essential flows of transactions, contributions, energy, and waste heat. This
boundary definition allows us to clearly distinguish between Bitcoin’s internal
processes and its environmental interactions.


## 7 DSA Phase #3 - Recursive Decomposition

### 7.1 Overview

After identifying Bitcoin’s primary output and conducting a preliminary envi-
ronmental analysis we can now examine the internal architecture and dynamics
that enable the block production process. Analysis reveals four primary inter-
acting subsystems that maintain Bitcoin’s existence as a decentralized network:
Validation, Mining, Development, and Protocol. These subsystems work in
continuous coordination, with each playing a distinct but interconnected role in
Bitcoin’s operation:

1. Validation: Processes and propagates transactions.
2. Mining: Confirms transactions into blocks through energy intensive proof-
    of-work.
3. Protocol: Provides formal software-encoded rules governing the entire sys-
    tem.
4. Development: Enables controlled adaptation and evolution of the network.

across these subsystems while maintaining strict coordination through well-
defined interfaces and flows. We can trace how information and work moves
through the system, starting with transaction processing and following through
to protocol evolution.

### 7.2 Validation

Bitcoin’s architecture separates key responsibilities

7.2.1 Purpose and Components

The Validation subsystem is responsible for taking the transaction request in-
puts and feeding them into the network for processing and confirmation. It
maintains network decentralization through a distributed network of full nodes
that independently verify and propagate transactions and blocks. It serves as
the foundation of Bitcoin’s trustless consensus model by ensuring each node
maintains an identical representation of the blockchain state while operating
independently.

7.2.2 Key Interfaces

There are two key interfaces which manage the subsystem’s boundary interac-
tions and facilitate its role in the broader network. The validation subsystem
implements strict protocol rules for transaction and block validation, main-
taining a local mempool of unconfirmed transactions and participating in the
network-wide propagation of validated blockchain data. After receiving trans-
actions through the software wallet interface, the validation subsystem verifies


their format and signatures. Valid transactions are added to the node’s mem-
pool - a waiting area for unconfirmed transactions. Through the transaction
propagation interface (see Table 7 in Appendix A), these transactions are broad-
cast to other nodes and, crucially, to the mining subsystem where they become
candidates for inclusion in new blocks.

7.2.3 Internal Mechanics

7.2.4 Interaction with Mining

Once validated, carefully defined transactions flow into the mining subsystem
in a process managed by interfaces following strict protocols on both ends. This
flow (detailed in Table 8 in Appendix A) demonstrates a key principle of Bit-
coin’s architecture—the separation of validation from consensus determination.
While the validation subsystem ensures transactions meet all protocol rules, it’s
the mining subsystem that determines their ultimate ordering and inclusion in
the blockchain.

### 7.3 Mining

7.3.1 Purpose and Components

The mining subsystem is responsible for taking validated transactions as input
and feeding them into the complex confirmation process which produces con-
firmed transactions in blocks as output. It secures the Bitcoin network through
proof-of-work computation, while also driving the selection of transactions and
enforcing monetary policy. Mining connects to the system’s broader environ-
ment through the energy interface , consuming significant electrical power to
perform proof-of-work calculations.

7.3.2 Key Interfaces

Three critical interfaces manage its boundary interactions (see Table 9 in Ap-
pendix A for details):
1.Mempool Transaction Selection: Selects and prioritizes unconfirmed
transactions based on fee rates and block constraints 2.Protocol Rule Recep-
tion: Receives and implements consensus rules and blockchain state information
3.Block Dissemination: Propagates newly mined blocks to the network

7.3.3 Internal Mechanics

The mining subsystem first interacts with the validated transaction pool through
its mempool transaction Selection interface. This interface actively monitors
the mempool, selecting and prioritizing transactions based on fee rates and block
size constraints. To properly construct valid blocks, the mining subsystem must
adhere to strict consensus rules received through its protocol rule reception
interface. These rules govern critical parameters including:


1. Current block reward calculation
2. Difficulty target requirements
3. Block size and weight limits
4. Transaction ordering requirements

Once a valid proof-of-work solution is found, the block dissemination inter-
face handles propagating the newly mined block to the network. This initiates
a cascade of validation and synchronization across the network. This processing
cycle represents Bitcoin’s core operational loop.

7.3.4 Core Operational Loop

This processing cycle represents Bitcoin’s core operational loop:

1. Users submit unconfirmed transactions through the validation subsystem.
2. The protocol subsystem confirms their validity against current rules.
3. The mining subsystem selects and orders transactions based on Protocol’s
    parameters.
4. Once a valid block is found, the protocol subsystem validates it and up-
    dates the network.
5. The validation subsystem propagates these changes across the network.

This cycle demonstrates how Bitcoin achieves decentralized consensus through
the coordinated but independent actions of its subsystems.

7.3.5 Interaction with Protocol

The interaction between mining and protocol subsystems (detailed in Table 10
in Appendix A) represents a critical feedback loop in Bitcoin’s operation.

### 7.4 Protocol Subsystem

7.4.1 Purpose and Components

The protocol subsystem orchestrates inputs and outputs from all internal sub-
systems and ensures that the decentralized subsystems are all operating accord-
ing to the same set of code defined rules. It serves as Bitcoin’s fundamental rule
engine, enabling decentralized consensus without central coordination. Unlike
the other subsystems, protocol operates purely internally, coordinating inter-
actions between mining, validation, and development to maintain consistent
network behavior through strict code-defined rules.


```
Table 5: Protocol Subsystem Key Interfaces
Interface Purpose Key Functions
Protocol Version Management Upgrade coordination
```
- Version compatibility
- Security patch integration
- Update distribution

```
Block & Transaction Rules Consensus rule definition
```
- Block validation rules
- Transaction validity crite-
    ria
- Monetary policy parame-
    ters

```
Block Validation/Integration Chain state management
```
- Block verification
- Transaction validation
- State transitions

```
Block & State Distribution Network synchronization
```
- Block propagation
- State distribution
- Network consistency

7.4.2 Key Interfaces

Analysis reveals four critical interfaces that manage aspects of protocol opera-
tion.
Critical Feedback Loops The protocol subsystem coordinates several critical
feedback loops:

1. Difficulty Adjustment: Monitors block times between mining and valida-
    tion to maintain consistent block production
2. Block Reward Schedule: Controls monetary policy through predetermined
    subsidy adjustments


3. Consensus Rules: Updates network parameters based on observed network
    conditions
4. Upgrade Activation: Manages coordinated deployment of protocol im-
    provements

These feedback mechanisms enable Bitcoin to self-regulate and maintain
stability without central control.

7.4.3 Code-as-Law Implementation

The protocol subsystem is unique in that it exists as pure code—software rules
written in the Bitcoin Core implementation that govern how all other subsys-
tems must behave. These rules are replicated across every node in the network,
creating an immutable framework that converts human economic behavior into
deterministic computer operations.

Unlike traditional financial systems where rules might be interpreted or se-
lectively enforced by human authorities, Bitcoin’s protocol rules are explicit in
code and automatically enforced by every network participant. This code-as-law
principle ensures that critical parameters like monetary policy (coin issuance),
transaction validity, and consensus mechanisms operate with mathematical pre-
cision rather than human discretion.

```
Table 6: Protocol-Validation Interaction Flow
Flow Description Key Parameters
Block & State Updates Network state information and
new block announcements dis-
tributed from Protocol to Vali-
dation subsystem.
```
- Block propagation time
- Nodes receiving block
- Block size
- Network difficulty

```
Network Synchronization State and block propagation
data from the validation net-
work.
```
- Node version info
- Chain state
- Block header verification
    status


7.4.4 Interaction with Validation

This interaction maintains network-wide consistency while preserving decentral-
ization through:

1. Independent verification of all state changes by validation nodes
2. Rapid propagation of new blocks across the network
3. Continuous monitoring of network health metrics
4. Automatic adjustment of propagation parameters

### 7.5 Development Subsystem

7.5.1 Purpose and Components

The development subsystem takes in proposed enhancements to Bitcoin as in-
puts and feeds them into a complex process of political deliberation where
accepted enhancements are produced as outputs for the protocol. It enables
Bitcoin’s controlled evolution through a decentralized process of protocol en-
hancement. It interfaces with the external developer community through the
contribution interface, receiving code submissions, bug reports, and improve-
ment proposals. The key interface for this process, the Protocol Enhancement
Release interface, is described in detail in Table 11 in Appendix A.

7.5.2 Development Process

The development process emphasizes rigorous peer review and consensus-building
to ensure changes maintain Bitcoin’s fundamental properties and network secu-
rity. Core developers propose, review, and implement protocol improvements
through the Bitcoin Improvement Proposal (BIP) process.

7.5.3 Interaction with Protocol

The relationship between protocol and development subsystems is bidirectional,
creating a crucial feedback loop that governs Bitcoin’s evolution (see Table 12
in Appendix A for details).
The protocol subsystem influences development through:

1. Backward compatibility requirements for all changes
2. Existing consensus rules that must be preserved
3. Network-wide deployment considerations
4. Security model constraints


## 8 Discussion

This paper has demonstrated how applying Deep Systems Analysis to Bit-
coin reveals a holistic view of its functioning as a complex adaptive system.
Rather than reducing Bitcoin to simplistic framings—whether as mere peer-
to-peer currency, digital gold, or a speculative bubble—DSA enables a more
neutral, comprehensive perspective that acknowledges Bitcoin’s many dimen-
sions. The analysis identifies Bitcoin’s primary function—the production of
confirmed transactions within blocks—and systematically traces the internal
subsystems and environmental interactions that enable this process. By map-
ping key inputs (electricity, code contributions, transaction requests) through
clearly defined interfaces to outputs (confirmed transactions, waste heat), we
establish measurable flows that can be monitored, analyzed, and modeled. This
structured decomposition reveals how Bitcoin’s essential properties like decen-
tralization and censorship resistance emerge not from any single component but
from the dynamic interactions between subsystems. Bitcoin’s architecture sep-
arates concerns across four primary subsystems (Validation, Mining, Protocol,
and Development), with each maintaining distinct responsibilities while coor-
dinating through well-defined interfaces. This separation serves as a defense
against centralization—no single subsystem can control the network, yet to-
gether they maintain coherent functioning through carefully designed flows and
feedback mechanisms. The Bitcoin protocol serves as the system’s ”constitu-
tion”—encoding basic rules as immutable code while providing mechanisms for
coordinated evolution through the Development subsystem. This helps Bitcoin
maintain a balance between stability and adaptability that has proven remark-
ably resilient over Bitcoin’s fifteen-year history. DSA clearly shows how Bitcoin
operates at the intersection of physical, digital, and social realms. The Mining
subsystem converts electricity into digital security, the Validation subsystem
transforms digital rules into social trust, and the Development subsystem chan-
nels social consensus into protocol evolution. These cross-domain interactions
create unique feedback loops that traditional disciplinary approaches struggle
to capture in isolation. The framework established in this analysis provides a
foundation for more rigorous, empirically-grounded research on Bitcoin’s be-
havior, evolution, and potential futures. By identifying measurable flows at
system boundaries and interfaces, we enable data collection that can inform
both theoretical models and practical applications, from engineering updates to
regulatory approaches.

## 9 Future Research Directions

### 9.1 Refined Analysis

The subjective nature of systems analysis means that our initial decomposi-
tion represents just one of many possible perspectives. Future work should
engage a diverse group of domain experts—from core developers and miners to


economists and regulators—to refine the system boundaries, interfaces, and flow
definitions. Comparing multiple candidate models would strengthen confidence
in the framework while highlighting areas where competing perspectives exist.

This paper has pursued decomposition only to the first major level of subsys-
tems. Each identified subsystem (Validation, Mining, Protocol, and Develop-
ment) could be further decomposed to reveal more detailed internal structures
and dynamics. For example, exploring the internal workings of the Mining sub-
system would illuminate how mining pools, individual miners, and ASIC manu-
facturers interact, potentially revealing additional feedback loops and emergent
behaviors.

An important element of the DSA process not fully addressed in this paper
involves estimating system transformation functions that describe relationships
between inputs and outputs. With appropriate data collection guided by the
framework established here, researchers could develop and test mathematical
models of how Bitcoin transforms inputs (electricity, transaction requests, con-
tributions) into outputs (confirmed transactions, network security).

Bitcoin offers a unique opportunity for evolutionary analysis due to its com-
pletely transparent transaction history and extensive archives of community
discussions. The DSA framework could inform historical analysis of key evolu-
tionary milestones—from the early hardening of the protocol (2010-2012) to the
scaling debates (2015-2017) to recent developments in layer-2 technologies. This
historical perspective would shed light on how Bitcoin’s subsystems co-evolve
and how governance mechanisms have developed over time.

A critical next step involves developing the technical infrastructure to collect
and organize real-time network data aligned with the flows identified in this
analysis. Building a structured knowledgebase would support ongoing research
while enabling more sophisticated modeling and prediction efforts

### 9.2 Modeling and Simulation

The core premise of DSA is that thorough analysis prior to modeling leads to
more robust and useful models. This hypothesis deserves empirical testing. The
Bitcoin system decomposition presented here provides a foundation for develop-
ing integrated models that combine agent-based, system dynamics, and network
approaches.

Agent-based models could simulate how individual miners, developers, and
users interact within the constraints of Bitcoin’s protocol rules, potentially re-
vealing emergent behaviors not obvious from the system description alone. Sys-
tem dynamics models could explore feedback loops between subsystems, helping
predict how changes in one area (e.g., development governance) might affect
others (e.g., mining incentives). Network models could map and analyze the


evolving relationships between system components, from transaction patterns
to mining pool distributions.

These modeling approaches could be particularly valuable for exploring Bit-
coin’s emergent properties—those fundamental characteristics that don’t belong
to any single component but arise from system-wide interactions. Key emergent
properties include decentralization, censorship resistance, trust, and value cre-
ation [22]. These properties form interconnected feedback loops; for instance,
increased value drives mining participation, enhancing security and building
trust, which enables further adoption. A deeper understanding of these emer-
gent dynamics would not only improve theoretical frameworks but also inform
practical decisions by protocol developers, miners, and users.

### 9.3 Generalized Cryptoeconomic Systems Research

While Bitcoin served as a logical starting point for this research due to its long
history and relatively simple design, the DSA approach demonstrated here could
be extended to analyze other public blockchain systems. Comparative analysis
of systems including Bitcoin, Ethereum, Cosmos Hub, and Solana would reveal
how different architectural choices influence system behavior and emergent prop-
erties. Such comparative analysis could build on existing blockchain governance
research while adding systematic depth through the DSA framework [23]. This
approach could be particularly valuable for addressing open problems in De-
centralized Autonomous Organizations (DAOs), where the interaction between
technical, economic, and social systems poses unique challenges [24]. The theo-
retical frameworks underlying DSA could also be enriched through integration
with other promising approaches in cryptoeconomic theory. These include the
contribution systems framework [25], mathematical models based on dynami-
cal systems and control theory [26], and set-theoretic approaches to consensus
mechanisms [27]. Such integration would strengthen the mathematical foun-
dations of DSA while broadening its applicability across the cryptoeconomic
landscape.

## 10 Conclusion

This paper has demonstrated how Deep Systems Analysis provides a valuable
framework for understanding Bitcoin as a complex adaptive system. By decom-
posing Bitcoin into its constituent subsystems and mapping their interactions,
we’ve revealed the intricate mechanisms that enable its core functions while
maintaining decentralization and security. The DSA approach bridges tradi-
tional disciplinary divides, allowing technical, economic, and social perspectives
to be integrated within a single analytical framework. This integration is partic-
ularly valuable in the cryptoeconomic domain, where emergent system proper-
ties arise from interdependent technical designs, economic incentives, and human
behaviors. As nation-states and major corporate institutions continue adopt-


ing Bitcoin and blockchain technologies for treasury reserves, payments infras-
tructure, and settlement systems, comprehensive analytical frameworks become
essential for sound policy and strategy development. Similarly, as blockchain
systems increasingly mediate human and AI agent interactions, the need for
rigorous systems-based understanding becomes more critical. The recent surge
in AI agents interacting with blockchains points to a future where these systems
may serve as primary coordination mechanisms for complex economic networks
involving both human and artificial intelligence. By providing a framework
that spans technical, economic, and social dimensions, DSA offers a promising
approach for navigating this complex future. The Bitcoin analysis presented
here represents an initial step toward a more sophisticated understanding of
cryptoeconomic systems. By continuing to refine these analytical methods and
applying them across diverse blockchain architectures, researchers can develop
more robust theories, models, and practical applications that account for the
full complexity of these revolutionary technologies.

## References

```
[1] Joseph Bonneau, Andrew Miller, Jeremy Clark, Arvind Narayanan,
Joshua A. Kroll, and Edward W. Felten. SoK: Research Perspectives and
Challenges for Bitcoin and Cryptocurrencies. In2015 IEEE Symposium on
Security and Privacy, pages 104–121, May 2015. doi: 10.1109/SP.2015.14.
```
```
[2] Jason P. Lowery. Softwar: A Novel Theory on Power Projection and the
National Strategic Significance of Bitcoin. Thesis, Massachusetts Institute
of Technology, February 2023.
```
```
[3] Shermin Voshmgir and Michael Zargham. Foundations of cryptoeco-
nomic systems. Working paper, Vienna University of Economics and
Business, 2020. URLhttps://research.wu.ac.at/en/publications/
foundations-of-cryptoeconomic-systems-6.
```
```
[4] Andreas Hieronymi. Understanding Systems Science: A Visual and Integra-
tive Approach. Systems Research and Behavioral Science, 30(5):580–595,
```
2013. ISSN 1099-1743. doi: 10.1002/sres.2215.

```
[5] George E. Mobus and Michael C. Kalton.Principles of Systems Science.
Understanding Complex Systems. Springer, New York, NY, 2015. ISBN
978-1-4939-1919-2 978-1-4939-1920-8. doi: 10.1007/978-1-4939-1920-8.
```
```
[6] Zachary Neal. Handbook of Applied System Science.
https://www.routledge.com/Handbook-of-Applied-System-
Science/Neal/p/book/9780415843348, 2016.
```
```
[7] Chaitanya Kaligotla and Charles M Macal. A GENERALIZED AGENT
BASED FRAMEWORK FOR MODELING A BLOCKCHAIN SYSTEM.
```

```
In2018 Winter Simulation Conference (WSC), pages 1001–1012, Gothen-
burg, Sweden, December 2018. IEEE. ISBN 978-1-5386-6572-5. doi:
10.1109/WSC.2018.8632374.
```
```
[8] Kiran Karra, Tom Mellan, Maria Silva, Juan P. Madrigal-Cianci,
Axel Cubero Cortes, and Zixuan Zhang. An Agent-Based Model Frame-
work for Utility-Based Cryptoeconomies, July 2023.
```
```
[9] Protocol Labs. Filecoin Economics Explorer · Streamlit.
https://filcryptoecon.streamlit.app/SupplyExploration, 2023.
```
[10] Benjamin Kraner, Nicol`o Vallarano, Claudio J. Tessone, and Caspar
Schwarz-Schilling. Agent-Based Modelling of Ethereum Consensus, May
2023.

[11] Vignesh Gopalakrishnan.Modeling the Trajectory of Bitcoin Using System
Dynamics. Thesis, Massachusetts Institute of Technology, May 2022.

[12] Davide Lasi and Lukas Saul. A System Dynamics Model of Bitcoin: Mining
as an Efficient Market and the Possibility of ”Peak Hash”, April 2020.

[13] Paolo Tasca, Shaowen Liu, and Adam Hayes. The Evolution of the Bitcoin
Economy: Extracting and Analyzing the Network of Payment Relation-
ships, July 2016.

[14] Marco Venturini. Mapping network structures and dynamics of de-
centralised cryptocurrencies: The evolution of Bitcoin (2009-2023).
https://arxiv.org/html/2501.11416v1, 2025.

[15] Ting Chen, Yuxiao Zhu, Zihao Li, Jiachi Chen, Xiaoqi Li, Xiapu Luo,
Xiaodong Lin, and Xiaosong Zhange. Understanding Ethereum via Graph
Analysis. InIEEE INFOCOM 2018 - IEEE Conference on Computer Com-
munications, pages 1484–1492, April 2018. doi: 10.1109/INFOCOM.2018.
8486401.

[16] Yijun Xia, Jieli Liu, Jiatao Zheng, Jiajing Wu, and Xiaokang Su. Portraits
of Typical Accounts in Ethereum Transaction Network. In Hong-Ning Dai,
Xuanzhe Liu, Daniel Xiapu Luo, Jiang Xiao, and Xiangping Chen, edi-
tors,Blockchain and Trustworthy Systems, pages 44–56, Singapore, 2021.
Springer. ISBN 9789811679933. doi: 10.1007/978-981-16-7993-34.

[17] Tian Min and Wei Cai. Portrait of decentralized application users: An
overview based on large-scale Ethereum data.CCF Transactions on Perva-
sive Computing and Interaction, 4(2):124–141, June 2022. ISSN 2524-5228.
doi: 10.1007/s42486-022-00094-6.

[18] Dan Lin, Jingjing Yang, Jialan Chen, Jiajing Wu, and Zibin Zheng.
Evolution of Global Driving Factors in Ethereum Transaction Networks.
In Jiajing Wu, Dan Lin, and Zibin Zheng, editors,Blockchain Transac-
tion Data Analytics: Complex Network Approaches, pages 51–72. Springer


```
Nature, Singapore, 2025. ISBN 978-981-9744-30-5. doi: 10. 1007 /
978-981-97-4430-53.
```
[19] Arijit Khan. Graph Analysis of the Ethereum Blockchain Data: A Sur-
vey of Datasets, Methods, and Future Work. In2022 IEEE International
Conference on Blockchain (Blockchain), pages 250–257, August 2022. doi:
10.1109/Blockchain55522.2022.00042.

[20] George E. Mobus.Systems Science: Theory, Analysis, Modeling, and De-
sign. Springer International Publishing, Cham, 2022. ISBN 978-3-030-
93481-1 978-3-030-93482-8. doi: 10.1007/978-3-030-93482-8.

[21] Cambridge University. Cambridge Blockchain Network Sustainability In-
dex. https://ccaf.io/cbnsi/cbeci, 2025.

[22] Michael Norman. The Emergence of Trust and Value in Public Blockchain
Networks. https://www.researchgate.net/publication/325552991, June
2018.

[23] Gabriella Laatikainen, Mengcheng Li, and Pekka Abrahamsson. A system-
based view of blockchain governance.Information and Software Technology,
157:107149, May 2023. ISSN 09505849. doi: 10.1016/j.infsof.2023.107149.

[24] Joshua Tan, Tara Merk, Sarah Hubbard, Eliza R. Oak, Helena Rong, Joni
Pirovich, Ellie Rennie, Rolf Hoefer, Michael Zargham, Jason Potts, Chris
Berg, Reuben Youngblom, Primavera De Filippi, Seth Frey, Jeff Strnad,
Morshed Mannan, Kelsie Nabben, Silke Noa Elrifai, Jake Hartnell, Ben-
jamin Mako Hill, Tobin South, Ryan L. Thomas, Jonathan Dotan, Ariana
Spring, Alexia Maddox, Woojin Lim, Kevin Owocki, Ari Juels, and Dan
Boneh. Open Problems in DAOs, June 2024.

[25] Ellie Rennie and Jason Potts. Contribution Systems, November 2024.

[26] Zixuan Zhang, Michael Zargham, and Victor M. Preciado. On model-
ing blockchain-enabled economic networks as stochastic dynamical systems.
Applied Network Science, 5(1):1–24, December 2020. ISSN 2364-8228. doi:
10.1007/s41109-020-0254-9.

[27] Mike Neuder. A set-theoretic view of Ethereum coteries.
https://notes.ethereum.org/@mikeneuder/set-theoretic-ethereum, Oc-
tober 2023.


## A Detailed Interface and Flow Specifications

This appendix provides detailed specifications for the interfaces and flows be-
tween Bitcoin’s subsystems that were referenced in the main text. These spec-
ifications include comprehensive parameter listings and technical details that
support the Deep Systems Analysis methodology.

```
Table 7: Validation Subsystem Key Interfaces
Interface Purpose Key Functions
Transaction Propagation Network distribution of
unconfirmed transactions •Transaction verification
```
- Network broadcast
- Fee evaluation

```
Table 8: Validation-Mining Interaction Flow
Flow Description Key Parameters
Mempool Transactions Validated but unconfirmed
transactions passed from the
Validation subsystem to the
Mining subsystem for potential
block inclusion, representing
the current pool of pending
transactions managed through
strict interface protocols.
```
- Number of unconfirmed
    transactions
- Average transaction fee
- Propagation time (Sec-
    onds)


Table 9: Mining Subsystem Key Interfaces
Interface Purpose Key Functions
Mempool Transaction Selection Block content determina-
tion •Selects and prioritizes
unconfirmed transactions
based on fee rates and
block constraints

Protocol Rule Reception Block template creation

- Receives and implements
    consensus rules and
    blockchain state informa-
    tion

Block Dissemination Network distribution of
new blocks •Propagates newly mined
blocks to the network

Table 10: Mining-Protocol Interaction Flow
Flow Description Key Parameters
Protocol Rules & Parameters Consensus rules and chain state
parameters transmitted from
Protocol to Mining subsystem.
Guides valid block creation and
reward calculation.

- Current block subsidy
- Network difficulty
- Chain height
- Block template rules

Mined Blocks Newly created blocks transmit-
ted from Mining to Protocol sub-
system for validation and net-
work distribution. Represents
the core proof-of-work output.

- Block hash
- Transaction count
- Block reward


Table 11: Development Subsystem Key Interface
Interface Purpose Key Functions
Protocol Enhancement Release Protocol upgrade coordi-
nation

```
Issues new protocol versions that
have achieved community con-
sensus through the Bitcoin Im-
provement Proposal (BIP) pro-
cess, manages:
```
- BIP implementation
- Version release coordina-
    tion
- Upgrade deployment
- Backward compatibility
    testing

Table 12: Development-Protocol Interaction Flow
Flow Description Key Parameters
Protocol Constraints Existing consensus rules and pro-
tocol architecture that constrain
and guide development decisions

- Current protocol version
- Active soft forks
- Network compatibility re-
    quirements
- Security boundaries

Protocol Updates Protocol upgrades and security
patches flowing from Develop-
ment to Protocol

- Protocol version number
- BIP implementation status
- Activation height
- Backward compatibility re-
    quirements


