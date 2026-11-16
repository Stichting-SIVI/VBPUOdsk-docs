This is an unofficial, machine-assisted English translation. In case of differences, the [Dutch version](https://stichting-sivi.github.io/VBPUOdsk-docs-prepare/) prevails. The figures are still in Dutch; English versions will follow.

<div class="print-verberg">

12-10-2026

Standard for data exchange between Asset Management and Pension Administration

<img src="media/image1.png" style="width:3.69685in;height:3.69685in" alt="Data exchange" />

</div>

<table>
<colgroup>
<col style="width: 22%" />
<col style="width: 77%" />
</colgroup>
<tbody>
<tr>
<td>Date</td>
<td>20261012</td>
</tr>
<tr>
<td>Project Reference</td>
<td>VBPUO</td>
</tr>
<tr>
<td>Confidentiality</td>
<td>Public</td>
</tr>
<tr>
<td>Status</td>
<td>Release 2027</td>
</tr>
<tr>
<td>Client</td>
<td>Steering Group DSO</td>
</tr>
<tr>
<td>Authors</td>
<td>SIVI</td>
</tr>
<tr>
<td>Repository</td>
<td><a href="https://github.com/Stichting-SIVI/VBPUOdsk">https://github.com/Stichting-SIVI/VBPUOdsk</a></td>
</tr>
<tr>
<td>Dutch version (authoritative)</td>
<td><a href="https://stichting-sivi.github.io/VBPUOdsk-docs-prepare/">https://stichting-sivi.github.io/VBPUOdsk-docs-prepare/</a> (official; in case of differences the Dutch version prevails)</td>
</tr>
<tr>
<td>Document version</td>
<td>20261012 Manual Standard data exchange VB-PUO release 2027</td>
</tr>
<tr>
<td>Release numbers</td>
<td><p><a href="https://github.com/Stichting-SIVI/VBPUOdsk/releases/tag/v1.4.0">GitHub release 2027 Tag v1.4.0</a> consists of the following components:</p>
<ul>
<li><p>JSON Schemas version: VBPUO-001.05<br />
Model base: 20261011-2252 generieke-bronmetadata-json</p></li>
</ul></td>
</tr>
<tr>
<td>Release notes</td>
<td><p><a href="https://github.com/Stichting-SIVI/VBPUOdsk/releases/tag/v1.4.0">https://github.com/Stichting-SIVI/VBPUOdsk/releases/tag/v1.4.0</a></p>
<p>The release notes describe the changes. The impact of the changes has been incorporated into this manual.</p></td>
</tr>
<tr>
<td>Changes after publication</td>
<td><p>16-11-2026 &mdash; &sect;2.9.2 Release Policy and Version Management: the example of the supported releases still listed the releases for 2026 and has been updated to 2027 (Release 2027, Release 2026 and 2024 November). The release policy itself has not changed: in addition to the current annual release, the two preceding ones remain available.</p>
<p>Reason: questions about the number of supported releases. The proposal to support the current and the immediately preceding annual release, plus <code>main</code>, from release 2028 onwards is in GitHub issue <a href="https://github.com/Stichting-SIVI/VBPUOdsk/issues/123">#123</a> and has not yet been adopted.</p></td>
</tr>
<tr>
<td>Prerelease 2027</td>
<td><p>The manual of the prerelease of 21 July 2026 remains available for consultation until April 2027: <a href="../2027-prerelease/">English prerelease 2027</a> (Dutch: <a href="https://stichting-sivi.github.io/VBPUOdsk-docs-prepare/prerelease-2027/">prerelease 2027</a>).</p></td>
</tr>
<tr>
<td><a href="https://github.com/Stichting-SIVI/VBPUOdsk/releases/tag/v1.4.0">Technical changes release 2027</a></td>
<td><p>Transition to JSON Schema Draft 2020-12:</p>
<ul>
<li>Transition from <code>definitions</code> to <code>$defs</code></li>
<li>Adjustment of internal and external schema references</li>
<li>Modernisation of JSON Schema validation and tooling support</li>
</ul>
<p>See also GitHub issue <a href="https://github.com/Stichting-SIVI/VBPUOdsk/issues/104">#104 JSON Schema Version</a></p></td>
</tr>
<tr>
<td><a href="chapter-8-5-changes-release-2027/">Functional changes release 2027</a></td>
<td>
<p>The most important functional changes:</p>
<ul>
<li>One FPR model; the cohort pool and the ACB role have been dropped; messages 7, 8, 9, 11 and 12 are no longer active (&sect;4.3.11).</li>
<li>New message 15 Corporate Actions (&sect;4.3.10).</li>
<li>SPR route and FPR route in messages 2, 3 and 4, with the investment portfolio for the FPR route (&sect;3.2.5, &sect;6.3.1).</li>
<li>Order flow: switch convention and consistency checks for messages 5 and 6 (&sect;4.3.5, &sect;6.3.2).</li>
<li>Messages 10, 13 and 14 simplified; multiple payments per scheme in message 14 (&sect;4.3).</li>
<li>Feedback Message: longer error description and updated value list of message types; handling of duplicates and non-executable orders explained (&sect;4.4).</li>
<li>Reserves and provisions: division of roles between the fields and consistency check (&sect;6.3).</li>
<li>Sender and receiver per message according to the process flows (Table 12, &sect;6.4).</li>
<li>Fixed <code>afdDefinitionName</code> (&sect;7.5.1.1); example messages in a separate folder per release (&sect;7.5.2).</li>
</ul>
<p>The complete overview, per topic and per message, is given in <a href="chapter-8-5-changes-release-2027/">&sect;8.5 Changes Release 2027</a>; what has been added or changed since the prerelease of 21 July 2026 is shown there in red.</p>
</td>
</tr>
</tbody>
</table>

<!-- niet-in-word:start -->
<h2 class="print-pagina-breuk">Table of Contents</h2>

- [1 Introduction](chapter-1-introduction.md)
- [2 Principles](chapter-2-principles.md)
- [3 Processes & Information Flows – Solidarity Premium Scheme](chapter-3-spr-processes.md)
- [4 Processes & Information Flows – Flexible Premium Scheme](chapter-4-fpr-processes.md)
- [5 Approach/Set-up of the Data Standard](chapter-5-data-standard-setup.md)
- [6 Functional Specifications](chapter-6-functional-specs.md)
- [6.4 Messages](chapter-6-4-messages.md)
- [6.5 Cross-reference Attributes & Messages](chapter-6-5-cross-reference.md)
- [7 Technical Specifications](chapter-7-tech-specs.md)
- [7.4 Transport / OpenAPI](chapter-7-4-transport-openapi.md)
- [7.5 Message Assembly, Versioning and Publication](chapter-7-5-message-assembly.md)
- [7.6 Processing Protocol for Partial messages (Chunking)](chapter-7-6-chunking.md)
- [8 Appendices](chapter-8-appendices.md)
- [8.1 Glossary/List of Abbreviations Asset Management & Pension Administration](chapter-8-1-glossary-vbpuo.md)
- [8.2 Glossary of Data Exchange Based on Standards](chapter-8-2-glossary-data-exchange.md)
- [8.3 Components of the Standard Asset Management Pension Administration](chapter-8-3-standard-components.md)
- [8.4 Translation Table from Functional Attributes to AFD2.0 Attributes.](chapter-8-4-translation-table.md)
- [8.5 Changes Release 2027](chapter-8-5-changes-release-2027.md)
<!-- niet-in-word:eind -->
