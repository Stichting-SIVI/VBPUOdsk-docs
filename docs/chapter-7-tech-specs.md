# 7 Technical Specifications

**The technical data specifications are made available on the basis of AFD 2.0 from SIVI AFS. In this chapter, the reader can find an explanation.**

## 7.1 Messages & Schemes

Each message can concern several schemes (pension.scheme). It always concerns 1 `party.pensionProvider`, however. Sending is per message, and that message therefore contains 1 `party.pensionProvider` and 1 or more pension.scheme's

## 7.2 Validations

The following validation rules can be carried out with the technical specifications:

- Check whether the message structure is correct;

<!-- -->

- Is the data type correct (including numbers, strings);

- Check on minimum and maximum values;

- Validation of the field length;

- Check whether mandatory entities and mandatory attributes are present;

- Check on the number of repetitions of entities;

- Are permitted codes from code lists being applied.

PM consistency checks (validation rules on the relationships between different data) are still under development. See also the JSON schemas.

## 7.3 JSON

1.  For AFD 2.0 in combination with JSON, the SIVI AFS team follows the specifications below (taken from [Forum Standaardisatie](https://www.forumstandaardisatie.nl/open-standaarden/json)):

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 70%" />
</colgroup>
<thead>
<tr>
<th>Subject</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<th>Full name</th>
<td>JavaScript Object Notation</td>
</tr>
<tr>
<th>Version</th>
<td>RFC8259, December 2017</td>
</tr>
<tr>
<th>Specification document</th>
<td><a href="https://tools.ietf.org/html/rfc8259">Specification document JSON</a></td>
</tr>
<tr>
<th>Managing organisation</th>
<td><p>Internet Engineering Task Force</p>
<p><a href="https://datatracker.ietf.org/doc/html/rfc7159">https://datatracker.ietf.org/doc/html/rfc7159</a></p></td>
</tr>
<tr>
<th>Functional scope</th>
<td>Object notation for exchanging data structures. For example in web applications that retrieve data asynchronously from the web server.</td>
</tr>
<tr>
<th>Classification</th>
<td>Exchange of data structures</td>
</tr>
<tr>
<th>Benefit</th>
<td>JSON (JavaScript Object Notation) is a subset of the JavaScript programming language. The simplicity of JSON has made it very popular, in particular as a ‘light’ alternative to XML.</td>
</tr>
<tr>
<th>Operation</th>
<td><p>JavaScript Object Notation (JSON) is a format for storing and sending data, just like XML. JavaScript is the programming language from which the basic syntax description is derived for use in JSON. JSON is used for exchanging data structures, in particular in web applications that retrieve data asynchronously from the web server. The standard is aimed in particular at efficient programming and has a compact notation, for example:</p>

<pre><code>{
  "naam": "Jan",
  "geboren": 1983
}</code></pre></td>
</tr>
<tr>
<th>Tools</th>
<td>Various online JSON validators and tools can be found, also for the various programming platforms. More information about the standard can also be found via <a href="http://www.ecma-international.org/publications/files/ECMA-ST/ECMA-404.pdf">publications of ECMA International</a></td>
</tr>
</tbody>
</table>

**Guideline**: If a non-mandatory attribute has no value, the attribute must be omitted entirely from the JSON message. This is a recommended practice according to the JSON conventions.

### 7.3.1 Use of JSON Schema

For the validation of the message structures, the standard uses JSON Schema.

The JSON schemas are generated from AFD 2.0 / AOS and published via GitHub. These schemas support:
- validation of message structures;
- validation of mandatory fields;
- validation of code lists;
- validation of technical constraints.

### 7.3.2 Transition to JSON Schema Draft 2020-12

From release 2027, the VBPUO standard uses JSON Schema Draft 2020-12.

This change was discussed and recorded via GitHub issue:

[#104 JSON Schema Version](https://github.com/Stichting-SIVI/VBPUOdsk/issues/104)

The transition is a technical modernisation of the JSON schemas. It does not change the functional meaning of the messages.

#### Differences Compared with JSON Schema Draft 2019-09

##### Main Schema

1. The schema dialect has been changed from:

`http://json-schema.org/draft/2019-09/schema#`

to:

`https://json-schema.org/draft/2020-12/schema`

2. The container with definitions is no longer called `definitions` but `$defs`.

3. Internal references have been changed from:

`#/definitions/...`

to:

`#/$defs/...`

4. The external reference to the code list now uses the 2020-12 path:

`https://www.sivi.org/afd-online-tool/json/2020-12/AFDIDP.json#/$defs/AFDIDP`

instead of:

`https://www.sivi.org/afd-online-tool/json/AFDIDP.json#/definitions/AFDIDP`

##### ValidationRules

1. No 2020-12-specific model differences identified.

2. The file remains a JSON structure with metadata and validation rules; no substantive changes have been identified as a result of the transition to Draft 2020-12.

##### AfdCodelists

1. The schema dialect has been changed from:

`http://json-schema.org/draft-07/schema#`

to:

`https://json-schema.org/draft/2020-12/schema`

2. The container with definitions is no longer called `definitions` but `$defs`.
