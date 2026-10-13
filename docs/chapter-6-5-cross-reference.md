## 6.5 Cross-reference Attributes & Messages

This overview shows which attributes within a given message are mandatory (V), optional (O) or not applicable ( ). V stands for the Dutch *verplicht* (mandatory); O stands for optional.

Each entity has its own table below.

<!-- BEGIN legenda -->
The columns carry a short name with the message number above it:

| No. | Short | Message | No. | Short | Message |
|---|---|---|---|---|---|
| 1 | **Assets** | Assets (0001a) | 6 | **Conf** | Order Confirmation (00542) |
| 2 | **Cash** | Cashflow (0001b) | 10 | **Control** | Control Information Investment Pools (00553) |
| 3 | **Proj** | Pension Projection (0001c) | 13 | **Value** | Value Information Investment Pool (00555b) |
| 4 | **Return** | Return Information (00002) | 14 | **Pay** | Payment Information (00556) |
| 5 | **Order** | Order Instruction (00541) | 15 | **CorpAct** | Corporate Actions (00557) |
<!-- EIND legenda -->

The row *(entity)* indicates whether the entity itself is mandatory or optional within
that message; the rows below it apply per attribute. The T number refers to
the corresponding entity block in [§6.3](../chapter-6-functional-specs/#63-attributes-in-entitiesentity-types).






**One block per position.** An entity type, with its T number, is described once in §6.3. In a message it can occur in more than one position in the hierarchy, and what is mandatory or optional can differ per position. That is why each position has its own block below. The title names the direct parent, for example *under pension.cohort*; hovering the mouse over that label shows the full path.

For example, `financialTransaction.payment` (T9) occurs in three positions: under the scheme (messages 3 and 14), under the cohort and under the investment portfolio (both only in message 3). And `investment.portfolio` (T13) occurs in two positions: under the scheme (messages 1 to 4) and under the cohort (only in message 1).



The complete overview in one wide table remains available via
[the cross-reference table in full screen](../assets/kruisreferentie.html).

<!-- Blokken hieronder gegenereerd door gen_html_assets.py uit de modeluitlevering. -->
<!-- Toelichtende tekst hoort TUSSEN de blokken en blijft bij hergeneratie staan.   -->

<div class="vbt-entiteit" id="kruis-commontechnical-default">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">commonTechnical.default</span>
  <span class="vbt-titel-nr">[T1]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>messageId</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>creationDateTime</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>testMessage</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-party-sender">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">party.sender</span> <span class="vbt-titel-herhaling" title="commonTechnical.default">under commonTechnical.default</span>
  <span class="vbt-titel-nr">[T2]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>refKey</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>rsinNumber</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>organizationName</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>applicationSenderName</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-party-contact">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">party.contact</span> <span class="vbt-titel-herhaling" title="commonTechnical.default / party.sender">under party.sender</span>
  <span class="vbt-titel-nr">[T3]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>emailWork</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>workPhoneNumber</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-party-receiver">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">party.receiver</span> <span class="vbt-titel-herhaling" title="commonTechnical.default">under commonTechnical.default</span>
  <span class="vbt-titel-nr">[T4]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>refKey</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>rsinNumber</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>organizationName</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-commonfunctional-default">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">commonFunctional.default</span>
  <span class="vbt-titel-nr">[T5]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>function</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>afdDefinitionName</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>afdDefinitionVersion</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>originalMessageId</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-party-pensionprovider">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">party.pensionProvider</span>
  <span class="vbt-titel-nr">[T6]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>puvCode</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>rsinNumber</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>organizationName</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-pension-scheme">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">pension.scheme</span> <span class="vbt-titel-herhaling" title="party.pensionProvider">under party.pensionProvider</span>
  <span class="vbt-titel-nr">[T7]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>refKey</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>pensionSchemeName</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>startAmount</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>tradingPortfolioId</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-financialinformation-reportingperiod">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">financialInformation.reportingPeriod</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme">under pension.scheme</span>
  <span class="vbt-titel-nr">[T8]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
<tr><td>startDate</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>endDate</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>projectionDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>instructionDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>investmentOrderSettlementDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>tradeDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>participationValuationDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>valueDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-party-creditor">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">party.creditor</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme / financialTransaction.payment">under financialTransaction.payment</span>
  <span class="vbt-titel-nr">[T10]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
<tr><td>refKey</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
<tr><td>collectionAccountIban</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
<tr><td>collectionAccountInNameOf</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
<tr><td>collectionAccountBic</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
<tr><td>collectionAccountBicCorrespondent</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-financialtransaction-cashflow-onder-pension-scheme">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">financialTransaction.cashflow</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme">under pension.scheme</span>
  <span class="vbt-titel-nr">[T11]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>contributionAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>contributionDate</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>withdrawalAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>withdrawalDate</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>netAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>netDate</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-financialtransaction-payment-onder-pension-scheme">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">financialTransaction.payment</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme">under pension.scheme</span>
  <span class="vbt-titel-nr">[T9]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
<tr><td>refKey</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>expectedPensionPaymentDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>amount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
<tr><td>hedgedExpectedPensionPaymentAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>currencyType</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
<tr><td>collectionAccountIban</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
<tr><td>description</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-pension-cohort">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">pension.cohort</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme">under pension.scheme</span>
  <span class="vbt-titel-nr">[T12]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>refKey</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>description</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>participationStatus</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>startAge</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>endAge</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>reserveIndicator</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>reserveType</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>reserveDescription</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>startAmount</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>netAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>netDate</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>contributionAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>withdrawalAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>protectionReturnPercentage</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>excessReturnPercentage</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>protectionReturnAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>excessReturnAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-financialtransaction-payment-onder-pension-cohort">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">financialTransaction.payment</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme / pension.cohort">under pension.cohort</span>
  <span class="vbt-titel-nr">[T9]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>refKey</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>expectedPensionPaymentDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>amount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>hedgedExpectedPensionPaymentAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-investment-portfolio-onder-pension-scheme">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">investment.portfolio</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme">under pension.scheme</span>
  <span class="vbt-titel-nr">[T13]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>refKey</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>description</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>startExposureAmount</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>startExposurePercentage</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>startAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>netAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>endAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>returnPercentage</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>returnAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-investment-portfolio-onder-pension-cohort">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">investment.portfolio</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme / pension.cohort">under pension.cohort</span>
  <span class="vbt-titel-nr">[T13]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>refKey</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>description</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>startExposureAmount</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>startExposurePercentage</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>startAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>netAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>endAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>returnPercentage</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>returnAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-investment-pool">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">investment.pool</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme">under pension.scheme</span>
  <span class="vbt-titel-nr">[T14]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>refKey</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>description</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>buySellId</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>tradeValueAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>currencyType</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>unitsSummedValueAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>preliminaryUnitValueAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>numberOfUnits</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-financialtransaction-cashflow-onder-investment-portfolio">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">financialTransaction.cashflow</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme / investment.portfolio">under investment.portfolio</span>
  <span class="vbt-titel-nr">[T11]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>contributionAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>contributionDate</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>withdrawalAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>withdrawalDate</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>netAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>netDate</td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-financialtransaction-payment-onder-investment-portfolio">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">financialTransaction.payment</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme / investment.portfolio">under investment.portfolio</span>
  <span class="vbt-titel-nr">[T9]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>refKey</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>expectedPensionPaymentDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>amount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>hedgedExpectedPensionPaymentAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-investment-investmentdetails">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">investment.investmentDetails</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme">under pension.scheme</span>
  <span class="vbt-titel-nr">[T15]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>refKey</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>description</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>currencyType</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>numberOfUnits</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-financialtransaction-trade">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">financialTransaction.trade</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme / investment.investmentDetails">under investment.investmentDetails</span>
  <span class="vbt-titel-nr">[T17]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>tradeDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>refKey</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>buySellId</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>tradeAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>tradeQuantity</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>switchType</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>financialInformationRef</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>adjustmentIndicator</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>tradePrice</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>counterparty</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>broker</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>interestAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>commissionAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>clearingBroker</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
<tr><td>clearingBrokerCashAccount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-document-default">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">document.default</span>
  <span class="vbt-titel-nr">[T18]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>refKey</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>fileName</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>fileExtension</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-chunking-default">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">chunking.default</span>
  <span class="vbt-titel-nr">[T19]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>currentChunkId</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>chunkSequenceNumber</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>totalNumberOfChunks</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>chunkFragmentPaths</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td><td class="vbt-td-c vbt-v">V</td></tr>
</tbody></table>
</div>

<div class="vbt-entiteit" id="kruis-investment-corporateaction">
<div class="vbt-titel-rij">
  <span class="vbt-titel-naam">investment.corporateAction</span> <span class="vbt-titel-herhaling" title="party.pensionProvider / pension.scheme / investment.investmentDetails">under investment.investmentDetails</span>
  <span class="vbt-titel-nr">[T16]</span>
</div>
<table>
<thead><tr>
<th style="width:30%">Attribute</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">1</span>Assets</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">2</span>Cash</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">3</span>Proj</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">4</span>Return</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">5</span>Order</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">6</span>Conf</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">10</span>Control</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">13</span>Value</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">14</span>Pay</th>
<th class="vbt-td-c vbt-kop-bericht"><span class="vbt-kop-nr">15</span>CorpAct</th>
</tr></thead>
<tbody>
<tr class="vbt-rij-entiteit"><td>(entity)</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>refKey</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>description</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>corporateActionType</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>instructionDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>tradeDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>paymentDate</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-v">V</td></tr>
<tr><td>cashDividendTotalAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>cashDividendPerUnitAmount</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>currencyType</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>stockDividendPerUnitNumber</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>stockDividendTotalNumber</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>newProductName</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td></tr>
<tr><td>newProductIdentifier</td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c"></td><td class="vbt-td-c vbt-o">O</td></tr>
</tbody></table>
</div>
