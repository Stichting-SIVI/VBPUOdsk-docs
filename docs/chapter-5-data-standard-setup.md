# 5 Approach/Set-up of the Data Standard

**In this chapter we explain how we arrive at the specifications of the messages.**

**Steps to arrive at the functional specifications of the messages:**

1.  **Create descriptions of the processes and information flows.**

2.  **Draw up a list of entities and associated attributes.**

3.  **Determine the base structure of the messages.**

4.  **Indicate which messages are needed.**

5.  **Create a cross-reference table between the base structure and the messages.**

    **We explain the relationship with SIVI AFS. We use the building blocks from SIVI AFS (AFD 2.0) to arrive at technical specifications.**

## 5.1 Create Descriptions of the Processes and Information Flows

In order to standardise the interfaces, including the message exchange between parties in the chain(s), we create descriptions of the various chain processes as they take place, including, in broad outline, the desired functionality at the chain actors. We also indicate which information flows are involved. Visualisations of the information flows between parties serve as an aid in this.

**The processes & information flows are described in detail in the report ‘’[Results of research: Standard for data exchange between pension administration & asset management parties’’](https://www.pensioenfederatie.nl/cms/streambin.aspx?documentid=18380):**

**Chapter 4: Solidarity premium scheme.**

**Chapter 5: Flexible premium scheme.**

See also chapter 3 of this manual.

## 5.2 Draw up a List of Entities and Associated Attributes

Create definitions of entities and attributes. Use code lists where possible, preferably existing code lists. Also indicate the required relationships between the data elements. Each entity and each attribute is also given a label at the technical level. The labels are included in a message together with the associated values. This enables a computer to process the data from the message automatically. Figure 10 shows the building blocks of a data model.

![](media/image18.png)

**Figure 10 – Building blocks of the data model**

## 5.3 Determine the Base Structure of the Messages

Also make the composition of the messages clear, for example:

<table>
<tr><td>Entity A</td><td>M</td></tr>
<tr><td>Entity B*</td><td>M, 1… 999</td></tr>
<tr><td style="padding-left: 40px;">Entity C</td><td>M, 1</td></tr>
<tr><td style="padding-left: 40px;">Entity D</td><td>O, 1</td></tr>
</table>

Entity A is mandatory and occurs 1 time.

Entity B occurs at least 1 time and at most 999 times.

Entity C is nested under entity B and must occur 1 time.

Entity D is nested under entity B and occurs at most 1 time.

## 5.4 Indicate Which Messages Are Needed.

On the basis of the descriptions of the processes and information flows, determine which messages are needed.

## 5.5 Create a Cross-reference Table Between the Base Structure and the Messages.

For each message, indicate in the table which entities/attributes apply. In doing so, indicate the number of repetitions (entities) and also indicate which attributes must be populated. It is also possible to make selections from code lists, i.e. to indicate which code values apply.

Figure 11 below shows how we compose several base structures from a collection of entities/attributes and how we can derive several functional messages from each base structure. Finally, we deliver technical message specifications. Figure 11 illustrates this.

![](media/image19.png)

**Figure 11 - From entities to base structure to functional messages to technical message definitions  
**

## 5.6 Relationship with SIVI AFS

The English-language AFD 2.0 is part of the SIVI All Finance Standard. Via [Consult AFD 2.0 Online](https://www.sivi.org/standaarden/sivi-all-finance-standaard/afd-online-2-0/) you can search online for all entities, attributes and code lists. In addition, you will also find an overview of AFD 2.0 in XLS format. Pensions are to some extent already present in AFD 2.0. This is partly related to the mapping that SIVI developed for the [Ockto Data Model](https://www.sivi.org/actueel/persbericht-sivi-en-ockto-brengen-registratie-klantdata-stap-verder/). Ockto has a link with the pension register. The use of JSON is a principle of AFD 2.0.

AFD 2.0 contains building blocks that we use when specifying the entities and attributes for the standard for data exchange between asset management and pension administration. In doing so, we indicate which AFD 2.0 building blocks we use and which building blocks are missing. SIVI can then add the latter to AFD 2.0. Besides entities/attributes, this may also concern code lists.
