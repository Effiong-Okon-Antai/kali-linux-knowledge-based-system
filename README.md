
# A Semantically Developed Knowledge-Based System for Deploying Kali Linux Tools

## Research Overview

**Research Title:** A Semantically Developed Knowledge-Based System for Deploying Kali Linux Tools  
**Researcher:** Effiong Okon Antai  
**Programme:** MSc Cybersecurity  
**Institution:** Nottingham Trent University, United Kingdom  
**Research Supervisor:** Dr Richard Otuka  
**Completed:** September 2025

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

- 
## Research Ontology Versions

This repository preserves two versions of the OWL ontology developed for the research project:

**A Semantically Developed Knowledge-Based System for Deploying Kali Linux Tools**

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
- 477 inferred axioms
- Successful inference transfer into the OWL model

This version demonstrates the results of rule-based semantic reasoning.

### SPARQL Query Validation

The four documented SPARQL queries are available in the [queries folder](queries/).

They demonstrate:
1. Password-cracking tool retrieval
2. Skill-level filtering
3. SWRL-based suggested-tool classifications
4. Tool-sequencing relationships

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
| Drools | Rule engine available through the SWRLTab interface |

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
| `SuggestedToolChain` | An additional object property defined in the original ontology |

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

The original query demonstrates task-based retrieval. Skill-level filtering is a separate capability and should be verified through an appropriate skill-level query.

### Original SPARQL Query

The following query is transcribed from the original MSc research screenshot:

```sparql
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
```

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

OWL reasoning and SWRL rule execution are related but distinct processes. The presence of enabled SWRL rules and an active reasoner does not, by itself, demonstrate that every rule was executed successfully.

Further reproducibility testing can document these results separately.

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

The repository includes screenshots of the original DL and SPARQL query demonstrations.

Executable SPARQL query files may be added separately to support independent reproduction of the research.

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
4. Open the ontology file:

   [`kali_linux_tool_recommendation_ontology.owl`](./kali_linux_tool_recommendation_ontology.owl)

5. Inspect the **Classes** tab to explore the ontology hierarchy.
6. Inspect **Object properties** and **Data properties**.
7. Open **Individuals by class** to examine tools, tasks, categories and user levels.
8. Inspect the **SWRLTab** to review the reasoning rules.
9. Configure a compatible reasoner to examine consistency and inferred relationships.
10. Use **DL Query** or a compatible **SPARQL Query** interface to reproduce the research examples.
11. Compare the results with the original dissertation and screenshots.

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

### Cybersecurity Education

A research prototype designed to help learners understand cybersecurity tool selection through structured semantic knowledge.

### Research Reproducibility

The ontology, dissertation and original implementation screenshots provide artefacts that can support further testing and independent examination.

These contributions are demonstrated within the scope of the MSc research project. Broader claims of research novelty, independent recognition or industry impact require additional evidence.

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
- Full SWRL rule execution and inference reproducibility require additional verification.

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
- Collaborating with cybersecurity researchers and open-source contributors.

---

## 17. Repository Contents

The repository contains:

- The original MSc Cybersecurity dissertation.
- The OWL ontology artefact.
- Screenshots of ontology classes and relationships.
- Screenshots of cybersecurity tasks and categories.
- User-level classification screenshots.
- Object and data property documentation.
- OntoGraf visualisations.
- SWRL rule demonstrations.
- DL and SPARQL query screenshots.
- Query outputs and supporting implementation evidence.

**Ontology File:** [`kali_linux_tool_recommendation_ontology.owl`](./kali_linux_tool_recommendation_ontology.owl)

**GitHub Repository:** https://github.com/Effiong-Okon-Antai/kali-linux-knowledge-based-system

---

## 18. Research Status and Acknowledgement

**Research Status:** Completed MSc research prototype (2025), with further technical validation and development opportunities.

The repository documents the original research implementation and provides a foundation for reproducibility and future development.

The project is not presented as a commercially deployed or independently certified cybersecurity product.

### Acknowledgement

I acknowledge the academic guidance and supervision of **Dr Richard Otuka**, Nottingham Trent University, during the development and evaluation of this MSc Cybersecurity research project.

### Author

**Effiong Okon Antai**  
MSc Cybersecurity — Nottingham Trent University

**Research Interests:** Cybersecurity, Semantic Web Technologies, Knowledge-Based Systems, Digital Forensics and Smart Energy Systems Security.
