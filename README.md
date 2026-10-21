
# A Semantically Developed Knowledge-Based System for Deploying Kali Linux Tools

## Research Overview

**Research Title:** A Semantically Developed Knowledge-Based System for Deploying Kali Linux Tools  
**Researcher:** Effiong Okon Antai  
**Programme:** MSc Cybersecurity  
**Institution:** Nottingham Trent University, United Kingdom  
**Research Supervisor:** Dr Richard Otuka  
**Completed:** September 2025  
**Additional Technical Validation:** October 2026

This research project presents the design, development and evaluation of an ontology-based Knowledge-Based System (KBS) for recommending Kali Linux cybersecurity tools according to user-defined tasks, experience levels and tool relationships.

The system uses Semantic Web technologies to organise cybersecurity knowledge and support reasoning-based tool recommendations.

It is intended for cybersecurity students, learners, penetration testers and researchers working in authorised testing environments.

The implementation is a Protégé-based research prototype rather than a commercially deployed application.

---

## 1. Research Problem

Kali Linux provides numerous tools for cybersecurity assessment, penetration testing, network analysis and digital forensics.

Selecting suitable tools can be challenging, particularly for beginners who may not understand the differences between tools, their applications or the order in which they should be used.

Traditional tool directories and static documentation provide useful information but may not offer personalised, task-based recommendations or explain relationships between tools.

This research investigates how semantic knowledge representation and reasoning can support more structured and context-aware cybersecurity tool selection.

---

## 2. Research Aim and Objectives

**Aim:** To design and implement a knowledge-based system that assists cybersecurity learners and practitioners in selecting Kali Linux tools for defined cybersecurity tasks.

### Research Objectives

- Review existing approaches to cybersecurity tool classification and selection.
- Design an ontology representing cybersecurity tools, tasks, categories and user skill levels.
- Implement semantic relationships and reasoning rules for tool recommendations.
- Develop Description Logic (DL) and SPARQL queries for retrieving relevant tools and workflow relationships.
- Evaluate the system through functional testing, reasoning checks and user feedback.
- Identify limitations and opportunities for further development.

---

## Research Ontology Versions

This repository preserves two versions of the OWL ontology developed for the research project.

### 2025 — Original MSc Research Ontology

**File:** [kali_linux_tool_recommendation_ontology.owl](kali_linux_tool_recommendation_ontology.owl)

This is the original ontology developed as part of my MSc Cybersecurity research at Nottingham Trent University in 2025.

It models:

- Kali Linux cybersecurity tools
- Cybersecurity tasks
- User skill levels
- Tool categories
- Tool-to-tool relationships
- SWRL-based recommendation rules

This version preserves the original research model.

### 2026 — SWRL Inference Validation

**File:** [kali_linux_tool_recommendation_inferred.owl](kali_linux_tool_recommendation_inferred.owl)

This version contains inferred assertions transferred into the ontology following additional validation in Protégé using SWRLTab and the Drools rule engine in October 2026.

The validation reported:

- 18 SWRL rules exported
- 31 OWL classes exported
- 63 OWL individuals exported
- 522 OWL axioms exported
- 477 inferred axioms reported
- Successful inference transfer into the OWL model

The inferred axiom count is the rule engine's reported inference output, not the number of distinct tool recommendations.

### SPARQL Query Validation

Five documented SPARQL queries are available in the [queries folder](queries/).

They demonstrate:

1. Password-cracking tool retrieval.
2. Skill-level filtering.
3. SWRL-based suggested-tool classifications.
4. Direct tool-sequencing relationships.
5. Direct and indirect tool reachability.

The original research was completed in 2025, while additional query verification and documentation were carried out in October 2026.

---

## 3. Technologies Used

| Technology | Purpose |
|---|---|
| Protégé | Ontology development and management |
| OWL 2 | Formal representation of cybersecurity knowledge |
| RDF | Structured semantic knowledge representation |
| SWRL | Rule-based semantic inference |
| Pellet | Ontology reasoning used in the original research |
| SPARQL | Querying cybersecurity tools and their relationships |
| Description Logic | Class-based reasoning and ontology queries |
| OntoGraf | Visualisation of ontology relationships |
| Drools | Rule execution through the SWRLTab interface |

The project combines ontology modelling, rule-based reasoning and semantic querying to support cybersecurity tool recommendations.

---

## 4. System Architecture and Ontology Design

The system represents cybersecurity knowledge through interconnected ontology concepts.

### 4.1 Core Classes

