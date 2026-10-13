## 8.5 Changes release 2027

This section summarises what has changed in this manual compared with release 2026: first what applies to all or several messages, then what changes per message, and finally the structure of the manual. What has been added or changed since the prerelease of 21 July 2026 is shown in <span class="sinds-prerelease">red</span>. Section numbers refer to this version. The changes in the JSON schemas are in the [release notes](https://github.com/Stichting-SIVI/VBPUOdsk/releases/tag/v1.4.0).

### For all or several messages

**FPR model and roles**

- <span class="sinds-prerelease">One FPR model: the distinction between model 1 (direct order model) and model 2 (layered order model) has been dropped, with one schematic representation (Figure 2). What happens below the investment pool falls outside the data exchange (§4.1, §4.2).</span>
- <span class="sinds-prerelease">The cohort pool as a layer between cohort and investment pool has been discontinued. The PUO aggregates the changes at participant level per cohort and translates them directly into net orders in one or more investment pools; that allocation lies with the PUO and falls outside the data exchange. The investment administrator does not know the strategic allocation within a cohort and administers the investment pools on the instruction of the PUO (§4.2). In the translation table (§8.4), the rows of `pension.cohortPool` have been dropped.</span>
- The role ACB (administrator of cohort and investment pools) has been discontinued as an independent actor; in practice the BA or the PUO performs it, and the message schema can still support the role (§6.4). See [#131](https://github.com/Stichting-SIVI/VBPUOdsk/issues/131). <span class="sinds-prerelease">The roles have been reduced to the four from Figure 8 and 9: PUO, BA, FM/VB and LDI manager.</span>
- <span class="sinds-prerelease">Investment product is the umbrella term for investment funds, mandates and other investments; the investment pool is the administrative layer above it (§4.2, §4.3.5, §6.4).</span> Terms `LDI-mandaat` and `Mandaat` added to §8.1; <span class="sinds-prerelease">also `Beleggingsproduct`, `Beleggingsfonds` and `Virtuele pool`, the last with the note that the standard does not use that term.</span>
- For collective premium flows within FPR (risk premiums, reserves, withdrawals), SPR messages 1 to 4 are used (§4.1). See [#91](https://github.com/Stichting-SIVI/VBPUOdsk/issues/91). <span class="sinds-prerelease">Within FPR, messages 2 and 4 serve for the flows outside the unit administration and message 3 for the interest rate risk profile towards the FM/VB and the LDI manager (§4.3).</span>
- <span class="sinds-prerelease">Return allocation depends on the set-up: for unitized products the return is included in the unit price; for a collective payout provision in euros it runs via message 4 (§4.2).</span>

**FPR process flow (Figure 8 and 9, §4.3.1)**

- Figure 8 and 9 are indicative: the times are indicative, the order of the steps is guiding. <span class="sinds-prerelease">They show one run of the trading cycle for one administrative set-up; sending to more recipients and additional deliveries have no step of their own. Both figures use the same step letter for the same step.</span>
- <span class="sinds-prerelease">Phase 1 is called *order input* and covers only T-4; the feedback on T+3 (order confirmation, message 6, and final month-end NAV, message 13) is in phase 3.</span>
- Phase 3: the LDI manager carries out the transactions on the LDI mandate itself (H1); the FM/VB monitors the LDI manager and handles the other investment portfolios (H2). <span class="sinds-prerelease">Figure 8 now also shows this split execution, with the feedback.</span>
- Figure 9 (non-unitized): the cash instruction for the CVP goes out on T-4, at the same time as the order instruction (was T+3). <span class="sinds-prerelease">In the case of a switch the BA sends that instruction, in the case of a complete sell the PUO. The EUR order for the CVP does not go through the order instruction (message 5); the valuation message after the CVP execution has been dropped, and the return reaches the PUO via message 4. The same applies to other collective parts in euros: risk-sharing reserve, compensation deposit, other reserves and provisions.</span>
- <span class="sinds-prerelease">Feedback on executed transactions usually runs via SWIFT, but this is not prescribed and does not apply to all instruments (swaps are handled differently); the channel is a matter of mutual agreement. The channel names have been removed from the diagrams.</span>

**Sender and recipient (Table 12, §6.4)**

- Table 12 has new actor columns: `Soort`, `ACB` and `BR` dropped, `LDI` added. See [#99](https://github.com/Stichting-SIVI/VBPUOdsk/issues/99), [#119](https://github.com/Stichting-SIVI/VBPUOdsk/issues/119), [#121](https://github.com/Stichting-SIVI/VBPUOdsk/issues/121), [#98](https://github.com/Stichting-SIVI/VBPUOdsk/issues/98).
- <span class="sinds-prerelease">Sender and recipient follow Figure 1 (SPR) and Figure 8 and 9 (FPR) throughout: in Table 12, in the overview of the message types (§6.4) and in chapter 4. Table 12 is a role matrix: messages 10 and 14 are sent by the BA, and by the PUO only if it performs the role of BA itself. See [#142](https://github.com/Stichting-SIVI/VBPUOdsk/issues/142). The changes per message are listed below.</span>
- <span class="sinds-prerelease">Principle: information received is not forwarded, so the sender sends the same message to each recipient separately, with its own endpoint and identification. The purpose can differ per recipient: the same order instruction is an instruction for one and a notification for the other (§2.4).</span>

**Reserves and provisions (§6.3)**

- Division of roles: `refKey` identifies, `reserveType` (AFDRES) classifies and is the key for the investment policy, `reserveDescription` describes. See [#111](https://github.com/Stichting-SIVI/VBPUOdsk/issues/111).
- Code list AFDRES extended with codes 9 to 15. Where investment policy is shared, consolidation is possible; a separate code only for a separate investment policy. Applies to SPR and FPR. See [#134](https://github.com/Stichting-SIVI/VBPUOdsk/issues/134).
- <span class="sinds-prerelease">If `reserveIndicator` = true, `reserveType` is mandatory; `reserveDescription` is desirable for 99 (Other) and possible for the other codes.</span>
- <span class="sinds-prerelease">The reserve fields are only in the cohort, not on the investment portfolio.</span>

**Other rules**

- Cohorts with value 0 may be sent with `0` or omitted. See [#100](https://github.com/Stichting-SIVI/VBPUOdsk/issues/100). <span class="sinds-prerelease">The rule is in §6.3 and applies to all messages with cohorts (1 to 4), including reserves and provisions; omitting a reserve does not automatically mean that the value is 0. The standard does not recognise a field without a value (`null`).</span>
- `messageId` is unique across all messages and does not serve for grouping or bundling; the exception is chunking (§6.3, §7.6). See [#108](https://github.com/Stichting-SIVI/VBPUOdsk/issues/108).
- Date conventions for `startDate` and `projectionDate` (§6.3, §3.2.1, §3.2.3). See [#94](https://github.com/Stichting-SIVI/VBPUOdsk/issues/94).
- APFs with several ring-fenced compartments (kringen): two common scenarios for the PUV codes (§6.3, §6.4.1). See [#114](https://github.com/Stichting-SIVI/VBPUOdsk/issues/114).
- `participationStatus` (ADNDNS): value 60 removed from the documentation, in line with the schema. See [#103](https://github.com/Stichting-SIVI/VBPUOdsk/issues/103) and [#71](https://github.com/Stichting-SIVI/VBPUOdsk/issues/71).
- Chunking: the standard has no maximum number of chunks; limits are agreements between chain parties (§2.7). See [#127](https://github.com/Stichting-SIVI/VBPUOdsk/issues/127). `chunkMeta.default` is called `chunking.default` in the documentation, in line with the schemas.
- The funding ratio falls outside the scope (§2.3). See [#118](https://github.com/Stichting-SIVI/VBPUOdsk/issues/118).
- <span class="sinds-prerelease">Digital signing (`x-jws-signature`) and authentication with an API key (`x-api-key`) are options, not obligations; only OAuth 2.0 is mandatory, in line with the OAS (§2.7, §7.4). The limits in the schemas are binding (§2.7).</span>
- <span class="sinds-prerelease">`afdDefinitionName` has a fixed value in each schema, equal to the file name with `001.00`; this also applies to the feedback message (in the prerelease `…-001.02-…`) (§7.5.1.1). See [#140](https://github.com/Stichting-SIVI/VBPUOdsk/issues/140). `afdDefinitionVersion` remains 001.05 for the ten messages and 001.02 for the feedback message, the same numbers as in the prerelease.</span>

### Per message

Message 1 Assets (0001a) has no changes of its own beyond the rules above (cohorts with value 0, reserves and provisions).

**Messages 2, 3 and 4: SPR and FPR route**

- The prerelease laid down two mutually exclusive population patterns for message 2, with an exclusion rule as a consistency check (§6.3.1). See [#113](https://github.com/Stichting-SIVI/VBPUOdsk/issues/113). <span class="sinds-prerelease">The exclusion between the cash flow directly under the scheme and the cash flow per investment portfolio has been dropped; the breakdowns per cohort and per investment portfolio continue to exclude each other in messages 2 and 3. The routes for messages 2, 3 and 4 are set out together in the new §3.2.5, with Figure 1a, 1b, 9a and 9b: in message 2 the breakdown is optional, in message 3 there is exactly one; in message 4 the investment portfolio applies to both routes, without route exclusion. The cash flow and the payments directly under the scheme apply in both routes; in the FPR route they as a rule contain the total of the portfolios.</span>
- Consistency checks (§6.3.1): sum checks for a cohort breakdown, and the concept of reconciliation explained. <span class="sinds-prerelease">A scheme in message 2 contains at least one cash flow (direct, per cohort or per investment portfolio). The technical safeguarding via `(..)-validationRules.json` has not yet been modelled.</span>

**Message 2 Cashflow (0001b)**

- <span class="sinds-prerelease">In each cash flow block, `netAmount` and `netDate` are mandatory and the amounts and dates of inflow and outflow optional; the money changes hands on the `netDate` (§6.3).</span>
- <span class="sinds-prerelease">The message carries an expected or an established net cash flow. Timing and frequency are chain agreements; what is fixed, however, is that an established statement follows the settlement of the unit sale, because the amount arises from it (§4.3.1, §4.3.2).</span>
- <span class="sinds-prerelease">Own section in chapter 4, with the purpose, the FPR population pattern and the relationship with messages 5, 10 and 14 (§4.3.2). In Table 12 the BA is also a sender.</span>

**Message 3 Pension Projection (0001c)**

- <span class="sinds-prerelease">A portfolio branch for the FPR route, with its own section in chapter 4 (§4.3.3).</span>
- <span class="sinds-prerelease">The payments under the cohort and under the investment portfolio are optional (`0..*, O`); an empty list `financialTransaction` no longer needs to be included (§6.4.4, §6.5).</span>

**Message 4 Return Information (00002)**

- Total return and the breakdown into matching and return may be included in one message, distinguished via `refKey` (§3.2.4). See [#109](https://github.com/Stichting-SIVI/VBPUOdsk/issues/109).
- <span class="sinds-prerelease">Own section in chapter 4, with the demarcation from message 13. Its use depends on the set-up: with a unitized CVP it is not needed, with a CVP in euros it is, because message 13 has no unit value there (§4.3.4).</span>

**Messages 5 Order Instruction (00541) and 6 Order Confirmation (00542)**

- Switch convention: the code `switch` in `buySellId` has been replaced by `switchfrom` and `switchto`; the direction follows from `buySellId`, amounts are always positive. `switchType` and `financialInformationRef` are also in message 6. See [#115](https://github.com/Stichting-SIVI/VBPUOdsk/issues/115). <span class="sinds-prerelease">`switchType` has the codes of AFDSWI (`1`, `2`) instead of the labels *sequential* and *one-day*.</span>
- Message 5: per trade instruction exactly one of `tradeAmount` and `tradeQuantity`. See [#116](https://github.com/Stichting-SIVI/VBPUOdsk/issues/116). <span class="sinds-prerelease">In a switch, exactly one leg per switch pair carries the amount or the quantity, and the other leg neither; in practice the `switchfrom` leg carries the number of units on the transition to the collective payout phase. The consistency checks of messages 5 and 6 are in the new §6.3.2.</span>
- Message 6: `tradeQuantity`, `tradePrice`, `counterparty`, `broker`, `interestAmount`, `commissionAmount`, `clearingBroker` and `clearingBrokerCashAccount` are optional; `tradeAmount` remains mandatory. See [#105](https://github.com/Stichting-SIVI/VBPUOdsk/issues/105). <span class="sinds-prerelease">If `tradeQuantity` and `tradePrice` are both present, quantity × price = amount applies (§6.3.2).</span>
- <span class="sinds-prerelease">The order instruction goes from the PUO to the BA, the order confirmation back from the BA to the PUO. The provider of the fund, which carries out the ordering in the underlying investments, is a different role from the order-processing party (§4.3.5, §4.3.6). In §6.4 the designation *Direct order* has been dropped.</span>

**Message 10 Control Information Investment Pools (00553)**

- The `cohortPool` layer has been removed; the data are directly on `investment.pool` (§6.4.8). A formal FPR decision has not been found in the minutes; the change has been made in the absence of known objections. See [#124](https://github.com/Stichting-SIVI/VBPUOdsk/issues/124).
- `dummyCashId`, `tradeQuantity`, `unitPrice` and `currencyExchangeRate` removed from `investment.pool`; `buySellId`, `tradeValueAmount` and `currencyType` remain. See [#133](https://github.com/Stichting-SIVI/VBPUOdsk/issues/133).
- <span class="sinds-prerelease">Explanation of the purpose, with the translation from message 5 to message 10: netting per investment pool, conversion of units into amounts and the treatment of switches (§4.3.7). The permitted values of `buySellId` are `sell; buy`.</span>

**Message 13 Value Information Investment Pool (00555b)**

- `marketValueAmount` removed from `investment.pool`; the net asset value runs only via `preliminaryUnitValueAmount`. Field descriptions merged. See [#128](https://github.com/Stichting-SIVI/VBPUOdsk/issues/128). <span class="sinds-prerelease">The description of `participationValuationDate` has been updated; the attribute remains mandatory.</span>
- <span class="sinds-prerelease">Own explanation: the message delivers the price information on T-4 and the final month-end NAV on T+3, and is the basis for reconciliation and payment information (§4.3.8).</span>

**Message 14 Payment Information (00556)**

- <span class="sinds-prerelease">Several payments per scheme in one message, at least one and at most 999, instead of one message per payment (§4.3.9, §6.4). See [#149](https://github.com/Stichting-SIVI/VBPUOdsk/issues/149).</span>
- <span class="sinds-prerelease">Sent by the BA to the FM; the PUO sends it only if it performs the role of BA itself, and is no longer listed as sender in Table 12. Explanation of purpose and meaning (§4.3.9).</span>
- `collectionAccountIban` has a maximum of 34 characters, the international IBAN length according to ISO 13616 (was 10) (§6.3). See [#135](https://github.com/Stichting-SIVI/VBPUOdsk/issues/135).

**Message 15 Corporate Actions (00557)**

- New message, with a process explanation for passing on corporate actions from the asset management chain to the PUO (§4.3.10). See [#87](https://github.com/Stichting-SIVI/VBPUOdsk/issues/87). <span class="sinds-prerelease">It is an ad hoc message outside the trading run and is therefore not in Figure 8 and 9. It relates to investment funds that are traded directly on a trading platform; corporate actions do not apply to investment pools themselves. The sender is the FM or the BA.</span>
- <span class="sinds-prerelease">Code list AFDCOA (formerly AFDCAE) for `corporateActionType`: `1` Cash dividend, `2` Stock dividend, `3` Product change, `99` Other. A rebate falls under `99` (in the prerelease: `rebate`); a separate code is not yet available. See [#137](https://github.com/Stichting-SIVI/VBPUOdsk/issues/137).</span> The amount of a rebate is in `cashDividendTotalAmount` and/or `cashDividendPerUnitAmount`.
- <span class="sinds-prerelease">Message 15 is an exception to the rule that changes within an investment product do not affect the PUO: the PUO does have to process dividend, rebate and unit changes (§4.2).</span>
- <span class="sinds-prerelease">The empty `financialInformation.reportingPeriod` has been removed from the message.</span>

**Feedback Message**

- A duplicate `messageId` is rejected with HTTP 400 and a feedback message in the response body (§4.4). See [#129](https://github.com/Stichting-SIVI/VBPUOdsk/issues/129). <span class="sinds-prerelease">Chunking is the exception to this.</span>
- `party.sender` and `party.receiver` in the description of `commonTechnical`. See [#90](https://github.com/Stichting-SIVI/VBPUOdsk/issues/90).
- More scenarios for successful and failed processing; `errorCodeExplanation` a maximum of 1000 characters (was 300). See [#107](https://github.com/Stichting-SIVI/VBPUOdsk/issues/107).
- Orders that cannot be executed are reported back with the feedback message (status Rejected, error code, description); force majeure falls under bilateral agreements (§4.4). See [#132](https://github.com/Stichting-SIVI/VBPUOdsk/issues/132).
- `originalMessageType` also includes `00542`. See [#126](https://github.com/Stichting-SIVI/VBPUOdsk/issues/126). <span class="sinds-prerelease">The list of values follows the ten active messages: `00557` added, the discontinued messages removed; also in the figure in §4.4.</span>

**Discontinued messages 7, 8, 9, 11 and 12**

- Removed from the active message set; the numbering of the other messages is unchanged. See [#99](https://github.com/Stichting-SIVI/VBPUOdsk/issues/99), [#119](https://github.com/Stichting-SIVI/VBPUOdsk/issues/119), [#121](https://github.com/Stichting-SIVI/VBPUOdsk/issues/121). <span class="sinds-prerelease">They are in one block at the end of chapter 4, with the reason per message (§4.3.11), and no longer in §6.4.</span>

### Structure of the manual

- <span class="sinds-prerelease">Chapter 4 has been reorganised: the use of SPR messages within FPR is at the end of the introduction (§4.1); the process flow has its own section (§4.3.1); each active message has a section, now including messages 2, 3 and 4 (§4.3.2 to §4.3.10); the discontinued messages are in §4.3.11; the feedback message is §4.4. In §6.4 the message structures have been renumbered consecutively: message 10 is §6.4.8, through to the feedback message, §6.4.12.</span>
- <span class="sinds-prerelease">The tables with the basic message structure and the maximum numbers in §6.4.1 are generated from the model. They show the hierarchy per location: an entity that occurs in several places appears there several times, each under its own parent. For `financialTransaction.payment` the three maxima (999, 9999 or 99999) are shown with the place where they apply. §6.4 explains the suffixes (such as `_1`) in the message diagrams on GitHub.</span>
- <span class="sinds-prerelease">§6.5 Cross-reference: readable headings, a filter by message and one block per entity and parent.</span>
- <span class="sinds-prerelease">The example messages are in a separate folder `Voorbeeldberichten` per release on GitHub, no longer in the message folders; main is leading there. For release 2027 they have been supplemented for all messages, based on situations from practice with existing pension providers and fictitious data (§7.5).</span>
- <span class="sinds-prerelease">Figure 3 (§4.2) shows ages instead of years of birth.</span>
- <span class="sinds-prerelease">References: internal references that led nowhere have been fixed, with a check that monitors this from now on; GitHub references point to the Stichting SIVI repository; references to GitHub issues placed with the text; spelling of technical names harmonised.</span>
- <span class="sinds-prerelease">The colophon summarises the changes; this section is new.</span>
- Some textual improvements.
