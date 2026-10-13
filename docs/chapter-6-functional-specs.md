# 6 Functional Specifications

**This chapter sets out the functional specifications:**

- **Data dictionary;**

- **Base message;**

- **Cross-reference base message & messages.**

## 6.1 Data Dictionary

The data dictionary gives an overview of all entities and entity types used within this standard.

| **Entity.entitytype**                |
|--------------------------------------|
| commonTechnical.default              |
| party.sender                         |
| party.contact                        |
| party.receiver                       |
| commonFunctional.default             |
| party.pensionProvider                |
| pension.scheme                       |
| financialInformation.reportingPeriod |
| financialTransaction.payment         |
| party.creditor                       |
| financialTransaction.cashflow        |
| pension.cohort                       |
| investment.pool                      |
| investment.portfolio                 |
| investment.investmentDetails         |
| investment.corporateAction           |
| financialTransaction.trade           |
| error.default                        |
| document.default                     |
| chunking.default                     |

## 6.2 Entities and Entity Types

This section describes the various entities and the attributes within those entities.

Below is an explanation of the entities. This information is derived from AFD 2.0, which can be consulted via this [link](https://www.sivi.org/standaarden/sivi-all-finance-standaard/afd-online-2-0/).

Note: the entity type is mandatory.

<table>
<colgroup>
<col style="width: 40%" />
<col style="width: 59%" />
</colgroup>
<thead>
<tr>
<th>Entity.entitytype</th>
<th>Explanation</th>
</tr>
</thead>
<tbody>
<tr>
<th>commonTechnical.default</th>
<td>This entity contains technical details about sending and storing messages. It forms, as it were, the basis for the technical aspects within the messaging system.</td>
</tr>
<tr>
<th>party.sender</th>
<td>The entity "party.sender" refers to the sender of the message.</td>
</tr>
<tr>
<th>party.contact</th>
<td>The entity "party.contact" represents a contact person within a legal entity. These contact persons can be approached for further information about the message.</td>
</tr>
<tr>
<th>party.receiver</th>
<td>This entity represents the receiver of the message.</td>
</tr>
<tr>
<th>commonFunctional</th>
<td>This entity contains domain-specific information about the content of the message. It gives context and meaning to the functional details in the message.</td>
</tr>
<tr>
<th>party.pensionProvider</th>
<td><p>This entity represents a pension provider,</p>
<p>A pension provider is a pension fund, insurer or premium pension institution (PPI) with which pension is accrued for the employee by the employer.</p></td>
</tr>
<tr>
<th>pension.scheme</th>
<td>This entity contains data at the level of the pension scheme, or the pension plan or schema.</td>
</tr>
<tr>
<th>financialInformation.reportingPeriod</th>
<td>This entity relates to reporting periods, time intervals over which reporting takes place and other generic dates.</td>
</tr>
<tr>
<th>financialTransaction.payment</th>
<td>This combination of entity and entity type contains data about a payment.</td>
</tr>
<tr>
<th>party.creditor</th>
<td>This entity represents the creditor; the recipient of the payments, within the ecosystem in which the messages are exchanged.</td>
</tr>
<tr>
<th>financialTransaction.cashflow</th>
<td>This entity deals with financial transactions relating to pensions, specifically focused on cash flows.</td>
</tr>
<tr>
<th>financialTransaction.payment</th>
<td>This entity contains information about payments and future cash flows/payments.</td>
</tr>
<tr>
<th>pension.cohort</th>
<td>This entity contains information about specific target groups within the pension scheme.</td>
</tr>
<tr>
<th>investment.pool</th>
<td>This entity (investment pool) represents the collections of diverse underlying investments (liquid, illiquid, funds and mandates).</td>
</tr>
<tr>
<th>investment.portfolio</th>
<td>This entity relates to investment portfolios, which represent the total managed assets (or a sub-portfolio) within the collective.</td>
</tr>
<tr>
<th>investment.investmentDetails</th>
<td>This entity describes individual investments of a pension provider in shares or investment funds.</td>
</tr>
<tr>
<th>investment.corporateAction</th>
<td>This entity contains data about corporate action events on investment products, such as cash dividend, stock dividend, rebate, unit and capital shifts and product changes. The message is intended for passing on such events from the asset management chain to the PUO.</td>
</tr>
<tr>
<th>financialTransaction.trade</th>
<td>This entity relates to trading activities within the pension scheme.</td>
</tr>
<tr>
<th>error</th>
<td>In the case of errors in the system, this entity is used to generate error messages and to indicate exactly what went wrong.</td>
</tr>
<tr>
<th>document</th>
<td>This entity is intended for adding any attachments to messages.</td>
</tr>
<tr>
<th>chunking.default</th>
<td>This entity contains metadata for splitting large messages into partial messages and merging them again (chunking). If present, it indicates that the message is part of a larger logical message.</td>
</tr>
</tbody>
</table>

## 6.3 Attributes in Entities.Entity Types

In the tables in this section, the attributes are described per combination of entity and entity type. In addition to the attribute name, the description contains a definition of the attribute, the data type of the attribute, the intended maximum length of the data item and a reference (link) to any code list.

Note: the description of the attributes in the feedback message may differ from the description in the substantive messages.

The description of the data types used can be found in the [sivi-all-finance-standard manual](https://www.manula.com/manuals/sivi/sivi-all-finance-standard/1/en/topic/data-types-and-formats?q=string).

When interpreting the tables below, the following is important:

- Data type string: in the tables below, the maximum number of positions is stated for strings, unless reference is made to a code list or an enumeration. In those cases “length” is empty.

- Data type decimal: by default at most 2 decimal places (1E-2). Any exception is stated in the data type column.

The attribute names differ from the naming in the consultation document; they are now – partly – designed on the basis of the AFD 2.0 conventions. Appendix 8.4 contains the “Translation table of functional attributes to AFD2.0 attributes”.

**Use of `refKey`**

In the tables below, the attribute `refKey` occurs in almost every entity. This attribute serves as the unique identifier of an entity. The aim is that an entity can be reliably recognised and referred to within or between messages and files — just as an ISIN identifies an investment instrument without saying anything about the investment policy that applies to it.

`refKey` may be technically or functionally recognisable, but no classification, investment policy or business logic may be derived from it. The substantive classification belongs in the fields intended for that purpose (for example `reserveType`).

See GitHub issue [#111](https://github.com/Stichting-SIVI/VBPUOdsk/issues/111).

<!-- Generated by gen_html_assets.py — entities/attributes §6.3          -->
<!-- Integrate into chapter-6-functionele-specificaties.md               -->
<!-- Keep footnotes manually BETWEEN the entity blocks                   -->

<!-- Entity blocks generated by gen_html_assets.py from the model delivery.   -->
<!-- Explanations between and below the blocks belong to the documentation    -->
<!-- side and are re-applied on regeneration by scripts/integreer63.py.       -->

<div class="vbt-entiteit" id="entiteit-commontechnical-default">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">commonTechnical.default</span>
  <span class="vbt-titel-nr">[T1]</span>
</div>
<div class="vbt-omschrijving-rij">The commonTechnical entity covers all information about sending or storing the message. This is typically technical information.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>messageId</td><td>Unique message identification</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>creationDateTime</td><td>Creation date and time Date</td><td>timestamp</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>testMessage</td><td>Test message indicator</td><td>boolean</td><td class="vbt-td-c"></td><td></td></tr>
</tbody></table>
</div>

**Uniqueness of `messageId`**

The `messageId` is always unique across all messages, regardless of message type or period. Using the `messageId` to group or bundle messages is not allowed. Any relationship between messages is derived from substantive characteristics, such as the period to which the message relates.

The only exception is chunking (§7.6): chunks of the same logical message share the same `messageId`.

See GitHub issue [#108](https://github.com/Stichting-SIVI/VBPUOdsk/issues/108).

<div class="vbt-entiteit" id="entiteit-party-sender">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">party.sender</span>
  <span class="vbt-titel-nr">[T2]</span>
</div>
<div class="vbt-omschrijving-rij">Sender.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>refKey</td><td>Unique reference key assigned to an entity.</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>rsinNumber</td><td>Governmental identification number for legal entities and associations (RSIN)</td><td>string</td><td class="vbt-td-c">9</td><td></td></tr>
<tr><td>organizationName</td><td>Organisation name of the sender</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>applicationSenderName</td><td>Name of the application that created the message<a href="#fn-appsender" id="fnref-appsender"><sup>*</sup></a></td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
</tbody></table>

<p id="fn-appsender" style="font-size: 0.85em; margin-top: 0.5em;"><sup>*</sup> In AFD 2.0, applicationSendername is available under both party.sender and commonTechnical. This is indeed not apparent from the AFD 2.0 Online consultation documentation (as of April 2024). It was decided to place the attribute under party.sender for VBPUO. <a href="#fnref-appsender">↩︎</a></p>
</div>

<div class="vbt-entiteit" id="entiteit-party-contact">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">party.contact</span>
  <span class="vbt-titel-nr">[T3]</span>
</div>
<div class="vbt-omschrijving-rij">A natural person who can be contacted within a legal person for further information.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>emailWork</td><td>Work email address </td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>workPhoneNumber</td><td>Work phone number </td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="entiteit-party-receiver">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">party.receiver</span>
  <span class="vbt-titel-nr">[T4]</span>
</div>
<div class="vbt-omschrijving-rij">Receiver.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>refKey</td><td>Unique reference key assigned to an entity.</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>rsinNumber</td><td>Governmental identification number for legal entities and associations (RSIN)</td><td>string</td><td class="vbt-td-c">9</td><td></td></tr>
<tr><td>organizationName</td><td>Name of the receiver(s) (organisation(s))</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="entiteit-commonfunctional-default">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">commonFunctional.default</span>
  <span class="vbt-titel-nr">[T5]</span>
</div>
<div class="vbt-omschrijving-rij">The commonFunctional entity covers all information about the content of the message. This is typically domain-specific information.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>function</td><td>Message function code.</td><td>string</td><td class="vbt-td-c"></td><td>ADNFUN (01; 02;09;54 or 23)</td></tr>
<tr><td>statusType</td><td>Status of the proccessing of the original message for which the status and/or errors are being sent to the Feedback endpoint. Message statuses are either &#x27;Accepted (8 - Geaccepteerd)&#x27; or &#x27;Not Accepted (0 - Afgewezen).</td><td>string</td><td class="vbt-td-c"></td><td>ADNSTS (0; 8)</td></tr>
<tr><td>afdDefinitionName</td><td>Message type</td><td>string</td><td class="vbt-td-c">80</td><td></td></tr>
<tr><td>afdDefinitionVersion</td><td>Version of the standard</td><td>string</td><td class="vbt-td-c">80</td><td></td></tr>
<tr><td>originalMessageId</td><td>The original messageId of the message that is replaced by this message</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>originalMessageType</td><td>Message type of the original request to which this message is a response. For example: 0001a from “Message Structure 1. Assets (0001a)”</td><td>string</td><td class="vbt-td-c"></td><td>0001a; 0001b; 0001c; 00002; 00541; 00542; 00553; 00555b; 00556; 00557</td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="entiteit-party-pensionprovider">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">party.pensionProvider</span>
  <span class="vbt-titel-nr">[T6]</span>
</div>
<div class="vbt-omschrijving-rij">Information on pensionprovider Level</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>puvCode</td><td>ID of the pension provider (PUV code) / Unique reference key assigned to an entity.</td><td>string</td><td class="vbt-td-c"></td><td>AFDIDP (U0003; U0005; ... ;U0765)</td></tr>
<tr><td>rsinNumber</td><td>Governmental identification number for legal entities and associations (RSIN)</td><td>string</td><td class="vbt-td-c">9</td><td></td></tr>
<tr><td>organizationName</td><td>Name of the pension provider</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
</tbody></table>
</div>

For APFs with multiple ring-fenced compartments (kringen), there are two common scenarios for the use of PUV codes. See the explanation of the [base message in §6.4.1](../chapter-6-4-messages/#641-base-message).

<div class="vbt-entiteit" id="entiteit-pension-scheme">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">pension.scheme</span>
  <span class="vbt-titel-nr">[T7]</span>
</div>
<div class="vbt-omschrijving-rij">Data on pension scheme level</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>refKey</td><td>ID of the pension scheme / (Unique reference key assigned to an entity.)</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>pensionSchemeName</td><td>Name of the pension scheme</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>startAmount</td><td>Total pension assets as at the start date</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>tradingPortfolioId</td><td>Portfolio ID of the custodian (safekeeping and administration of financial assets)</td><td>string</td><td class="vbt-td-c">10</td><td></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="entiteit-financialinformation-reportingperiod">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">financialInformation.reportingPeriod</span>
  <span class="vbt-titel-nr">[T8]</span>
</div>
<div class="vbt-omschrijving-rij">Reportingperiod Information</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>startDate</td><td>Start date of the data period on which the delivery from the PUO is based, or reference date</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>endDate</td><td>End date of the data period on which the delivery from the PUO is based</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>endDate</td><td>End date of the data period over which return is reported</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>tradeDate</td><td>Desired trade date</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>investmentOrderSettlementDate</td><td>Date by which the full cycle of the investment order must have been settled</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>projectionDate</td><td>Date of the projection of pension benefits</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>instructionDate</td><td>Instruction date (date of the order sent by the PUO)</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>participationValuationDate</td><td>Price date of the net asset value (NAV) per unit of the investment pool, as determined by the investment administrator.</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>valueDate</td><td>Currency date.</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
</tbody></table>
</div>

**Date conventions for startDate and projectionDate**

To prevent inconsistent use of dates between chain parties, the standard applies the following convention:

| Field | Message | Convention | Example |
|------|---------|-----------|-----------|
| startDate | Message 1 (Assets) | Last day of the preceding month | 31-01-2025 |
| projectionDate | Message 3 (Pension Projection) | Last day of the preceding month | 31-01-2025 |
| firstExpectedPaymentDate | Message 3 (Pension Projection) | First day of the current month | 01-02-2025 |

This approach provides clarity and predictability in the chain. See GitHub issue [#94](https://github.com/Stichting-SIVI/VBPUOdsk/issues/94).

<div class="vbt-entiteit" id="entiteit-financialtransaction-payment">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">financialTransaction.payment</span>
  <span class="vbt-titel-nr">[T9]</span>
</div>
<div class="vbt-omschrijving-rij">Information about payments.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>amount</td><td>Amount in currency</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>currencyType</td><td>Currency</td><td>string</td><td class="vbt-td-c"></td><td>ISOVAL (EUR; USD; …)</td></tr>
<tr><td>collectionAccountIban</td><td>IBAN of the debit account</td><td>string</td><td class="vbt-td-c">34</td><td></td></tr>
<tr><td>description</td><td>Description of the transaction (payment)</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>refKey</td><td>ID of the expected payment</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>expectedPensionPaymentDate</td><td>Pension benefit payment date</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>amount</td><td>Projected benefit across all cohorts</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>hedgedExpectedPensionPaymentAmount</td><td>Cash flow to be hedged across all cohorts</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>amount</td><td>Projected benefit </td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>hedgedExpectedPensionPaymentAmount</td><td>Cash flow to be hedged</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
</tbody></table>

Field length of `collectionAccountIban` corrected from 10 to 34 (international maximum IBAN length in accordance with ISO 13616). See GitHub issue [#135](https://github.com/Stichting-SIVI/VBPUOdsk/issues/135).
</div>

<div class="vbt-entiteit" id="entiteit-party-creditor">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">party.creditor</span>
  <span class="vbt-titel-nr">[T10]</span>
</div>
<div class="vbt-omschrijving-rij">The party that has a claim.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>refKey</td><td>Unique reference key assigned to an entity.</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>collectionAccountIban</td><td>IBAN of the credit account per scheme</td><td>string</td><td class="vbt-td-c">34</td><td></td></tr>
<tr><td>collectionAccountInNameOf</td><td>Name of the counterparty per scheme</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>collectionAccountBic</td><td>Business Identifier Code (BIC) per scheme</td><td>string</td><td class="vbt-td-c">10</td><td></td></tr>
<tr><td>collectionAccountBicCorrespondent</td><td>BIC correspondent per scheme</td><td>string</td><td class="vbt-td-c">10</td><td></td></tr>
</tbody></table>

Field length of `collectionAccountIban` corrected from 10 to 34. See GitHub issue [#135](https://github.com/Stichting-SIVI/VBPUOdsk/issues/135).
</div>

<div class="vbt-entiteit" id="entiteit-financialtransaction-cashflow">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">financialTransaction.cashflow</span>
  <span class="vbt-titel-nr">[T11]</span>
</div>
<div class="vbt-omschrijving-rij">The sum of contributions and withdrawals on all cohorts</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>contributionAmount</td><td>Sum of contributions</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>contributionDate</td><td>Date of receipt of the contributions</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>withdrawalAmount</td><td>Sum of the outflow</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>withdrawalDate</td><td>Date on which (at the latest) the liquidity for the withdrawal has been made available</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>netAmount</td><td>Sum of contributions and withdrawals per scheme (net). A negative amount is a (net) withdrawal. / Difference between contributions and withdrawals. A negative amount is a (net) withdrawal.)</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>netDate</td><td>The value date on which the netted cash flow amount (contributions minus withdrawals) is actually paid by the PUO to, or received by the PUO from, the asset manager</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>netAmount</td><td>Netted cash flow amount per investment portfolio within a scheme. A negative amount is a net withdrawal.</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>netDate</td><td>The value date on which the net cash flow amount per investment portfolio is actually paid by the PUO to, or received by the PUO from, the asset manager</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
</tbody></table>
</div>

**Field usage in `financialTransaction.cashflow`**

In the SPR context, `financialTransaction.cashflow` is used directly under `pension.scheme`. The entity itself is optional, but if it occurs, `netAmount` and `netDate` are mandatory; the fields for inflow and outflow are optional (see §6.3.1).

In the FPR context, the `financialTransaction.cashflow` entity is used under `investment.portfolio` and `netAmount` and `netDate` are mandatory.

<div class="vbt-entiteit" id="entiteit-pension-cohort">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">pension.cohort</span>
  <span class="vbt-titel-nr">[T12]</span>
</div>
<div class="vbt-omschrijving-rij">Information on cohort (pension target audience) level</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>refKey</td><td>ID of the cohort</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>description</td><td>Description of the cohort</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>participationStatus</td><td>Status of the participants in a cohort</td><td>string</td><td class="vbt-td-c"></td><td>ADNDNS (16; 20; 35; 40; 70; 80)</td></tr>
<tr><td>startAge</td><td>Start age in months</td><td>integer</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>endAge</td><td>End age in months</td><td>integer</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>reserveIndicator</td><td>Indicator of whether the cohort reflects a reserve</td><td>boolean</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>reserveType</td><td>Choice of the type of (reserve, in fact a) provision / type of provision. Where the investment policy is shared, consolidation is possible; an explicit code only for a separate investment policy.</td><td>string</td><td class="vbt-td-c"></td><td>AFDRES (1; 2; 3; 4; 5; 6; 7; 8; 9; 10; 11; 12; 13; 14; 15; 99)</td></tr>
<tr><td>reserveDescription</td><td>Description of the reserve when &quot;Other&quot; is chosen in reserve type.</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>startAmount</td><td>Pension assets of the cohort as at the start date</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>netAmount</td><td>Sum of contributions and withdrawals per cohort. A negative amount is a (net) withdrawal.)</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>netDate</td><td>The value date on which the netted cash flow amount for the cohort is actually paid by the PUO to, or received by the PUO from, the asset manager</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>contributionAmount</td><td>Inflow to be invested by the fiduciary manager</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>withdrawalAmount</td><td>Outflow to be invested by the fiduciary manager</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>protectionReturnPercentage</td><td>The protection return achieved, as a percentage, over the data period per scheme and per cohort</td><td>decimal (1E-12)</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>excessReturnPercentage</td><td>The excess return achieved, as a percentage, over the data period per scheme and per cohort </td><td>decimal (1E-12)</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>protectionReturnAmount</td><td>The protection return achieved, in the currency of the scheme, over the data period per scheme and per cohort</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>excessReturnAmount</td><td>The excess return achieved, in the currency of the scheme, over the data period per scheme and per cohort</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
</tbody></table>
</div>

**Age cohorts: standard set-up**

The standard set-up uses annual age cohorts. This means that, in principle, a difference of 12 months is applied between two consecutive `startAge` values: `startAge` is a multiple of 12 (0, 12, 24, ...) and `endAge` = `startAge` + 11. Smaller steps (for example monthly) are not excluded, but the annual division serves as the reference model. See GitHub issue [#111](https://github.com/Stichting-SIVI/VBPUOdsk/issues/111).


**Cohorts with value 0**
{: #cohorten-met-waarde-0 }

For all messages with cohorts (messages 1 to 4), the following applies: a cohort with value 0 may be sent with the value `0` or be omitted. Sending it makes the distinction visible between "the value is 0" and "the cohort is missing"; omitting it keeps the message compact. Parties must be able to process both. What the absence of a cohort means is laid down by chain parties in their agreements (TOM/SLA). For large messages, the [chunking mechanism](../chapter-7-6-chunking/#761-fundamental-principles-of-chunking) can offer a solution. See GitHub issue [#100](https://github.com/Stichting-SIVI/VBPUOdsk/issues/100).

This also applies to cohorts that represent a reserve or provision (`reserveIndicator` = true). Omitting a reserve therefore does not automatically mean that the value is 0.

The standard has no separate representation for "nothing to report": parties use the value `0` for this or omit the cohort. The standard does not recognise a field without a value (in JSON: `null`): a field is delivered with a value, or it is omitted.


**Reserves and provisions: division of roles between fields**


**Consistency check.** If `reserveIndicator` = true, `reserveType` is mandatory. `reserveDescription` is desirable for `reserveType` 99 (Other) and possible for the other codes. Both fields are optional in the model; the obligation for `reserveType` follows from this rule. The reserve fields are only on `pension.cohort`, not on `investment.portfolio`.


For cohorts that represent a reserve or provision (`reserveIndicator` = true), the following division of roles applies:

- **`reserveType`** (code list AFDRES) is the substantive classification and the exclusive key for the investment policy. Reserves or provisions with a different investment policy require a different `reserveType` value. As of release 2027, the code list has been extended with codes 9 to 15. Where the investment policy is shared, consolidation is possible; an explicit code is only needed for a separate investment policy. This applies to both SPR and FPR. See GitHub issue [#134](https://github.com/Stichting-SIVI/VBPUOdsk/issues/134).
- **`reserveDescription`** is purely descriptive. The description may explain or clarify, but does not determine classification, routing or investment policy.
- **`refKey`** uniquely identifies the cohort (see the general explanation of `refKey` above). Multiple cohorts with the same `reserveType` are permitted, provided they fall under the same investment policy.

See GitHub issue [#111](https://github.com/Stichting-SIVI/VBPUOdsk/issues/111).

<div class="vbt-entiteit" id="entiteit-investment-portfolio">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">investment.portfolio</span>
  <span class="vbt-titel-nr">[T13]</span>
</div>
<div class="vbt-omschrijving-rij">Investment portfolio</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>refKey</td><td>Investment portfolio ID / Unique reference key assigned to an entity.</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>description</td><td>Description</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>startExposureAmount</td><td>The allocation of the pension assets per cohort to a specific investment portfolio, calculated on the basis of the allocation rules as applied by the PUO.)</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>startExposurePercentage</td><td>The relative share of startExposureAmount in relation to the total pension assets as at the date.)</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>startAmount</td><td>The value of the Total Market Value at the start of the data period</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>netAmount</td><td>Sum of contributions and withdrawals per scheme (net). A negative amount is a (net) withdrawal</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>endAmount</td><td>The value of the Total Market Value at the end of the data period. Per scheme and investment portfolio</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>returnPercentage</td><td>The return achieved, as a percentage, over the data period per scheme and per investment portfolio</td><td>decimal (1E-12)</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>returnAmount</td><td>The return achieved, in the currency of the scheme, over the data period per scheme and per investment portfolio</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="entiteit-investment-pool">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">investment.pool</span>
  <span class="vbt-titel-nr">[T14]</span>
</div>
<div class="vbt-omschrijving-rij">Investment pool / investment portfolio</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>refKey</td><td>ID of the investment pool per scheme</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>description</td><td>Description</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>unitsSummedValueAmount</td><td>Value per investment pool (unit value)</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>preliminaryUnitValueAmount</td><td>The net asset value (NAV) per unit of the investment pool, as determined by the investment administrator</td><td>decimal (1E-06)</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>numberOfUnits</td><td>Number of units issued for the investment pool, </td><td>decimal (1E-06)</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>currencyType</td><td>Currency of the pool</td><td>string</td><td class="vbt-td-c"></td><td>ISOVAL (EUR; USD; …)</td></tr>
<tr><td>buySellId</td><td>Buy/sell indicator; ID for buy/sell per investment pool per scheme</td><td>string</td><td class="vbt-td-c"></td><td>sell; buy</td></tr>
<tr><td>tradeValueAmount</td><td>Transaction value per investment pool per scheme</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
</tbody></table>

`marketValueAmount` has been removed from the standard as of release 2027; the net asset value is expressed exclusively through `preliminaryUnitValueAmount`. The field name `preliminary` has historical origins and will be cleaned up in a future release. See GitHub issue [#128](https://github.com/Stichting-SIVI/VBPUOdsk/issues/128).
</div>

<div class="vbt-entiteit" id="entiteit-investment-investmentdetails">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">investment.investmentDetails</span>
  <span class="vbt-titel-nr">[T15]</span>
</div>
<div class="vbt-omschrijving-rij">An investment in both liquid (easily tradable) and illiquid (of limited tradability) funds or groups (pools) thereof.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>refKey</td><td>Identifier (for example ISIN or internal code)</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>description</td><td>The name of the investment / the official name of the fund / of the instrument</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>currencyType</td><td>Currency of the instrument </td><td>string</td><td class="vbt-td-c"></td><td>ISOVAL (EUR; USD; …)</td></tr>
<tr><td>numberOfUnits</td><td>Number of units purchased per instrument per scheme per investment portfolio</td><td>decimal (1E-06)</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>refKey</td><td>Identifier of the investment product, for example ISIN or internal code.</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>description</td><td>Description of the investment product.</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>tradeDate</td><td>trade date (intended)</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="entiteit-investment-corporateaction">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">investment.corporateAction</span>
  <span class="vbt-titel-nr">[T16]</span>
</div>
<div class="vbt-omschrijving-rij">A Corporate Action belonging to the investment product.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>refKey</td><td>Key of the Corporate Action.</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>description</td><td>Description of the Corporate Action.</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>corporateActionType</td><td>Type of Corporate Action.</td><td>string</td><td class="vbt-td-c"></td><td>AFDCOA (1; 2; 3; 99)</td></tr>
<tr><td>instructionDate</td><td>Instruction date of the Corporate Action.</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>tradeDate</td><td>Transaction date of the Corporate Action.</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>paymentDate</td><td>Payment date of the Corporate Action.</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>cashDividendTotalAmount</td><td>Total cash amount of the Corporate Action.</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>cashDividendPerUnitAmount</td><td>Cash amount per unit.</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>currencyType</td><td>Currency of the cash amount.</td><td>string</td><td class="vbt-td-c">3</td><td>ISOVAL (EUR; USD; GBP; CHF; JPY)</td></tr>
<tr><td>stockDividendPerUnitNumber</td><td>Stock dividend quantity per unit.</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>stockDividendTotalNumber</td><td>Total stock dividend quantity.</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>newProductName</td><td>Name of the new product.</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>newProductIdentifier</td><td>Identifier of the new product.</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="entiteit-financialtransaction-trade">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">financialTransaction.trade</span>
  <span class="vbt-titel-nr">[T17]</span>
</div>
<div class="vbt-omschrijving-rij">Trading/ ordering; Buying and selling</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>tradeDate</td><td>trade date (actual)</td><td>date</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>refKey</td><td>Unique reference key assigned to an entity.</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>adjustmentIndicator</td><td>Adjusted trade instruction</td><td>boolean</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>buySellId</td><td>Buy, sell or switch direction indicator</td><td>string</td><td class="vbt-td-c"></td><td>sell; buy; switchfrom; switchto</td></tr>
<tr><td>tradeAmount</td><td>Positive amount of the transaction in the currency in which the investment is denominated; direction follows from buySellId</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>tradeQuantity</td><td>Positive number of securities (units) to be traded in the transaction; direction follows from buySellId</td><td>decimal (1E-06)</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>tradePrice</td><td>Purchase price / quoted price</td><td>decimal (1E-06)</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>switchType</td><td>Switch type; one-day or sequential</td><td>string</td><td class="vbt-td-c"></td><td>AFDSWI (1; 2)</td></tr>
<tr><td>financialInformationRef</td><td>For switchfrom/switchto, refer here to the refKey of the other switch leg for the purpose of the consistency check.</td><td>array</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>counterparty</td><td>Transfer Agent; the party that carries out the purchase/sale</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>broker</td><td>Broker that executes investment orders on the market on behalf of clients</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>interestAmount</td><td>Amount of applicable interest</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>commissionAmount</td><td>Fee for executing the transaction</td><td>decimal</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>clearingBroker</td><td>Broker responsible for the administrative and financial settlement of the transaction</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>clearingBrokerCashAccount</td><td>Cash account (IBAN) at the clearing broker in the name of the pension provider</td><td>string</td><td class="vbt-td-c">18</td><td></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="entiteit-error-default">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">error.default</span>
  <span class="vbt-titel-nr">[Te]</span>
</div>
<div class="vbt-omschrijving-rij">Error message.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>refKey</td><td>Unique reference key assigned to an entity.</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>errorCode</td><td>Error code type.</td><td>string</td><td class="vbt-td-c"></td><td><a href="https://www.sivi.org/afd-online-tool/json/2020-12/ADNFTM.json">ADNFTM</a> (09; 11; 12; 13; 14; 99)</td></tr>
<tr><td>errorCodeExplanation</td><td>Explanation of the error message.</td><td>string</td><td class="vbt-td-c">1000</td><td></td></tr>
</tbody></table>
</div>

See also the information about error.default in the [SIVI All Finance Standard](https://www.manula.com/manuals/sivi/sivi-all-finance-standard/1/en/topic/error-handling)

<div class="vbt-entiteit" id="entiteit-document-default">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">document.default</span>
  <span class="vbt-titel-nr">[T18]</span>
</div>
<div class="vbt-omschrijving-rij">Information about an attachment/document.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>refKey</td><td>Unique reference key assigned to an entity.</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>fileName</td><td>Name of the file under which the attachment can be saved.</td><td>string</td><td class="vbt-td-c">60</td><td></td></tr>
<tr><td>fileExtension</td><td>Extension of the file under which the attachment can be saved. For example &quot;pdf&quot;, &quot;doc&quot;, etc.</td><td>string</td><td class="vbt-td-c"></td><td>pdf; csv; txt</td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="entiteit-chunking-default">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">chunking.default</span>
  <span class="vbt-titel-nr">[T19]</span>
</div>
<div class="vbt-omschrijving-rij">Chunking&quot; (splitting large messages) into partial messages.</div>
<table>
<thead><tr>
<th style="width:25%">Attribute name</th>
<th style="width:43%">Definition</th>
<th style="width:12%">data type</th>
<th style="width:8%" class="vbt-td-c">length</th>
<th style="width:12%">Code list</th>
</tr></thead>
<tbody>
<tr><td>currentChunkId</td><td>Unique reference (id) of the current chunk.</td><td>string</td><td class="vbt-td-c">70</td><td></td></tr>
<tr><td>chunkSequenceNumber</td><td>Sequence number of the current chunk.</td><td>integer</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>totalNumberOfChunks</td><td>Total number of chunks the message has been split into.</td><td>integer</td><td class="vbt-td-c"></td><td></td></tr>
<tr><td>chunkFragmentPaths</td><td>Array of JMESPath references to the message fragments used within the current chunk.</td><td>array</td><td class="vbt-td-c"></td><td></td></tr>
</tbody></table>
</div>

## 6.3.1 Consistency Checks Cashflow Message (0001b) { #consistency-checks-cashflow-message-0001b }



### Structural rule: cohort or investment portfolio (messages 2 and 3)

In messages 2 and 3, the breakdown under a `pension.scheme` may take place either per cohort (`pension.cohort`, the SPR route) or per investment portfolio (`investment.portfolio`, the FPR route), not both. A message that uses both breakdowns within one scheme is not valid. In message 2 the breakdown is optional: a scheme with only the cash flow directly under the scheme is valid. In message 3, exactly one breakdown is used per scheme.

The data directly under the scheme fall outside this rule and apply in both routes: in message 2 the cash flow `financialTransaction.cashflow` (0..1), in message 3 the payments at scheme level. In message 4 the rule does not apply: there, the investment portfolio is mandatory (1..99) and the breakdown per cohort is an optional addition.

### Cash flow blocks in message 2

- In every cash flow block, directly under the scheme, per cohort and per investment portfolio, `netAmount` and `netDate` are mandatory.
- Every investment portfolio used contains exactly one `financialTransaction.cashflow`.
- Per scheme, the message contains at least one cash flow: directly under the scheme, per cohort or per investment portfolio.


### Sum checks for cohort breakdown (SPR route)

When, in the SPR route, `pension.cohort` is used as a breakdown of the cash flow at scheme level, the detail amounts must reconcile with the total. This is a reconciliation check: the check that the sum of the individual cohort amounts matches the previously reported amount at cohort-scheme level — in other words, the parts add up to the whole.

- `scheme.netAmount = sum(cohort.netAmount)`
- `scheme.contributionAmount = sum(cohort.contributionAmount)`
- `scheme.withdrawalAmount = sum(cohort.withdrawalAmount)`

These sum checks apply to the SPR route and not automatically to the FPR route. In the FPR route, the total is in the cash flow directly under the scheme, alongside the cash flows per investment portfolio. Whether the sum of the portfolio amounts must reconcile with that total has not been laid down; a sum check for the FPR route is therefore not part of the standard. Apply these checks only when totals and underlying breakdowns are present at the same time.

**Technical enforcement**

The consistency checks in this section have been established functionally. Technically, consistency checks are enforced in the file `(..)-validationRules.json` that accompanies the JSON schemas of each message. For these checks, that technical enforcement has not yet been modelled.


## 6.3.2 Consistency Checks Order Instruction and Order Confirmation (00541, 00542) { #consistency-checks-order-instruction-order-confirmation }

### Message 5: amount or quantity

- Per trade instruction, exactly one of `tradeAmount` or `tradeQuantity` is filled. Filling both is not allowed; leaving both empty is allowed only for the leg of a switch that does not drive the switch.
- A switch consists of two legs: one with `buySellId` = `switchfrom` and one with `buySellId` = `switchto`. They refer to each other through `financialInformationRef`, which contains the `refKey` of the other leg.
- Per switch pair, exactly one leg carries exactly one of the two fields; the other leg carries neither.

### Message 6: quantity, price and amount reconcile

- If `tradeQuantity` and `tradePrice` both occur, the following applies per trade: `tradeQuantity × tradePrice = tradeAmount`.
- In a switch, the amount that comes out of the `switchfrom` leg goes into the `switchto` leg. This check does not apply to a switch between investment products in different currencies: the messages contain no exchange rate.

See [§4.3.5](../chapter-4-fpr-processes/#435-message-5-order-instruction-00541) for the explanation, and GitHub issues [#115](https://github.com/Stichting-SIVI/VBPUOdsk/issues/115) and [#116](https://github.com/Stichting-SIVI/VBPUOdsk/issues/116).

**Technical enforcement.** For these checks too, the technical enforcement in `(..)-validationRules.json` has not yet been modelled.