The original ontology contains five main top-level classes:

- `Tool`
- `Task`
- `Category`
- `UserLevel`
- `SuggestedTool`

### 4.2 Tool Subclasses

The ontology includes tool classifications such as:

- `ExploitationTool`
- `ForensicsTool`
- `NetworkScanningTool`
- `PasswordCrackingTool`
- `ReportingTool`
- `SniffingSpoofingTool`
- `VulnerabilityAnalysisTool`
- `WirelessAttackTool`

These subclasses support the organisation of cybersecurity tools according to their functions.

### 4.3 User-Level Classification

The ontology represents three user experience levels:

- `Beginner`
- `Intermediate`
- `Advanced`

These are individuals associated with the `UserLevel` class.

The original ontology also contains the following subclasses under `UserLevel`:

- `BeginnerTool`
- `IntermediateTool`
- `AdvancedTool`

These classes support the classification of tools according to skill-level relationships.

### 4.4 Suggested Tool Classes

The `SuggestedTool` hierarchy contains task-oriented recommendation classes, including:

- `CrackPassword`
- `CrackWireless`
- `InformationGathering`
- `PortScanner`
- `ScanningForensics`
- `ExploitWebApplication`
- `AttacksVulnerability`
- `AttacksMiTM`
- `ReportCollaborationTool`

These classes represent recommendation-related concepts defined in the original ontology.

### 4.5 Object Properties

The original ontology includes:

| Object Property | Purpose |
|---|---|
| `isUsedFor` | Associates cybersecurity tools with tasks |
| `belongsToCategory` | Links tools to their categories |
| `requiresSkillLevel` | Associates tools with user experience levels |
| `isFollowedBy` | Represents possible tool workflow sequences |
| `SuggestedToolChain` | Additional object property defined in the original ontology |

The precise use of `SuggestedToolChain` can be examined through the ontology's property assertions.

### 4.6 Data Properties

The original Protégé screenshots identify:

- `hasCommand` — stores example command information.
- `hasDescription` — stores descriptions of cybersecurity tools.

### 4.7 Research Workflow

The recommendation process follows these steps:

1. A cybersecurity task is identified.
2. The task is matched with concepts represented in the ontology.
3. Semantic relationships and configured reasoning rules are examined.
4. DL or SPARQL queries retrieve matching tools.
5. Relevant tool information, including descriptions, example commands and workflow relationships, is presented where available.

This process is demonstrated within Protégé rather than through a standalone application.

---

## 5. Cybersecurity Tools Covered

The ontology represents selected Kali Linux tools across different cybersecurity tasks and categories.

| Tool | Primary Function |
|---|---|
| Nmap | Network scanning |
| Netdiscover | Network discovery |
| Hashcat | Password cracking |
| John the Ripper | Password auditing |
| Hydra | Password authentication testing |
| Aircrack-ng | Wireless security testing |
| Reaver | WPS security assessment |
| Zenmap | Graphical interface for Nmap |

Additional cybersecurity tools and categories are represented in the ontology, including vulnerability analysis, web application testing, digital forensics, exploitation testing, reporting and network traffic analysis.

---

## 6. Cybersecurity Tasks Represented

The `Task` class contains individuals representing cybersecurity activities.

Examples visible in the original Protégé implementation include:

- `AnalyzeArtifacts`
- `AnalyzeFileSystem`
- `AnalyzeFirmware`
- `AnalyzeMemory`
- `AnalyzeTraffic`
- `CrackPassWord`
- `Exploitation`
- `FindExploits`
- `GeneratePayload`
- `PerformMITMAttack`
- `PortScanner`
- `ScanVulnerabilities`
- `TestWifiSecurity`

The ontology also contains a task labelled `find live hosts`.

These task individuals allow the system to represent relationships between cybersecurity activities and relevant tools.

---

## 7. Cybersecurity Categories Represented

The `Category` class contains individuals including:

- `AttacksMiTM`
- `AttacksVulnerability`
- `CrackingPassWord`
- `CrackingWireless`
- `ExploitationWeb`
- `ExploitationDatabase`
- `ExploitationPassword`
- `ExploitationPayload`
- `InformationCollaboration`
- `InformationGathering`
- `ManInTheMiddle`
- `ReportCollaborationTool`
- `ScanningForensics`

These categories provide structured groupings for cybersecurity tools.

**Ontology naming note:** The original research contains similar identifiers, including `CrackPassWord`, `CrackingPassWord` and `CrackPassword`. These names are retained as implemented. Future ontology maintenance may standardise naming after reviewing their meanings and relationships.

