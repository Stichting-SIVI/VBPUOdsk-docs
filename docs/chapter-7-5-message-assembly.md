## 7.5 Message Assembly, Versioning and Publication

### 7.5.1 Explanation of the Use of `afdDefinitionVersion` { #751-toelichting-op-het-gebruik-van-afddefintionversion }

`afdDefinitionVersion` is populated with the version number (from the “Schema name”) of the VBPUO JSON schema.

The **VBPUO JSON schema** for the functional messages and the VBPUO_Feedback_Message is maintained by SIVI using “[AFD Online Samenstellen](https://www.sivi.org/afd-online-samenstellen) (AOS)” and is administered there with the following metadata:

| **AOS schema metadata** | **Values (example)**         |
|----------------------------|------------------------------|
| SIVI community             | AFD 2.0                      |
| Message type:              | Protocol PUO Vermogensbeheer |
| Domain:                    | Algemeen                     |
| Schema name:               | VBPUO-**<u>\###.##</u>**     |

Table : Metadata (AOS) VBPUO schema

In the (AOS) VBPUO schema, the VBPUO message structures are defined as **”functions”**, for example the function: “Bericht_1.\_Vermogen\_(0001a)”. From release 2027, 10 substantive messages and the Feedback Message are active; 5 FPR messages have been discontinued (see §6.4). For each “function”, 3 **JSON schemas** are then generated, which are published on GitHub (“commit”). These JSON schemas have the following purposes:

JSON Schema explained

| **Purposes** | **Further description** | **Example file name** |
|----|----|----|
| Message structure | Definition of the structure, mandatory elements and field validations, with internal and external references to safeguard data consistency and standardisation. | VBPUO-001.00-Bericht_1.\_Vermogen\_(0001a).json |
| Code lists/tables: | Defines the code lists (for example pension provider and currency codes) that are used as references in the JSON schema for field validation. | VBPUO-001.00-Bericht_1.\_Vermogen\_(0001a)-afdCodelists.json |
| Consistency checks | Defines the rules for consistency checks in the JSON schema to safeguard the validity and consistency of data relationships. | VBPUO-001.00-Bericht_1.\_Vermogen\_(0001a)-validationRules.json |

Table : JSON Schemas (from AOS) explained

#### 7.5.1.1 Version Number / afdDefinitionVersion in a GitHub Release

The version number of an AOS schema must be included in every message to be sent. This number can be found in the message structure as a constant under afdDefinitionVersion.

Under this number, the JSON Schemas can be found at <https://portal.sivi.org/organisationschemas>. The messages created with this schema – within the VBPUO schema these are defined as functions – are published on GitHub.

##### File Name versus afdDefinitionVersion

The file names of the JSON schemas contain a version number as part of the name, for example `VBPUO-001.00-Bericht_1._Vermogen_(0001a).json`. This version number is frozen at the value that applied at first publication and is not updated in later releases.

The reason for this is the link with the OpenAPI Specification (OAS). The OAS refers to the JSON schemas through a direct file path reference (`$ref`):

`$ref: 'VBPUO-Bericht_1._Vermogen_(0001a)/VBPUO-001.00-Bericht_1._Vermogen_(0001a).json'`

If the version number in the file name were updated with every release, all `$ref` references in the OAS would also have to be adjusted. Because implementing parties (PUOs and asset managers) base their API implementations on the OAS, every change of file name would require an adjustment in all implemented APIs in the sector. This has been deliberately avoided.

The consequence is that file name and content can diverge: the file name states `001.00`, while the field `afdDefinitionVersion` inside the schema contains the current value, such as `001.02`.

> **Note:** for implementation and validation, always use the value of `afdDefinitionVersion` — not the version number in the file name.


**`afdDefinitionName` follows the file name.** The field `afdDefinitionName` has a fixed value in every schema: the file name without `.json`, so with `001.00`. For message 1 this is `VBPUO-001.00-Bericht_1._Vermogen_(0001a)`, for the feedback message `VBPUO_Feedback_Message-001.00-VBPUO_Feedback_Message`. That name does not change with a new release. The version is only in `afdDefinitionVersion`: 001.05 for the ten messages, 001.02 for the feedback message. See GitHub issue [#140](https://github.com/Stichting-SIVI/VBPUOdsk/issues/140).


See also: [GitHub issue #58](https://github.com/Stichting-SIVI/VBPUOdsk/issues/58)

### 7.5.2 Publication on GitHub: Version Number and Tag

When releasing on GitHub, the release is given a Name and a Tag. All JSON schemas and the OAS fall under that release/tag. From release 2027, the example messages are in a folder of their own, [Voorbeeldberichten](https://github.com/Stichting-SIVI/VBPUOdsk/tree/main/Voorbeeldberichten), with a subfolder per release. There, main is authoritative: examples can be improved or supplemented between two releases, without a new release of the standard. Every change is recorded in the LEESMIJ of the release folder. The tag contains the examples as they were on the release date; the current examples are on main. Examples are not normative; in the event of a difference, the JSON schemas and this manual apply. For release 2027 there are examples for all active messages and the feedback message, including the FPR route with investment portfolios in messages 2 and 3 and reserves in message 1. They are built on situations from practice, with existing pension providers from the code list AFDIDP and fictitious amounts and characteristics, and validate against the JSON schemas and the consistency checks of §6.3.1 and §6.3.2.

The name of release 2027, for example, is “Release 2027 (v1.4.0)” with tag v1.4.0 (see [releases](https://github.com/Stichting-SIVI/VBPUOdsk/releases)). The GitHub release name and tag number cannot be found in the payload of the messages. Both the messages and the OAS have their own release number.

### 7.5.3 JSON Schema Versions

Several JSON-related files are published per message:
- message structure;
- code lists;
- validation rules.

From release 2027, these files are published in accordance with JSON Schema Draft 2020-12.

The following applies:
- message structures use `$defs`;
- internal references use `#/$defs/...`;
- external AFD references point to the `2020-12` path;
- validation rules remain unchanged in substance.
