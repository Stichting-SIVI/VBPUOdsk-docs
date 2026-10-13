## 6.4 Messages

The base message is elaborated below into specific messages. From release 2027, 10 substantive messages and the Feedback Message are active; 5 FPR messages have been discontinued (see [§4.3.11](../chapter-4-fpr-processes/#4311-discontinued-messages)). The distinction between a direct and a layered order model has been dropped as of release 2027; see §4.2.

Table 12 below gives an overview of these messages and between which roles they are exchanged:

| Message name | PUO | FM | BA | LDI |
|----|----|----|----|----|
| 1\. Assets (0001a) | from | to |  |  |
| 2\. Cashflow (0001b) | from | to | from |  |
| 3\. Pension Projection (0001c) | from | to |  | to |
| 4\. Return Information (00002) | to |  | from |  |
| 5\. Order Instruction (00541) | from |  | to |  |
| 6\. Order Confirmation (00542) | to |  | from |  |
| 10\. Control Information Investment Pools (00553) |  | to | from |  |
| 13\. Value Information Investment Pool (00555b) | to |  | from |  |
| 14\. Payment Information (00556) |  | to | from |  |
| 15\. Corporate Actions (00557) | to | from | from |  |
| Feedback Message |  |  |  |  |

The Feedback Message can be used for both FPR and SPR and is always a response to a received message; one of the other messages.

**Table 12 – Overview of messages between senders and receivers**

**Legend**

- Pension administration organisations (PUO) — these also include self-administering funds (ZAF)

- Fiduciary managers (FM)

- Investment administrators / asset service provider (BA)

- Liability-Driven Investment managers (LDI)

**Explanation: Administrator of Cohort and Investment Pools (ACB) — discontinued**

The ACB role has been discontinued as a separate actor in this overview. In practice this role is fulfilled by the BA or sometimes by the PUO. Because the ACB role no longer appeared as a separate party as of July 2026, the column has been removed from the matrix. Should the ACB role act as an explicit party again in the future, the message schema still allows for this through the existing messages. See GitHub issue [#131](https://github.com/Stichting-SIVI/VBPUOdsk/issues/131).

**Explanation: role versus party.** Table 12 is a **role** matrix and is generated from the data model. Messages 10 and 14 are sent by the BA role. That role can be fulfilled by the PUO; this does not make the PUO a second sender. For that reason, the PUO column for message 14 does not contain `from`. See GitHub issue [#142](https://github.com/Stichting-SIVI/VBPUOdsk/issues/142).

The Feedback Message has no fixed sender and receiver — it follows the message to which it responds — and therefore falls outside the generated rows.

**Note:** Each receiving party/role receives its **information directly** from the sending party. Sending to parties/roles not mentioned in Table 12 is also direct. Received information is not forwarded to other parties. A message can therefore be sent to more than one receiver, each with its own endpoint and identification; see [§2.4](../chapter-2-principles/#24-principles-of-data-exchange).

**Explanation: suffixes in the message diagrams on GitHub.** An entity can occur in more than one position in a single message. In message 3, for example, `financialTransaction.payment` occurs directly under the scheme, under the cohort and under the investment portfolio. In the message diagrams on GitHub (the [Wiki/Berichtenoverzicht](https://github.com/Stichting-SIVI/VBPUOdsk/wiki/Berichtenoverzicht) and the folder `MessageStructureView` for each message), these positions are given a suffix, such as `financialTransaction.payment_1`. That suffix is a sequence number to keep the positions in the diagram apart, not a different entity type: the attribute `entityType` has the same value in every position (here `payment`). The suffix does not occur in the message itself; which position is meant follows from the parent entity. The sequence number is assigned per message, so the same suffix can denote a different position in another message. This manual does not show the suffixes: in the base message (§6.4.1), the message structures and the cross-reference table (§6.5), each position appears under its own parent entity.

The table below shows the message types and their meaning. The messages discontinued from release 2027 are listed in [§4.3.11](../chapter-4-fpr-processes/#4311-discontinued-messages). In parentheses, the reference to the final report of the working group[^7]: “Eindrapport onderzoek standaard VB PUO (september 2023.pdf”.

PMT = pensionMessageType in AFD 2.0 (the descriptions of the message types are given).

TAG = the designation of the message used in the API[^8].

<table>
<colgroup>
<col style="width: 9%" />
<col style="width: 14%" />
<col style="width: 25%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr>
<th>Type</th>
<th>Message type</th>
<th>PMT/<br />
TAG</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<th>SPR</th>
<td><p>1. Assets (0001a)</p>
<p>(4.2.1.1)</p></td>
<td>Vermogen/<br />
Capital</td>
<td><p><strong>From 🡪 To</strong></p>
<p>From PUO to FM and BA/asset service provider.</p>
<p>On a periodic (expected to be monthly) basis, the FM receives, for a pension provider, per scheme the total pension assets at the start of the period.</p>
<p>In addition to the information at total level, the FM can also receive the pension assets per cohort. For example, for the age cohort 25-29 years, the total of the personal pension assets at the start can be received.</p>
<p>With the cohort information, the FM can, if desired, make a total calculation and test the reconciliation with the information supplied at total/collective level against the policy of the fund. This is useful for a robust handover and audit trail, depending on agreements the parties make. In accordance with the policy of the pension provider, rebalancing may be desirable in the event of (large) deviations. In addition to the FM, this information can, if desired, also be provided to the BA/asset service provider, so that it too is able to carry out testing and reporting activities using the leading investment administration.</p></td>
</tr>
<tr>
<th>SPR</th>
<td><p>2. Cashflow (0001b)</p>
<p>(4.2.1.3)</p></td>
<td>Cashflow/<br />
Cashflow</td>
<td><p>Inflow and outflow</p>
<p><strong>From 🡪 To</strong></p>
<p>From PUO to FM and BA/asset service provider.</p>
<p>On a periodic (expected to be monthly) basis, the FM receives, for a pension provider, per scheme the inflow in the period and the outflow. In addition to total level, inflow and outflow can also be supplied per cohort.</p>
<p>Besides premiums, value transfers and benefit payments, the inflow and outflow also contain the shifts between cohorts, where applicable. A cohort can also be a year of birth. The ‘cohort’ solidarity reserve, the ‘cohort’ compensation deposit and possibly other reserves will also be included.</p>
<p>With the cohort information, the FM can, if desired, make a total calculation and test the reconciliation with the information supplied at total/collective level against the policy of the fund. This is useful for a robust handover and audit trail, depending on agreements the parties make. In addition to the FM, this information can, if desired, also be provided to the BA/asset service provider, so that it too is able to carry out testing and reporting activities using the leading investment administration.</p></td>
</tr>
<tr>
<th>SPR</th>
<td><p>3. Pension Projection (0001c)</p>
<p>(4.2.1.3)</p></td>
<td>Pensioenprojectie/<br />
PensionProjection</td>
<td><p>Projected benefits</p>
<p><strong>From 🡪 To</strong></p>
<p>From PUO to FM, BA/asset service provider and LDI manager (see Figure 1, flow 1c, and Figures 8 and 9, steps F and G).</p>
<p>On a periodic (the expectation is monthly) basis, the FM receives from a pension provider, per scheme and per cohort, the projected benefits based on the accrued assets for future periods.</p>
<p>The data exchange also contains the cash flows to be hedged per scheme per future period. This is equal to the sum of the weighted projected benefits per cohort. The weighting factor is equal to the protection percentage per cohort. In this way a profile of the cash flows to be hedged is created. This exchange avoids misunderstandings regarding the cash flows to be hedged and can, if desired, introduce a check into the process.</p></td>
</tr>
<tr>
<th>SPR</th>
<td><p>4. Return Information (00002)</p>
<p>(4.2.2.)</p></td>
<td>Rendementsinformatie/<br />
ReturnOnInvestment</td>
<td><p>Information need of the PUO</p>
<p><strong>From 🡪 To</strong></p>
<p>Information flow from BA/asset service provider to the PUO.</p>
<p>To carry out the Solidarity Premium Scheme, the PUO periodically (expected to be monthly) needs information about the return achieved.</p>
<p>Periodically, the PUO receives over the period, for a pension provider, per scheme and per portfolio, the value at the start of the period, the value at the end of the period and the return in portfolio currency and (where applicable) expressed as a percentage. The PUO is responsible for allocating returns to participants on the basis of portfolio returns. Optionally, pension assets, protection return and excess return can also be shared with the PUO per cohort in the scheme. Whether these optional elements are exchanged depends on the agreed roles and responsibilities between the cooperating parties.</p>
<p>The principle is that the PUO is responsible for allocating returns, in accordance with the allocation rules set by the pension provider, to the personal pension assets of participants, the solidarity reserve, any compensation deposit and possibly other reserves.</p></td>
</tr>
<tr>
<th>FPR</th>
<td><p>5. Order Instruction (00541)</p>
<p>(5.4.1.)</p></td>
<td>Orderopdracht/<br />
Trade</td>
<td><p><strong>From 🡪 To</strong></p>
<p>Information flow from PUO to BA (see Figures 8 and 9, step A).</p>
<p>This is the minimum set of data needed to be able to send an order to an order-processing party. It can also be used to carry out a switch.</p>
<p>The PUO submits orders at the level of the investment product. The provider of the product carries out the ordering in the underlying investments itself. This may concern, among other things, listed and illiquid investments.</p></td>
</tr>
<tr>
<th>FPR</th>
<td><p>6. Order Confirmation (00542)</p>
<p>(5.4.2.)</p></td>
<td>Orderconfirmation</td>
<td><p><strong>From 🡪 To</strong></p>
<p>Information flow from BA to PUO (see Figures 8 and 9, step B).</p>
<p>The confirmation data of the order come back from the order-processing party to the PUO.</p></td>
</tr>
<tr>
<th>FPR</th>
<td><p>10. Control Information Investment Pools (00553)</p>
<p>(5.5.3)</p></td>
<td><p>Stuurinformatie</p>
<p>Beleggingspools/<br />
ControlInformationInvestmentPools</p></td>
<td><p>Information for controlling investment pools</p>
<p><strong>From 🡪 To</strong></p>
<p>From BA to FM (see Figures 8 and 9, step E). The PUO sends it only when it fulfils the role of BA itself.</p>
<p>The BA calculates the participation values of active age groups and combines these values with the specified changes to estimate the cash effects on the investment pools. The control information on the investment pool (with substantiation) is sent to the FM in the following format.</p></td>
</tr>
<tr>
<th>FPR</th>
<td><p>13. Value Information Investment Pool (00555b)</p>
<p>(5.5.5)</p></td>
<td>Waarde-informatie Beleggingspool/<br />
ValueAmountInvestmentPool</td>
<td><p>Passing on values per investment pool</p>
<p><strong>From 🡪 To</strong></p>
<p>Information flow from BA to PUO (see Figures 8 and 9, steps C and J).</p>
<p>The BA calculates the unit value per unit in the investment pool and passes it on, together with the value per investment pool, to the PUO.</p>
</td>
</tr>
<tr>
<th>FPR</th>
<td><p>14. Payment Information (00556)</p>
<p>(5.5.6)</p></td>
<td>Betaalinformatie/<br />
PaymentDetailsCreditor</td>
<td><p>Payment instructions for withdrawals</p>
<p><strong>From 🡪 To</strong></p>
<p>Information flow from BA to FM, at the beginning of the month (see Figures 8 and 9, step L). The PUO sends it only when it fulfils the role of BA itself.</p>
<p>The BA sends the payment instruction for withdrawals to the FM.</p></td>
</tr>
<tr>
<th>FPR</th>
<td><p>15. Corporate Actions (00557)</p></td>
<td>Corporate Actions/<br />
CorporateActions</td>
<td><p>Passing on corporate action events on investment products</p>
<p><strong>From 🡪 To</strong></p>
<p>Information flow from the asset management chain to the PUO.</p>
<p>Message 15 is used to pass on corporate action events on investment products from the asset management chain to the PUO. The message is intended for situations in which such events are processed within the asset management administration, but are not automatically visible within the administration of the PUO.</p></td>
</tr>
<tr>
<th>SPR/ FPR</th>
<td>Feedback Message</td>
<td>Feedback Message/<br />
Feedback</td>
<td><p>Reporting of errors or confirmation of processability.</p>
<p><strong>From 🡪 To</strong></p>
<p>The receiver of the substantive message, messages 1 to 15, is the sender of the feedback message.</p></td>
</tr>
</tbody>
</table>

### 6.4.1 Base Message

The base structure for messages (transaction) shows the hierarchical relationships between different entities in the data model. The entities and entity types form a coherent hierarchy. By definition, a hierarchy must be applied in the messages to be exchanged, and the structure of the transaction forms the basis for this. Among other things, the structure indicates which child entity belongs to which parent entity.

The column "Cardinality" shows the minimum and maximum number of times that entity can occur. V (mandatory, Dutch *verplicht*) or O (optional) indicates whether an entity.entitytype must or may occur.

The base message is a **generalisation** over the individual messages and not a message in itself. It shows every position in the hierarchy that occurs in at least one message. An entity that can occur in more than one position therefore appears more than once, each time under its own parent entity: `financialTransaction.payment` occurs directly under the scheme, under the cohort and under the investment portfolio. Not every message has every position. Which positions a message contains, and with which cardinality, is shown in the message structure of that message (§6.4.2 onwards); this may differ from this table.

From the table below it can be derived, for example, that:

1)  Per party.sender, multiple party.contact are possible



2)  Per party.pensionProvider, one or more pension.schemes occur

3)  Per pension.scheme, exactly one financialInformation.reportingPeriod occurs; message 15 has no reporting period (§6.4.11)

| Entity.entitytype | Cardinality |
|---|---|
| commonTechnical.default | 1..1, V |
| &nbsp;&nbsp;&nbsp;&nbsp;party.sender | 1..1, V |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;party.contact | 0..\*, O |
| &nbsp;&nbsp;&nbsp;&nbsp;party.receiver | 1..1, V |
| commonFunctional.default | 1..1, V |
| party.pensionProvider | 1..1, V |
| &nbsp;&nbsp;&nbsp;&nbsp;pension.scheme | 1..\*, V |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;financialInformation.reportingPeriod | 1..1, V |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;pension.cohort | 0..\*, O |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;investment.portfolio | 0..\*, O |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;financialTransaction.payment | 0..\*, O |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;investment.portfolio | 0..\*, O |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;financialTransaction.cashflow | 1..1, V |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;financialTransaction.payment | 0..\*, O |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;financialTransaction.cashflow | 0..1, O |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;financialTransaction.payment | 1..\*, V |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;party.creditor | 1..1, V |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;investment.investmentDetails | 1..\*, V |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;financialTransaction.trade | 1..\*, V |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;investment.corporateAction | 1..\*, V |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;investment.pool | 1..\*, V |
| document.default | 0..\*, O |
| chunking.default | 0..1, O |
| error.default | 0..\*, O |

<u>  
</u>

<u>NB. In the technical implementation, the number of repetitions (\*) is limited. See the overview below:</u>


<table>
<colgroup>
<col style="width: 70%" />
<col style="width: 29%" />
</colgroup>
<thead>
<tr>
<th><strong>Entity.entitytype</strong></th>
<th style="text-align: right;"><strong>Maximum number of<br />
iterations</strong></th>
</tr>
</thead>
<tbody>
<tr>
<th>commonTechnical.default</th>
<td style="text-align: right;">1</td>
</tr>
<tr>
<th>party.sender</th>
<td style="text-align: right;">1</td>
</tr>
<tr>
<th>party.contact</th>
<td style="text-align: right;">9</td>
</tr>
<tr>
<th>party.receiver</th>
<td style="text-align: right;">1</td>
</tr>
<tr>
<th>commonFunctional.default</th>
<td style="text-align: right;">1</td>
</tr>
<tr>
<th>party.pensionProvider</th>
<td style="text-align: right;">1</td>
</tr>
<tr>
<th>pension.scheme</th>
<td style="text-align: right;">999</td>
</tr>
<tr>
<th>financialInformation.reportingPeriod</th>
<td style="text-align: right;">1</td>
</tr>
<tr>
<th>party.creditor</th>
<td style="text-align: right;">1</td>
</tr>
<tr>
<th>financialTransaction.cashflow</th>
<td style="text-align: right;">1</td>
</tr>
<tr>
<th>financialTransaction.payment</th>
<td style="text-align: right;">999, 9999 or 99999<a href="#fn1" class="footnote-ref" id="fnref1" role="doc-noteref"><sup>1</sup></a></td>
</tr>
<tr>
<th>pension.cohort</th>
<td style="text-align: right;">99999</td>
</tr>
<tr>
<th>investment.pool</th>
<td style="text-align: right;">99</td>
</tr>
<tr>
<th>investment.portfolio</th>
<td style="text-align: right;">99</td>
</tr>
<tr>
<th>investment.investmentDetails</th>
<td style="text-align: right;">999</td>
</tr>
<tr>
<th>investment.corporateAction</th>
<td style="text-align: right;">99</td>
</tr>
<tr>
<th>financialTransaction.trade</th>
<td style="text-align: right;">99</td>
</tr>
<tr>
<th>error.default</th>
<td style="text-align: right;">99</td>
</tr>
<tr>
<th>document.default</th>
<td style="text-align: right;">99</td>
</tr>
<tr>
<th>chunking.default</th>
<td style="text-align: right;">1</td>
</tr>
</tbody>
</table>
<section id="footnotes" class="footnotes footnotes-end-of-document" role="doc-endnotes">
<hr />
<ol>
<li id="fn1"><p>The maximum number of financialTransaction.payment depends on the position in the message: under pension.scheme 99999 in message 3 and 999 in message 14; under pension.cohort and under investment.portfolio 9999 (message 3).<a href="#fnref1" class="footnote-back" role="doc-backlink">↩︎</a></p></li>
</ol>
</section>

**APF ring-fenced compartments: two common scenarios**

For a General Pension Fund (APF) with multiple ring-fenced compartments (kringen), there is one `pension.scheme` per ring-fenced compartment under one `party.pensionProvider`. Two scenarios exist side by side in the market:

**Scenario 1 — Ring-fenced compartment has its own PUV code**
Each ring-fenced compartment is identified by its own `puvCode` in `party.pensionProvider`. Buffer capital above ring-fenced compartment level is handled pragmatically through a cohort construction, because no separate PUV code exists for it.

**Scenario 2 — Ring-fenced compartment has no PUV code of its own**
There is one PUV code at APF/provider level. The distinction between ring-fenced compartments runs via references at `pension.scheme` level.

Both scenarios are supported by the standard. Parties lay down the chosen approach in agreements between chain parties (TOM / SLA). See GitHub issue [#114](https://github.com/Stichting-SIVI/VBPUOdsk/issues/114).

<span id="_Ref153871056" class="anchor"></span>

### 6.4.2 Message Structure 1. Assets (0001a)

See also [3.2.1](../chapter-3-spr-processes/#321-message-1-assets-1a).

<iframe
  src="../assets/berichtstructuur-01-vermogen.html"
  width="100%"
  height="380"
  style="border: 1px solid #ddd; border-radius: 4px; display: block;"
  title="Message structure 1. Assets (0001a)">
</iframe>
<p style="font-size: 11px; margin-top: 4px;"><a href="../assets/berichtstructuur-01-vermogen.html" target="_blank">Open table in full screen</a></p>

### 6.4.3 Message Structure 2. Cashflow (0001b)

See also [3.2.2](../chapter-3-spr-processes/#322-message-2-cashflow-1b-inflow-and-outflow) and, for FPR use, [4.3.2](../chapter-4-fpr-processes/#432-message-2-cashflow-0001b).

<iframe
  src="../assets/berichtstructuur-02-cashflow.html"
  width="100%"
  height="380"
  style="border: 1px solid #ddd; border-radius: 4px; display: block;"
  title="Message structure 2. Cashflow (0001b)">
</iframe>
<p style="font-size: 11px; margin-top: 4px;"><a href="../assets/berichtstructuur-02-cashflow.html" target="_blank">Open table in full screen</a></p>

### 6.4.4 Message Structure 3. Pension Projection (0001c)

See also [3.2.3](../chapter-3-spr-processes/#323-message-3-pension-projection-1c-projected-benefits).

See also, for FPR use, [4.3.3](../chapter-4-fpr-processes/#433-message-3-pension-projection-0001c), and for the routes in messages 2, 3 and 4 [3.2.5](../chapter-3-spr-processes/#325-spr-and-fpr-route-in-messages-2-3-and-4).

<iframe
  src="../assets/berichtstructuur-03-pensioenprojectie.html"
  width="100%"
  height="380"
  style="border: 1px solid #ddd; border-radius: 4px; display: block;"
  title="Message structure 3. Pension Projection (0001c)">
</iframe>
<p style="font-size: 11px; margin-top: 4px;"><a href="../assets/berichtstructuur-03-pensioenprojectie.html" target="_blank">Open table in full screen</a></p>

### 6.4.5 Message Structure 4. Return Information (00002)

See also, for FPR use, [4.3.4](../chapter-4-fpr-processes/#434-message-4-return-information-00002).

See also [3.2.4](../chapter-3-spr-processes/#324-message-4-return-information-2-information-need-of-the-puo).

<iframe
  src="../assets/berichtstructuur-04-rendementsinformatie.html"
  width="100%"
  height="380"
  style="border: 1px solid #ddd; border-radius: 4px; display: block;"
  title="Message structure 4. Return Information (00002)">
</iframe>
<p style="font-size: 11px; margin-top: 4px;"><a href="../assets/berichtstructuur-04-rendementsinformatie.html" target="_blank">Open table in full screen</a></p>

### 6.4.6 Message Structure 5. Order Instruction (00541)

See also [4.2](../chapter-4-fpr-processes/#42-the-fpr-model) &amp; [4.3.5](../chapter-4-fpr-processes/#435-message-5-order-instruction-00541).

<iframe
  src="../assets/berichtstructuur-05-orderopdracht.html"
  width="100%"
  height="380"
  style="border: 1px solid #ddd; border-radius: 4px; display: block;"
  title="Message structure 5. Order Instruction (00541)">
</iframe>
<p style="font-size: 11px; margin-top: 4px;"><a href="../assets/berichtstructuur-05-orderopdracht.html" target="_blank">Open table in full screen</a></p>

### 6.4.7 Message Structure 6. Order Confirmation (00542)

See also [4.2](../chapter-4-fpr-processes/#42-the-fpr-model) &amp; [4.3.6](../chapter-4-fpr-processes/#436-message-6-order-confirmation-00542).

<iframe
  src="../assets/berichtstructuur-06-orderconfirmation.html"
  width="100%"
  height="380"
  style="border: 1px solid #ddd; border-radius: 4px; display: block;"
  title="Message structure 6. Order Confirmation (00542)">
</iframe>
<p style="font-size: 11px; margin-top: 4px;"><a href="../assets/berichtstructuur-06-orderconfirmation.html" target="_blank">Open table in full screen</a></p>

The following fields under `financialTransaction.trade` have been changed from mandatory to optional: `tradeQuantity`, `tradePrice`, `counterparty`, `broker`, `interestAmount`, `commissionAmount`, `clearingBroker` and `clearingBrokerCashAccount`. `tradeAmount` remains mandatory. See GitHub issue [#105](https://github.com/Stichting-SIVI/VBPUOdsk/issues/105).

### 6.4.8 Message Structure 10. Control Information Investment Pools (00553)

From release 2027, the `cohortPool` layer has been removed from this message; the data land directly at `investment.pool` level. See GitHub issue [#124](https://github.com/Stichting-SIVI/VBPUOdsk/issues/124).

In addition, the following fields of entity `investment.pool` have been removed from message 00553: `dummyCashId`, `tradeQuantity`, `unitPrice` and `currencyExchangeRate`. The fields `buySellId`, `tradeValueAmount` and `currencyType` remain active. See GitHub issue [#133](https://github.com/Stichting-SIVI/VBPUOdsk/issues/133).

See also [4.2](../chapter-4-fpr-processes/#42-the-fpr-model) &amp; [4.3.7](../chapter-4-fpr-processes/#437-message-10-control-information-investment-pools-00553).

<iframe
  src="../assets/berichtstructuur-10-stuurinformatiebeleggingspools.html"
  width="100%"
  height="380"
  style="border: 1px solid #ddd; border-radius: 4px; display: block;"
  title="Message structure 10. Control Information Investment Pools (00553)">
</iframe>
<p style="font-size: 11px; margin-top: 4px;"><a href="../assets/berichtstructuur-10-stuurinformatiebeleggingspools.html" target="_blank">Open table in full screen</a></p>

### 6.4.9 Message Structure 13. Value Information Investment Pool (00555b)

See also [4.2](../chapter-4-fpr-processes/#42-the-fpr-model) &amp; [4.3.8](../chapter-4-fpr-processes/#438-message-13-value-information-investment-pool-00555b).

<iframe
  src="../assets/berichtstructuur-13-waarde-informatie-beleggingspool.html"
  width="100%"
  height="380"
  style="border: 1px solid #ddd; border-radius: 4px; display: block;"
  title="Message structure 13. Value Information Investment Pool (00555b)">
</iframe>
<p style="font-size: 11px; margin-top: 4px;"><a href="../assets/berichtstructuur-13-waarde-informatie-beleggingspool.html" target="_blank">Open table in full screen</a></p>

### 6.4.10 Message Structure 14. Payment Information (00556)

See also [4.2](../chapter-4-fpr-processes/#42-the-fpr-model) &amp; [4.3.9](../chapter-4-fpr-processes/#439-message-14-payment-information-00556).

<iframe
  src="../assets/berichtstructuur-14-betaalinformatie.html"
  width="100%"
  height="400"
  style="border: 1px solid #ddd; border-radius: 4px; display: block;"
  title="Message structure 14. Payment Information (00556)">
</iframe>
<p style="font-size: 11px; margin-top: 4px;"><a href="../assets/berichtstructuur-14-betaalinformatie.html" target="_blank">Open table in full screen</a></p>


### 6.4.11 Message Structure 15. Corporate Actions (00557)

<iframe
  src="../assets/berichtstructuur-15-corporate-actions.html"
  width="100%"
  height="380"
  style="border: 1px solid #ddd; border-radius: 4px; display: block;"
  title="Message structure 15. Corporate Actions (00557)">
</iframe>
<p style="font-size: 11px; margin-top: 4px;"><a href="../assets/berichtstructuur-15-corporate-actions.html" target="_blank">Open table in full screen</a></p>

### 6.4.12 Message Structure Feedback Message

See also [4.4](../chapter-4-fpr-processes/#44-feedback-message-resending).

<iframe
  src="../assets/berichtstructuur-feedback-message.html"
  width="100%"
  height="300"
  style="border: 1px solid #ddd; border-radius: 4px; display: block;"
  title="Message structure Feedback Message">
</iframe>
<p style="font-size: 11px; margin-top: 4px;"><a href="../assets/berichtstructuur-feedback-message.html" target="_blank">Open table in full screen</a></p>

Note:

- The initial message is not sent along with the feedback message.
- The feedback message **always** refers to the messageId (via **originalMessageId**) of the message to which the feedback message is a response and **may** refer to the messageType (via **originalMessageType**).

[^7]: Eindrapport onderzoek standaard VB PUO (september 2023.pdf. See: [SIVI/Downloads](https://www.sivi.org/pensioen/standaard-data-uitwisseling-vermogensbeheer-en-pensioenuitvoering/)

[^8]: [See: OAS (Open API Specification)](https://github.com/Stichting-SIVI/VBPUOdsk/tree/main/VBPUO%20OAS%20%28Open%20API%20Specificatie%29)