---

## 8. Example Use Case: Password Cracking

**Task:** Password Cracking  
**User Level:** Advanced

### Tools Returned

- Hashcat
- John the Ripper
- Hydra

The original Protégé SPARQL screenshots demonstrate that the ontology retrieves these three tools when queried for password-cracking activities.

### How the System Works

1. A cybersecurity task, such as password cracking, is selected.
2. The ontology identifies tools associated with the task.
3. SPARQL retrieves matching tools and their available information.
4. The results provide structured guidance for selecting tools relevant to the task.

The original query demonstrates task-based retrieval. Skill-level filtering is a separate capability.

### Original SPARQL Query

The following query is transcribed from the original MSc research screenshot:

    PREFIX KaliLinuxTools: <http://www.semanticweb.org/milli/ontologies/2025/6/KaliLinuxTools#>
    PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

    SELECT ?tool ?label ?command
    WHERE {
      ?tool KaliLinuxTools:isUsedFor ?task .
      ?task rdfs:label ?taskLabel .

      FILTER regex(str(?taskLabel), "crack.*pass", "i")

      OPTIONAL { ?tool rdfs:label ?label . }
      OPTIONAL { ?tool KaliLinuxTools:hasCommand ?command . }
    }

### Original Query Results

| Tool | Query Result |
|---|---|
| Hashcat | Returned |
| Hydra | Returned |
| JohnTheRipper | Returned |

The original screenshots also show example command information retrieved through the `hasCommand` property.

These results demonstrate that the ontology can retrieve relevant tool information using semantic relationships and SPARQL queries.

---

## 9. Semantic Reasoning and SWRL Rules

The system uses Semantic Web Rule Language (SWRL) rules to support selected tool classifications and recommendations.

The original Protégé SWRLTab shows rules associated with:

- Beginner tool classification.
- Intermediate tool classification.
- Password cracking.
- Wireless security testing.
- Information gathering.
- Port scanning.
- Vulnerability analysis.
- Web application exploitation.
- Reporting and collaboration.

### Example Rule-Based Classification

The beginner-level rule associates a tool with the `Beginner` individual through `requiresSkillLevel` and supports classification under `BeginnerTool`.

Other rules use relationships such as `belongsToCategory` to classify tools within recommendation-related classes.

The original SWRLTab also shows rules involving the `hasCommand` property.

### Reasoning Environment

The MSc project used Pellet for ontology reasoning.

The original Protégé screenshots also show the Drools rule engine interface in SWRLTab.

OWL reasoning and SWRL rule execution are related but distinct processes.

### October 2026 SWRL Validation

Additional rule execution was performed using SWRLTab and Drools.

The recorded results included:

| Measurement | Result |
|---|---|
| SWRL rules exported | 18 |
| OWL classes exported | 31 |
| OWL individuals exported | 63 |
| Object property declarations | 5 |
| Data property declarations | 7 |
| OWL axioms exported | 522 |
| Inferred axioms reported | 477 |
| Reported execution time | 464 ms |

Following rule execution, inferred assertions were transferred into a separate OWL model.

The resulting ontology was saved as:

[kali_linux_tool_recommendation_inferred.owl](kali_linux_tool_recommendation_inferred.owl)

Subsequent SPARQL testing successfully retrieved inferred recommendation classifications.

This provides evidence of functional SWRL execution and semantic query retrieval in the tested environment.

---

## 10. DL and SPARQL Query Capabilities

The research demonstrates semantic retrieval through Description Logic and SPARQL.

### Task-Based Retrieval

Identifying tools associated with specified cybersecurity tasks.

### Skill-Level Filtering

Retrieving tools associated with beginner, intermediate or advanced experience levels.

### Tool Workflow Relationships

Examining relationships between tools through properties such as `isFollowedBy`.

### Suggested Tool Recommendations

Exploring asserted and inferred recommendation-related knowledge.

### Query Validation

Checking whether retrieved results match expected ontology relationships.

### Verified SPARQL Queries — October 2026

Five SPARQL queries have been documented and tested in Protégé.

| Query | Capability | Verified Result |
|---|---|---|
| [Password Cracking](queries/password_cracking.rq) | Task-based retrieval | 3 tools |
| [Skill-Level Filtering](queries/skill_level_filtering.rq) | User-level filtering | 3 tools |
| [Suggested Tools](queries/suggested_tools.rq) | SWRL-derived classifications | Multiple classifications |
| [Tool Sequencing](queries/tool_sequencing.rq) | Direct relationships | 6 relationships |
| [Tool Reachability](queries/tool_reachability.rq) | Direct and indirect relationships | 7 reachable pairs |

