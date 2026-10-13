# 2 Principles

**In this chapter we discuss the main principles for the development, design and governance of the standard. This is based mainly on [Results of research: Standard for data exchange between pension administration & asset management parties’’](https://www.pensioenfederatie.nl/cms/streambin.aspx?documentid=18380).**

## 2.1 *Preamble: Principles of VBPUO Standardisation*

*The aim of standardisation is a seamless and efficient exchange of information between all parties in the chain. The VBPUO standard rests on the following principles:*

- *Pragmatism and flexibility  
  The standard is not a requirement for uniformity, but a framework for interoperability. Chain partners keep their own internal processes and systems. The focus is on streamlining external communication.*

- *Interoperability as the ultimate goal  
  The value of the standard is proven in practice. The test: an organisation must be able to switch to another chain partner without problems, without significant changes to the data interface.*

- *Controlled degrees of freedom  
  Flexibility is not unlimited. For predictability and reliability, the permitted variations are explicitly defined and deliberately limited.*

- *Supported by the chain  
  Changes and variations do not arise unilaterally. They require broad support, in order to prevent fragmentation and to preserve the value of the standard in the long term.*

  *In this way the VBPUO standard remains a shared instrument for efficiency, predictability and future-proof cooperation in the chain.*

## 2.2 Background

Pension administration organisations (PUOs) regularly need information from fiduciary managers (FMs) and/or investment administrators (BAs) in order to administer the participant records of pension schemes correctly. Conversely, FMs (and asset managers) need information in order to invest the funds for the various pension providers within the framework of the agreed investment policy. The required data exchange between PUOs, FMs and BAs (and asset managers) is expected to be very similar in all cases.

With the introduction of the Wtp, the information need will change and the frequency with which information exchange is desired will increase. The information need of PUOs, FMs and BAs for the services to pension providers is fundamentally very similar. Any differences in the information exchange will depend mainly on the type of scheme being administered.

In the accumulation phase of the flexible premium scheme (FPR), the information need will largely correspond to that of the current 'defined contribution' schemes, possibly supplemented with data on the risk-sharing reserve. As regards the exchange of data during the collective payout phase, this will in many respects be comparable to the payout phase of the solidarity premium scheme.

For the solidarity premium scheme (SPR), an entirely new data flow will have to be set up, for both the accumulation phase and the payout phase. There will have to be closer alignment between the fund assets invested by the FM and the collective administration of personal pension assets by the PUO.

## 2.3 Out of Scope

The following fall outside the scope of the elaboration of the information exchange:

- Contractual agreements between parties regarding the overall process around asset management. The standard provides for the necessary information exchange, the data need, between PUOs and asset management parties at the various process moments. The standard provides for the data need for both the Solidarity Premium Scheme (SPR) and the Flexible Premium Scheme (FPR). The exact form of the data exchange between parties is, however, determined by contractual agreements between the cooperating pension provider and its asset management partners.

- Processes that are already running and do not fundamentally change, such as the reconciliation of the investment administration between the FM and the BA/asset service provider.

- Information that does not need to be exchanged because it is used by only one party in the chain.

- Information regarding investment policy, protection and allocation rules and cohort composition. This information is shared by the pension provider with the parties involved through various policy documents, such as the strategic investment policy, the annual investment plan and the investment guidelines.

- Information exchange between pension participant, pension provider and/or PUO.

  Allocation of returns to participants.

- Information about costs:

  - As yet, there is no fully crystallised and unambiguous process in cooperation chains for arriving at the cost allocation (and also the communication about costs). Experience so far seems to indicate that this is difficult to standardise. Different parties make different trade-offs regarding processing, granularity, actual versus budgeted, making provisions, timeliness, division of roles in supplying the various components, etc.

  - It is expected that existing processes for compiling the DNB annual statement J402 will continue to form the basis for the information exchange about costs, for both the SPR and the FPR.

- Insight into/look-through to the actual investments, usually referred to as “Lookthrough” information. Ad hoc requests for additional information from the BA/asset service provider or FM may be necessary, but do not fall under regular data exchange in the context of the exchange as described in this manual.

- Any specific information exchange required for a premium-benefit agreement as offered by insurers.

- The periodicity of the exchange. Not every process within pension administration leads to necessary actions within asset management. The consequences of processes that do lead to asset management actions must, however, be exchanged on a periodic basis. The periodicity of the exchange of the related messages can be arranged flexibly between parties.

- Funding ratio / coverage ratio. The calculation and reporting of the funding ratio falls under the responsibility of the PUO or BA. The VBPUO standard does not provide a separate message for this. See GitHub issue [#118](https://github.com/Stichting-SIVI/VBPUOdsk/issues/118).

- Division of tasks/Division of roles. The way in which parties cooperate, the division of roles or governance, is <u>not</u> part of the standard.

## 2.4 Principles of Data Exchange

To make the data exchange as practical as possible, the following principles apply:

- The data standard can be used for any (governance) division between pension administration and asset management.

- If the asset service provider fulfils an independent role as leading BA and/or tests the execution of policy, it receives the same information as the FM, so that it can report independently to pension funds on the investment policy followed and realised in relation to the objectives.

- The FM role receives the information needed to invest the collective assets within the framework of the investment policy, taking into account inflow and outflow (through premiums, benefits and value transfers) and projected benefits.

- The PUO gives the participant insight into the development of the assets intended for the pension benefit (SPR) and/or the capital intended for pension (FPR), including the allocation of returns and expected benefits.

- Parties receive the data intended for them directly from the sending party. An FM therefore does not, for example, have to forward the information received from a PUO to another party selected by the pension fund, such as an asset service provider and/or a Liability-Driven Investment (LDI) manager. The consequence is that the sender sends the same message to each receiver separately, with its own endpoint and identification per receiver. In terms of content these are then the same data; technically they are different messages. The purpose of the sending may differ per receiver. The same order instruction is an instruction for one receiver and a notification or record for another; for a third receiver the same message may serve risk control.

- <u>Messages once accepted are not corrected unilaterally</u>. Messages that have been accepted by the receiving party may lead directly to irreversible operational processes, such as investment transactions or the allocation of returns to participants. If a sending party discovers an error in a message that has already been accepted, coordination with the receiving party is mandatory before any correction message is sent. The specific procedures for this are explained further in section [4.4](../chapter-4-fpr-processes/#44-feedback-message-resending).

## 2.5 Clarification of Data Exchange Principles

During the substantive consultation round in May/June 2023, a number of issues came up regularly that did not lead to changes in the substantive part of the [report](https://www.pensioenfederatie.nl/cms/streambin.aspx?documentid=18380), but did need to be clarified to prevent misunderstandings.

- **Data model**: The data model contains only the data needed to be able to send and/or receive the required information about the investment of pension money and to be able to share information about realised investment results.

- **Roles (not prescriptive)**: To support the elaboration of the data model, data exchange between various parties in the chain is described. To support understanding of the data model, a division of roles in the chain has been outlined for both the SPR and the FPR, in which the governance model provides for certain segregations of duties. In an alternative set-up, roles may be performed by one and the same party; for example, the FM may also keep the leading investment administration. It is not the intention of this manual to prescribe the form of cooperation between parties and thus the governance model.

- **Periodicity:** In the description of a number of processes it has been indicated that these are expected to have a monthly periodicity. This periodicity is not prescribed. The exchange moments and periods mentioned are examples that may be filled in differently in the agreements between parties.

- **Process description**: For the FPR it is possible to start from already existing processes (including -indicative- timelines and division of roles) for (collective) individual DC schemes. For the SPR this is not yet the case.

- **Costs**: The information exchange about costs falls outside the scope of this standard. For the time being we assume that it will build on existing processes that also form the basis for, for example, the J402 DNB annual statement.

- **The term asset management**: When the term “asset management” is used in this manual, it refers to the parties: FM, BA/asset service provider, custodian and Liability-Driven Investment manager. “Pension administration” refers to the combination of the statutory pension provider and the PUOs that carry out the administration for them.

- **Language**: This report has been prepared for the data exchange between PUOs and asset managers within the Dutch WTP context. The report and the standard are delivered in the Dutch language. The names of the variables used in the standards are, however, in English, so that the conceptual framework is also understandable for non-Dutch speakers who are familiar with asset management.

## 2.6 Participant Communication

See chapter 6 of the [final report](https://www.pensioenfederatie.nl/cms/streambin.aspx?documentid=18380) mentioned earlier in the introduction.

## 2.7 Technology

A number of principles have been formulated regarding the use and technical implementation of the data standard:

- The data exchange is “sustainable”, i.e. not tied to technological trends (or hypes).

- The documentation is clear and transparent.

- The data set can be adjusted in consultation with the parties involved.

- Open technical standards are used as much as possible (for example REST, JSON, SOAP, ODATA, OAuth).

The following has been agreed for the technical implementation of the message traffic:

- Data exchange: RESTful Web services.

- Data format: JSON.

- For the data format, we conform to AFD 2.0 within this standard. This has consequences for, among other things, the naming of the attributes and entities.

<!-- -->

- AFD 2.0 defines the data type of an attribute, **but does not restrict the string length or the number of decimal places**. Any restriction of the number of positions can be agreed between parties. That applies to AFD 2.0 in general. The VB-PUO schemas do lay down lengths and precision (`maxLength`, `multipleOf`); these are binding and cannot be lifted bilaterally. See <https://www.manula.com/manuals/sivi/sivi-all-finance-standard/1/en/topic/data-types-and-formats>

<!-- -->

- Message processing is asynchronous. The message traffic is synchronous in accordance with REST. The frequency of the information exchange is periodic (for example monthly) and processing by the receiver is in principle on a daily basis; synchronous (real-time) is not necessary.

- The message initiative lies with the sender of the information, who brings (pushes) the message to the receiver.

- Service window: the recommendation is office hours. Parties can make their own agreements on this between themselves.

- Security aspects:

  - Two-way authentication (mutual-TLS) is used during the transport of information.

  - Authentication of the sender at the receiving server is required.

  - The data must be guaranteed to arrive at the receiver unchanged. For this purpose the payload can be digitally signed (x-jws-signature, see [§7.4](../chapter-7-4-transport-openapi/)).

Agreements on the aspects below are worked out and dealt with within the framework of the governance structure around the standard.

- The complete – technical – data standard and the various messages based on it.

- Maximum size (numbers and/or file size) of the message. See below under "Handling Large Messages".

- Granularity of the message traffic.

<!-- -->

- A lower granularity means that -at a certain level- fewer details are exchanged.

<!-- -->

- Processing time of received messages.

- Message feedback: response messages (acknowledgement of receipt and correct or error message – substantive and technical – or warning). The rules for this must be described.

- Response time (server).

**Handling Large Messages (Partial messages or Chunking)**

Although the number of transactions per day may be relatively low, the size of individual messages (in particular Message 3 - Pension Projection) can be considerable. In practice, messages larger than approximately 4 MB can lead to problems in transport and processing via modern cloud infrastructures.

To deal with this, the standard offers a mechanism for splitting large messages into several smaller partial messages (chunks).

- Mechanism: The splitting is done via an optional chunking.default block at the top level of a message. This block contains metadata about the splitting, such as the sequence number and the total number of chunks.

- Applicability: This mechanism applies to all functional messages, but not to the feedback message.

- Validity: Each partial message is a self-contained, valid JSON message.

- Processing: The receiver can only merge the partial messages into the complete, logical message after receipt of all parts. An error in one partial message means that the entire logical message is regarded as failed.

- Limits: The standard does not prescribe a maximum number of chunks. The maximum message size and the number of chunks are agreements between chain parties (TOM / SLA). See GitHub issue [#127](https://github.com/Stichting-SIVI/VBPUOdsk/issues/127).

  The detailed specifications of this mechanism can be found in Chapter 6.

## 2.8 Transport of Data

(Some) standardisation of the transport of data, an interface, is of great importance. Standardisation makes life much simpler for the sending and receiving parties and prevents all cooperating parties from having to reinvent the wheel bilaterally every time. Its elaboration is limited to one solution, namely RESTful API/web service. The SIVI API framework provides support for this. Parties that cannot or do not wish to work with the RESTful API/web service solution can develop bilateral solutions themselves. No support for this is provided by the working groups around the standard.

The web service solution is preferred because the information flow can then be managed better (faster through the (internal) chain, better versioning, better verifiability). A portal solution involves manual work and is therefore undesirable.

See also: *7.4* Transport / OpenAPI.

## 2.9 Governance, Management and Releases

### 2.9.1 Roles and Responsibilities

The use of the standard forms part of the individual agreements between pension providers and asset management parties. Parties use the standard in accordance with the agreements that apply to the standard and that are laid down in their contracts.

The standard is owned by the Pensioenfederatie. Management has been placed with SIVI, which acts on behalf of the Steering Group DSO. The substantive further development takes place in consultation with the sector through an Advisory Group (KBG).

The precise organisation of the management, the roles, the change procedure and the working method of the Advisory Group are laid down in the document "Organisation of the Management of the Standard Asset Management Pension Administration". This document is the leading source for all governance-related agreements.

### 2.9.2 Release Policy and Version Management

To make the further development of the standard predictable and manageable, the following release policy applies:

- Annual release cycle: Each year a prerelease is published at the end of June, which is converted into the definitive annual release at the end of September (e.g. "Release 2026").

- Continuous development: Changes approved during the year are made available on GitHub as soon as they have been completed.

- Support of versions: In addition to the current annual release, the two preceding annual releases remain available. For 2026 these are: Release 2026, Release “2024 November” and Release “Juli 2024”.

### JSON Schema Draft 2020-12

From release 2027, the VBPUO standard uses JSON Schema Draft 2020-12 for the JSON schemas published via GitHub.

The move to Draft 2020-12 primarily concerns:
- modernisation of the JSON Schema dialect;
- harmonisation with current tooling and IDE support;
- adjustment of internal and external schema references.

As a result of this technical migration, the functional message structures and the business meaning of the messages remain unchanged.
