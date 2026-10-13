# 1 Introduction

**In this introduction we discuss the context, the purpose and the target audience of this manual. We also present the structure of the manual (in some detail).**

## 1.1 Context

**Final report**

In early September 2023 the final report ‘’[Results of research: Standard for data exchange between pension administration & asset management parties’’](https://www.pensioenfederatie.nl/cms/streambin.aspx?documentid=18380) was published.

With the introduction/implementation of the Future Pensions Act (Wtp), closer alignment between fund assets and the collective administration of personal pension assets is necessary. This increases the frequency of the required information exchange. In current practice, pension providers and asset management parties arrange the information exchange between themselves. Because the information exchange is intensifying, standardisation of the information exchange is desirable.

The final report mentioned describes the functional data required for the exchange, the information flows and the participant communication that partly depends on them.

The data and information flows have been worked out for both the solidarity premium scheme and the flexible premium scheme.

The final report is based on contributions from various organisations, including APG, AZL, Caceis, Capgemini, H&C, Van Lanschot Kempen IM, MN, Pensioenfederatie, SIVI and TKP. Through a consultation round, various other administration organisations, fiduciaries, custodians and pension funds, among others, were also involved. This consultation round has been completed and the input from it has been incorporated.

**Follow-up**

SIVI translates the final report into a data standard based on AFD 2.0 from SVI AFS. This data standard comes with a base message from which we derived the original 14 messages. The messages are exchanged via REST API endpoints. In addition to those messages, a Feedback_Message is available for feedback. In asynchronous processing, the feedback message is the mandatory mechanism for status and error feedback (see [§4.4](../chapter-4-fpr-processes/#44-feedback-message-resending)). The message set has since been changed, although the message names have been retained.

**Governance and management**

The standard represents a shared interest of pension administration and asset management, for which administrative and substantive management must be assigned. After the introduction of the standard, new wishes will arise that may or may not have to be included in the standard.

It has been agreed that:

- Ownership of the standard rests with the Pensioenfederatie.

- Substantive and administrative management of the standard will be put in place.

- The standard is managed by the management organisation SIVI.

- An advisory group supports the management and any further development.

## 1.2 Purpose

This manual provides an explanation of the standard for data exchange between asset management and pension administration. The manual gives:

- Analysts and developers a guide to implement the standard (or have it implemented);

- Those involved insight into the management of the standard.

## 1.3 Target Audience

This manual is intended for consultants, analysts and developers involved in the implementation of the standard for data exchange between asset management and pension administration parties.

## 1.4 Structure

### 1.4.1 Notation of Attribute Names

In the descriptive texts of this manual you will come across a dual naming for data fields, in the following format:

technicalName (Functional Name)

- **technicalName**: This is the **definitive, technical attribute name** in accordance with the SIVI AFD 2.0 standard, shown in a monospace font. This is the name that must actually be used in the JSON messages.

- **(Functional Name)**: This is the **original, functional name** as used during the requirements and design phase. This name is given temporarily, between parentheses and in a slightly smaller, normal font, to improve recognisability during the transition. In a future release of this manual this functional name will be removed.

The complete Translation Table from Functional Attributes to AFD2.0 Attributes is included in 8.4.

<table>
<colgroup>
<col style="width: 13%" />
<col style="width: 86%" />
</colgroup>
<thead>
<tr>
<th>Chapter</th>
<th>Contents</th>
</tr>
</thead>
<tbody>
<tr>
<th>1</th>
<td><p><strong>Introduction</strong></p>
<p>In this introduction we discuss the context, the purpose and the target audience of this manual. We also present the structure of the manual (in some detail).</p></td>
</tr>
<tr>
<th>2</th>
<td><p><strong>Principles</strong></p>
<p>In this chapter we discuss the main principles for the development, design and governance of the standard. This is based mainly on <strong><a href="https://www.pensioenfederatie.nl/cms/streambin.aspx?documentid=18380">Results of research: Standard for data exchange between pension administration &amp; asset management parties’’</a>.</strong></p></td>
</tr>
<tr>
<th>3</th>
<td><p><strong>Processes &amp; information flows – Solidarity premium scheme</strong></p>
<p>The processes &amp; information flows are described in detail in the report ‘’<strong><a href="https://www.pensioenfederatie.nl/cms/streambin.aspx?documentid=18380">Results of research: Standard for data exchange between pension administration &amp; asset management parties’’</a>:</strong></p>
<p>Chapter 4: Solidarity premium scheme.</p></td>
</tr>
<tr>
<th>4</th>
<td><p><strong>Processes &amp; information flows – Flexible premium scheme</strong></p>
<p>The processes &amp; information flows are described in detail in the report ‘’<strong><a href="https://www.pensioenfederatie.nl/cms/streambin.aspx?documentid=18380">Results of research: Standard for data exchange between pension administration &amp; asset management parties’’</a>:</strong></p>
<p>Chapter 5: Flexible premium scheme.</p></td>
</tr>
<tr>
<th>5</th>
<td><p><strong>Approach/set-up of the data standard</strong></p>
<p>In this chapter we explain how we arrive at the specifications of the messages.</p>
<p>Steps to arrive at the functional specifications of the messages:</p>
<ul>
<li><p>Create descriptions of the processes and information flows.</p></li>
<li><p>Draw up a list of entities and associated attributes.</p></li>
<li><p>Determine the base structure of the messages.</p></li>
<li><p>Indicate which messages are needed.</p></li>
<li><p>Create a cross-reference table between the base structure and the messages.</p>
<p>We explain the relationship with SIVI AFS. We use the building blocks from SIVI AFS (AFD 2.0) to arrive at technical specifications.</p></li>
</ul></td>
</tr>
<tr>
<th>6</th>
<td><p><strong>Functional specifications</strong></p>
<p>This chapter contains the functional specifications:</p>
<ul>
<li><p>Data dictionary;</p></li>
<li><p>Base message;</p></li>
<li><p>Cross-reference base message &amp; messages.</p></li>
</ul></td>
</tr>
<tr>
<th>7</th>
<td><p><strong>Technical specifications</strong></p>
<p>The technical data specifications are made available on the basis of AFD 2.0 from SIVI AFS. In this chapter the reader can read an explanation.</p></td>
</tr>
<tr>
<th>8</th>
<td><p><strong>Appendices</strong></p>
<p>In the appendices you will find the:</p>
<ul>
<li><p>Glossary/List of abbreviations Asset Management &amp; Pension Administration;</p></li>
<li><p>Glossary of data exchange based on standards.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 1.5 Links

This manual contains links, mostly source references. These are coloured **blue**. By clicking the link, the reader is taken to the relevant web page or the relevant report/article.

## 1.6 Source of the Title Page Image

<https://www.flaticon.com/free-icon/data-exchange_4995192>