### 10.1 Password-Cracking Tool Retrieval

**Query:** [password_cracking.rq](queries/password_cracking.rq)

**Verified Results:**

- Hashcat
- Hydra
- JohnTheRipper

**Status:** PASS — 3 tools retrieved.

The task-based retrieval is also supported by original MSc research screenshots.

### 10.2 Skill-Level Filtering

**Query:** [skill_level_filtering.rq](queries/skill_level_filtering.rq)

**Verified Results:**

- BurpSuite
- Kismet
- OWASPZAP

**Status:** PASS — 3 Intermediate-level tools retrieved in Protégé on 21 October 2026.

### 10.3 SWRL-Based Suggested Tool Classifications

**Query:** [suggested_tools.rq](queries/suggested_tools.rq)

SWRL rules were executed using the Drools rule engine in Protégé, and inferred assertions were transferred into the OWL model before running the query.

**Validation Observations:**

- 18 SWRL rules exported.
- 31 OWL classes and 63 OWL individuals exported.
- 522 OWL axioms exported.
- 477 inferred axioms reported.
- Inference transfer into OWL completed successfully.

Examples of retrieved classifications include:

| Tool | Inferred Classification |
|---|---|
| Hydra | CrackPassword |
| JohnTheRipper | CrackPassword |
| Nikto | AttacksVulnerability |
| OpenVAS | AttacksVulnerability |
| Lynis | AttacksVulnerability |
| BurpSuite | ExploitWebApplication |
| MITMf | AttacksMiTM |
| Kismet | CrackWireless |
| Reaver | CrackWireless |
| Wifite | CrackWireless |

**Status:** PASS — inferred tool classifications successfully retrieved.

### 10.4 Tool-Sequencing Relationships

**Query:** [tool_sequencing.rq](queries/tool_sequencing.rq)

The query retrieves direct relationships modelled using the `isFollowedBy` object property.

**Verified Results:**

| First Tool | Next Tool |
|---|---|
| Aircracking | Airmonng |
| Nikto | OpenVAS |
| Nmap | Netdiscover |
| OpenVAS | Lynis |
| Reaver | Wifite |
| Wireshark | Tcpdump |

**Status:** PASS — 6 relationships retrieved in Protégé on 21 October 2026.

These are relationships represented in the ontology, not independently validated optimal execution sequences.

### 10.5 Tool Reachability Analysis

**Query:** [tool_reachability.rq](queries/tool_reachability.rq)

**Validation Date:** 21 October 2026

This query extends the tool-sequencing analysis by identifying both direct and indirect connections between cybersecurity tools.

It uses the SPARQL property-path operator `+` with the `isFollowedBy` object property.

The operator retrieves relationships involving one or more steps.

**SPARQL Query:**

    PREFIX kali: <http://www.semanticweb.org/milli/ontologies/2025/6/KaliLinuxTools#>

    SELECT DISTINCT ?startTool ?reachableTool
    WHERE {
        ?startTool kali:isFollowedBy+ ?reachableTool .
    }
    ORDER BY ?startTool ?reachableTool

**Verified Results:**

| Starting Tool | Reachable Tool | Relationship |
|---|---|---|
| Aircracking | Airmonng | Direct |
| Nikto | Lynis | Indirect |
| Nikto | OpenVAS | Direct |
| Nmap | Netdiscover | Direct |
| OpenVAS | Lynis | Direct |
| Reaver | Wifite | Direct |
| Wireshark | Tcpdump | Direct |

**Status:** PASS — 7 reachable tool pairs retrieved in Protégé.

**Example of Indirect Reachability:**

Nikto → OpenVAS → Lynis

The ontology contains a direct relationship from Nikto to OpenVAS and another from OpenVAS to Lynis.

The reachability query therefore identifies Lynis as reachable from Nikto, even without a direct relationship between those two tools.

**Research Significance:**

This test demonstrates SPARQL property-path querying and transitive reachability analysis.

It extends the existing tool-sequencing capability by identifying multi-step connections within the cybersecurity knowledge model.

The results reflect semantic connectivity within the ontology. They do not establish that the resulting sequences are operationally optimal or appropriate for every security assessment.

### Overall Query Validation Summary

