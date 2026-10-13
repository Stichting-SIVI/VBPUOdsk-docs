## 8.3 Components of the Standard Asset Management Pension Administration

Figure 14 below shows what SIVI will lay down for the Standard Asset Management Pension Administration. The table that follows explains the components.

<img src="../media/image23.svg" style="width:6.26806in;height:3.52569in" />

**Figure 14 - Components of the standard in context**

<table>
<colgroup>
<col style="width: 6%" />
<col style="width: 26%" />
<col style="width: 66%" />
</colgroup>
<thead>
<tr>
<th>No.</th>
<th>Component of the standard</th>
<th>Explanation</th>
</tr>
</thead>
<tbody>
<tr>
<th>1</th>
<td><strong>Principles</strong></td>
<td>The main principles for the development, set-up and governance of the standard.</td>
</tr>
<tr>
<th>2</th>
<td><strong>Process descriptions</strong></td>
<td>Process descriptions are structured descriptions that explain in detail the steps, activities and elements involved in the specific chain processes and information flows. We use these descriptions to provide a clear understanding of how the processes work and which information flows are involved. In this case, the distinction between the flexible and the solidarity premium scheme is particularly relevant.</td>
</tr>
<tr>
<th>3</th>
<td><strong>Governance</strong></td>
<td>Governance is about organising the community around the standard in the best possible way. It must be clear who decides what is carried out with regard to standards, and who decides how this is carried out. This includes the rules of procedure of the advisory group and any temporary working groups.</td>
</tr>
<tr>
<th>4</th>
<td><strong>Maintenance organisation</strong></td>
<td>Maintenance covers the management processes around the standards. It comprises all activities aimed at adapting, extending, further developing, making available and keeping available a (set of) messages that always matches the current needs of the stakeholders.</td>
</tr>
<tr>
<th>5</th>
<td><strong>Change procedure</strong></td>
<td>Changes to the standard affect several stakeholders. The interests of all participating parties are therefore represented in the change procedure. Requests and proposals for changes will be handled according to an agreed procedure.</td>
</tr>
<tr>
<th>6</th>
<td><strong>Data specifications</strong></td>
<td><p>The data specifications describe the meaning of the data elements and their mutual relationships. Data elements are entities, attributes and code lists.</p>
<p>The data specifications include the mapping to AFD 2.0. This makes clear what is missing. For the missing elements, a proposal has been made in AFD 2.0 terms.</p></td>
</tr>
<tr>
<th>7</th>
<td><strong>Basic structure of messages</strong></td>
<td>Base message with the basic structure for a set of messages. The basic structure contains a list of the entities/attributes and the associated hierarchical structure. The description of this base message can be used to create a baseline.</td>
</tr>
<tr>
<th>8</th>
<td><strong>Cross table of basic structure and messages</strong></td>
<td><p>A cross table between the basic structure and the messages.</p>
<p>For each message, the table indicates which entities/attributes apply. It also indicates the number of repetitions (entities) and which attributes must be populated. It is also possible to make selections from code lists, i.e. to indicate which code values apply.</p></td>
</tr>
<tr>
<th>9</th>
<td><strong>Message specifications</strong></td>
<td><p>The specifications are based on the data specifications. In this message specification, this is translated into a hierarchical message structure.</p>
<p>Part of the set of message specifications is the response message. This is the feedback message (§4.4).</p>
<p>Each message has a general section that indicates, among other things, who the sender/recipient of the message is.</p></td>
</tr>
<tr>
<th>10</th>
<td><strong>Message checks</strong></td>
<td>A specification of all checks on the messages, for example consistency checks. It is an option to deliver these checks in machine-readable form, but initially this is not necessary.</td>
</tr>
<tr>
<th>11</th>
<td><strong>Extension of AFD 2.0</strong></td>
<td>Extension of AFD 2.0 with requested data elements. AFD 2.0 can be extended monthly at the request of stakeholders.</td>
</tr>
<tr>
<th>12</th>
<td><strong>Baseline</strong></td>
<td>This is the base message that is imported into AOS. After that, AFD definitions can be created.</td>
</tr>
<tr>
<th>13</th>
<td><strong>Schemas</strong></td>
<td><p>JSON Schema or XML Schema per message/basic structure. Among other things, to be able to validate messages.</p>
<p>AOS delivers JSON schemas based on AFD 2.0 messages and AFD definitions.</p></td>
</tr>
<tr>
<th>14</th>
<td><strong>Events manual</strong></td>
<td><p>Examples of handling specific situations. The situations show how the standard must be applied.</p>
<p>Example messages are part of the events manual.</p></td>
</tr>
<tr>
<th>15</th>
<td><strong>Interface specifications</strong></td>
<td><p>In automated connections between distributed systems (machine-to-machine), there is an interface that makes communication possible. Such an interface is called a ‘koppelvlak’ in Dutch. The description of an interface is what we call interface specifications.</p>
<p>Examples:</p>
<ul>
<li><p>Web services</p></li>
<li><p>File transfer</p></li>
<li><p>Delivery via a portal</p></li>
</ul>
<p>Instructions on (data) security can be part of the interface specifications.</p>
<p>The interface specification for the RESTful API is in §7.4 (OpenAPI).</p></td>
</tr>
<tr>
<th>16</th>
<td><strong>Test facilities</strong></td>
<td><p>Facilities to support developers in implementing the messages/interface specifications.</p>
<p>This can include a generic set of test data.</p></td>
</tr>
<tr>
<th>17</th>
<td><strong>Calculation rules</strong></td>
<td>Instructions for performing calculations. The calculations apply to data elements in the messages.</td>
</tr>
</tbody>
</table>

**Message checks/**

Consistency checks are recorded in JMESPath and relate to the message for which they have been written. Checks that go beyond a single message, i.e. for which other messages or back-office information are needed, fall outside the scope of these checks

**JSON schemas**

The JSON schemas are in principle self-explanatory, but some explanation may be useful because these schemas are also split up in JSON technology. This means that, in addition to the expected entities and entity types such as 'party' and 'pension.scheme', certain key elements are also referred to, such as "$defs", "type", "properties", "additionalProperties" and "required".

As of JSON Schema Draft 2020-12 this is called "$defs". In older versions (draft-07, 2019-09) the term "definitions" was used for this.

These properties and specifications that apply to, for example, 'commonFunctional' are not all grouped around 'commonFunctional', but are spread across the JSON schema. The main thing to note is that this spread is not arbitrary, but follows from the different types of properties