| Validation Test | Result | Status |
|---|---|---|
| Password-cracking retrieval | 3 tools | PASS |
| Skill-level filtering | 3 tools | PASS |
| SWRL rule execution | 477 inferred axioms reported | PASS |
| Suggested-tool classifications | Multiple classifications retrieved | PASS |
| Direct tool sequencing | 6 relationships | PASS |
| Direct and indirect reachability | 7 reachable pairs | PASS |

All five documented SPARQL queries produced results during Protégé testing.

### Query Files and Reproducibility

The complete query files, procedures, results and limitations are documented in the [queries README](queries/README.md).

The [original research ontology](kali_linux_tool_recommendation_ontology.owl) preserves the MSc implementation.

The [inferred ontology](kali_linux_tool_recommendation_inferred.owl) is a separate model containing assertions transferred after the 2026 SWRL validation.

---

## 11. Testing and Evaluation

The original MSc dissertation documents six evaluation scenarios addressing:

1. Task-based tool retrieval.
2. Skill-level filtering.
3. Tool-sequence retrieval.
4. Combined and advanced query conditions.
5. Negative testing for incorrect associations.
6. Performance and reasoning checks.

The dissertation reports that the tested scenarios produced results consistent with the intended ontology relationships.

### Additional Validation — October 2026

Further technical validation was carried out using Protégé.

This included:

- Execution of SWRL rules using Drools.
- Transfer of inferred assertions into a separate OWL ontology.
- Verification of task-based SPARQL retrieval.
- Verification of Intermediate skill-level filtering.
- Retrieval of inferred recommendation classifications.
- Retrieval of direct tool-to-tool relationships.
- Verification of direct and indirect reachability using SPARQL property paths.

These additional tests strengthen the reproducibility documentation of the original research prototype.

### User Feedback

The research also reports exploratory feedback from five participants:

- Three MSc Cybersecurity students.
- Two ethical hacking practitioners.

Participants considered cybersecurity activities including network scanning, password cracking and vulnerability scanning.

The reported feedback highlighted the potential usefulness of structured tool recommendations for learning and workflow guidance.

The evaluation involved a small group and does not constitute large-scale independent validation.

---

## 12. How to Open and Examine the Ontology

### Requirements

- Protégé Desktop.
- A compatible ontology reasoner.
- SWRLTab support where required.
- A SPARQL-capable environment.

### Instructions

1. Download or clone this GitHub repository.
2. Open Protégé Desktop.
3. Select **File → Open**.
4. Open the original ontology:

   [kali_linux_tool_recommendation_ontology.owl](kali_linux_tool_recommendation_ontology.owl)

5. Inspect the **Classes** tab to explore the ontology hierarchy.
6. Inspect **Object properties** and **Data properties**.
7. Open **Individuals by class** to examine tools, tasks, categories and user levels.
8. Inspect the **SWRLTab** to review the reasoning rules.
9. Configure a compatible reasoner to examine consistency and inferred relationships.
10. Use **DL Query** or a compatible **SPARQL Query** interface to reproduce the research examples.
11. Open a query from the [queries folder](queries/) and execute it in the SPARQL interface.
12. To reproduce inferred classifications, run the SWRL rules and transfer inferred assertions into a separate working copy of the ontology, or inspect the saved [2026 inferred ontology](kali_linux_tool_recommendation_inferred.owl).
13. Execute `tool_sequencing.rq` to retrieve direct relationships.
14. Execute `tool_reachability.rq` to retrieve direct and indirect relationships.
15. Compare the results with the original dissertation, screenshots and October 2026 validation documentation.

The ontology file may use Turtle serialisation despite its `.owl` extension. Select RDF/Turtle if your software does not detect the format automatically.

Plugin availability and reasoning behaviour may vary between Protégé versions.

---

## 13. Research Contributions

This project developed and documented the following contributions.

### Ontology-Based Cybersecurity Knowledge Representation

A structured ontology connecting selected Kali Linux tools with cybersecurity tasks, categories and user experience levels.

### Semantic Reasoning Framework

SWRL rule definitions and ontology relationships supporting selected tool classifications and recommendations.

### Query-Based Decision Support

DL and SPARQL query methods for retrieving tool information, skill-level relationships and workflow associations.

### Direct and Indirect Relationship Analysis

SPARQL queries for examining direct tool relationships and multi-step reachability within the ontology.

The reachability analysis demonstrates how property-path querying can identify connections that are not explicitly represented as direct relationships.

### Cybersecurity Education

A research prototype designed to help learners understand cybersecurity tool selection through structured semantic knowledge.

### Research Reproducibility

The original ontology, dissertation and implementation screenshots, together with the separate 2026 inferred ontology and five documented SPARQL queries, provide artefacts that can support further testing and independent examination.

These contributions are demonstrated within the scope of the MSc research project and subsequent technical validation.

Broader claims of research novelty, independent recognition or industry impact require additional evidence.

---

## 14. Ethical and Legal Considerations

The project is intended for cybersecurity education, research and authorised security testing.

The original ontology includes an ethical annotation stating that the ontology and taxonomy are designed for lawful penetration testing and cybersecurity training within authorised environments.

Users must obtain appropriate permission before conducting security assessments and comply with applicable laws and professional standards.

The presence of a tool recommendation does not authorise testing against third-party systems.

---

## 15. Research Limitations

The original research identifies several limitations:

- The ontology covers a selected subset of Kali Linux tools.
- Tool knowledge is maintained primarily through manual ontology editing.
- Some workflow relationships are explicitly modelled rather than automatically discovered.
- The prototype operates primarily within Protégé.
- No standalone production web interface or API was developed.
- User feedback involved a small exploratory group.
- Further independent testing is required to establish broader reliability.
- The October 2026 SWRL execution and query results provide functional validation, but broader independent reproducibility and accuracy evaluation remain necessary.
- Reachability analysis establishes graph connectivity within the ontology rather than practical workflow suitability.
- The reachability test does not establish shortest paths, optimal execution order or operational safety.

---

## 16. Future Research and Development

Potential improvements include:

- Expanding coverage to additional Kali Linux tools.
- Automating the collection and updating of tool information.
- Developing a user-friendly web interface.
- Supporting natural-language cybersecurity task descriptions.
- Hosting the ontology through a semantic query service.
- Improving tool workflow recommendations.
- Standardising ontology naming conventions.
- Conducting larger independent usability and accuracy evaluations.
- Extending reachability analysis to support more complex tool chains.
- Visualising direct and indirect relationships through interactive graph representations.
- Collaborating with cybersecurity researchers and open-source contributors.

---

## 17. Repository Contents

The repository contains:

- The original MSc Cybersecurity dissertation.
- The original 2025 OWL research ontology.
- A separate 2026 OWL ontology containing transferred SWRL inferences.
- Five documented SPARQL query files in the [queries folder](queries/).
- Screenshots of ontology classes, relationships, cybersecurity tasks and categories.
- User-level classification and object/data property documentation.
- OntoGraf visualisations, SWRL demonstrations and DL/SPARQL query screenshots.
- Original research evidence and additional 2026 validation results.

### Main Research Files

**2025 Original Ontology:** [kali_linux_tool_recommendation_ontology.owl](kali_linux_tool_recommendation_ontology.owl)

**2026 Inferred Ontology:** [kali_linux_tool_recommendation_inferred.owl](kali_linux_tool_recommendation_inferred.owl)

**SPARQL Query Files:** [queries/](queries/)

**Detailed Query Documentation:** [queries/README.md](queries/README.md)

### Five Verified SPARQL Queries

| Query File | Research Capability |
|---|---|
| [password_cracking.rq](queries/password_cracking.rq) | Task-based tool retrieval |
| [skill_level_filtering.rq](queries/skill_level_filtering.rq) | User skill-level filtering |
| [suggested_tools.rq](queries/suggested_tools.rq) | SWRL-based classification retrieval |
| [tool_sequencing.rq](queries/tool_sequencing.rq) | Direct tool relationships |
| [tool_reachability.rq](queries/tool_reachability.rq) | Direct and indirect reachability |

**GitHub Repository:** https://github.com/Effiong-Okon-Antai/kali-linux-knowledge-based-system

---

## 18. Research Status and Acknowledgement

**Research Status:** Completed MSc research prototype (2025), with additional SWRL inference and five SPARQL query validations documented in October 2026.

The repository documents the original research implementation and distinguishes it from additional 2026 technical verification, providing a foundation for reproducibility and future development.

The project is not presented as a commercially deployed or independently certified cybersecurity product.

### Acknowledgement

I acknowledge the academic guidance and supervision of **Dr Richard Otuka**, Nottingham Trent University, during the development and evaluation of this MSc Cybersecurity research project.

### Author

**Effiong Okon Antai**  
MSc Cybersecurity — Nottingham Trent University

**Research Interests:** Cybersecurity, Semantic Web Technologies, Knowledge-Based Systems, Digital Forensics and Smart Energy Systems Security.
