Kali Linux Knowledge-Based System for Intelligent Tool Recommendation
Research Overview
Research title: A Semantically Developed Knowledge-Based System for Deploying Kali Linux Tools
Researcher: Effiong Okon Antai
Programme: MSc Cybersecurity
Institution: Nottingham Trent University, United Kingdom
Supervisor: Dr Richard Otuka
Completed: August 2025

This project documents an ontology-based knowledge-based system (KBS) developed to recommend Kali Linux cybersecurity tools according to cybersecurity tasks, tool relationships and user skill levels. It uses Semantic Web technologies to represent tool knowledge and support task-based retrieval and reasoning within a Protégé research prototype.

The project is intended for cybersecurity education, research and authorised security testing. It is not a deployed standalone application. The UserLevel class in the original ontology also carries an rdfs:comment stating that the ontology and taxonomy are intended strictly for lawful penetration testing and cybersecurity training in authorised environments.
1. Research Problem
Kali Linux contains many tools for network analysis, penetration testing, vulnerability assessment and digital forensics. Learners and practitioners can find it difficult to identify appropriate tools and understand how tools relate to tasks or to one another.

This research investigates whether structured ontology modelling, semantic queries and rules can provide more systematic tool-selection guidance than a simple static tool list.
2. Aim and Objectives
Aim: Design and evaluate a knowledge-based system that supports the selection of Kali Linux tools for defined cybersecurity tasks.

Objectives:
- Represent tools, tasks, categories and user levels in an ontology.
- Model relationships between tools and cybersecurity activities.
- Define semantic rules supporting tool classification and recommendation.
- Retrieve tool information through Description Logic (DL) and SPARQL queries.
- Test task-based retrieval, skill-level filtering and tool relationships.
- Assess the prototype's usefulness and identify its limitations.
3. Technologies Used
Technology	Role in the project
Protégé	Ontology authoring and inspection
OWL 2 / RDF	Semantic knowledge representation
SWRL	Rule definitions for classification and inference
Pellet	Reasoning used in the original research
SPARQL	Retrieval of tools and their properties
Description Logic	Class-based ontology queries
OntoGraf	Visualisation of ontology relationships


4. Ontology Design and System Architecture
Core classes
The top-level classes visible in the original Protégé screenshots are:
- Tool
- Task
- Category
- UserLevel
- SuggestedTool
Class hierarchy shown in Protégé
The screenshots also show the following subclasses:
- Under Tool: ExploitationTool, ForensicsTool, NetworkScanningTool, PasswordCrackingTool, ReportingTool, SniffingSpoofingTool, VulnerabilityAnalysisTool and WirelessAttackTool.
- Under UserLevel: AdvancedTool, BeginnerTool and IntermediateTool.
- Under SuggestedTool: task-oriented recommendation classes such as CrackPassword, CrackWireless, InformationGathering, PortScanner, ScanningForensics, ExploitWebApplication and ReportCollaborationTool.
These names reflect the original ontology hierarchy as shown, including its unconventional placement of the tool-level subclasses beneath UserLevel. They have not been silently reorganised.
Object properties
The original Protégé object-property hierarchy shows:
- belongsToCategory — relates tools to categories.
- isFollowedBy — describes a possible tool sequence.
- isUsedFor — relates tools to tasks.
- requiresSkillLevel — relates tools to skill levels.
- SuggestedToolChain — an object property present in the original ontology; its exact usage should be inspected in the ontology before drawing further conclusions.
Data properties
The original Protégé data-property screenshot shows:
- hasCommand — stores example command text.
- hasDescription — stores descriptive information.
Represented individuals
The UserLevel class has three visible individuals: Beginner, Intermediate and Advanced. These are individuals, distinct from the subclasses BeginnerTool, IntermediateTool and AdvancedTool.

The Task class screenshot shows individuals including AnalyzeArtifacts, AnalyzeFileSystem, AnalyzeFirmware, AnalyzeMemory, AnalyzeTraffic, CrackPassWord, FindExploits, GeneratePayload, PortScanner, ScanVulnerabilities and TestWifiSecurity. One task is labelled find live hosts in the original interface. The examples are illustrative, not an exhaustive inventory.

The Category class screenshot shows individuals such as AttacksMiTM, AttacksVulnerability, CrackingPassWord, CrackingWireless, ExploitationWeb, InformationGathering, ManInTheMiddle, ReportCollaborationTool and ScanningForensics.

Modelling note: Similar identifiers appear in different parts of the ontology, including CrackPassWord, CrackingPassWord and CrackPassword. The original names are retained for fidelity; future revisions can standardise naming after checking their intended meanings and references.
Research workflow
1. Identify a cybersecurity task.
2. Locate the task and related tools represented in the ontology.
3. Apply the model's class relationships and, where configured, semantic reasoning rules.
4. Run DL or SPARQL queries to retrieve matching tool information.
5. Examine tool descriptions, example commands and related workflow information where available.
This workflow is demonstrated in the Protégé environment rather than through a production web interface.
5. Cybersecurity Tools Covered
The ontology contains selected tools from network scanning, password security assessment, wireless security testing and other cybersecurity categories.
Tool	Primary function
Nmap	Network scanning
Netdiscover	Network discovery
Hashcat	Password cracking
John the Ripper	Password auditing
Hydra	Password authentication testing
Aircrack-ng	Wireless security testing
Reaver	WPS security assessment
Zenmap	Graphical interface for Nmap


The research also discusses tools for vulnerability analysis, web application security, digital forensics, traffic analysis, exploitation testing and reporting.
6. Example Use Case: Password Cracking
Task: Password Cracking
User level: Advanced
Tools returned by the original task-based SPARQL query:
- Hashcat
- Hydra
- JohnTheRipper
The original Protégé screenshots show a SPARQL query matching the password-cracking task label and retrieving these three tools, with optional labels and example command values.

Important distinction: The screenshot demonstrates task-based retrieval. It does not by itself establish that this specific query filtered results by user level. The Advanced label reflects the skill classification identified in the ontology and should be tested separately through a skill-level query.
Example query transcribed from the original screenshot
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
The query is shown here as a transcription of the original research screenshot. Additional query files can be supplied separately for repeatable testing.
7. Semantic Reasoning and SWRL Rules
The project defines SWRL rules for selected tool and category classifications. The original SWRLTab screenshot shows enabled rules with names including BeginnerTools, Intermediate Tool, CrackPassword, CrackWireless, InformationGathering, PortScanner, AttacksVulnerability and ExploitWebApplication.

For example, the visible beginner-level rule associates a Tool with Beginner through requiresSkillLevel and classifies it as BeginnerTool. Other rules use belongsToCategory to infer task-oriented recommendation classes. The screenshot also shows rules involving the hasCommand property.

The SWRLTab control area displays instructions for the Drools rule engine. This is distinct from the use of Pellet as an OWL reasoner; rule execution should be documented separately from ordinary OWL reasoning.

The original screenshots show these rules in Protégé's SWRLTab. The presence of enabled rules and an active reasoner is evidence of the research configuration; it is not, on its own, proof that every SWRL inference was successfully executed or independently reproduced.
8. DL and SPARQL Query Capabilities
The dissertation documents queries intended to support:
- Task-based retrieval: Find tools associated with a given task.
- Skill-level filtering: Examine tools associated with particular experience levels.
- Tool relationships: Retrieve relationships such as isFollowedBy.
- Suggested recommendations: Explore asserted or inferred recommendation-related knowledge.
- Validation: Check expected results and identify incorrect or missing associations.
The repository includes original screenshots of Protégé queries and outputs. Executable .rq query files may be added as a separate reproducibility resource.
9. Testing and Evaluation
The original MSc dissertation reports six testing scenarios addressing task-based retrieval, skill-level conditions, workflow relationships, negative checks and reasoning/performance considerations.

The dissertation also describes exploratory feedback from three MSc Cybersecurity students and two ethical hacking practitioners. Participants considered selected activities including network scanning, password cracking and vulnerability scanning.

The reported results indicate that the prototype provided structured tool-selection guidance within the tested scenarios. The evaluation was small in scale and does not establish broad statistical performance, independent industry adoption or production reliability.
10. How to Explore the Ontology
1. Download or clone this repository.
2. Open Protégé Desktop.
3. Open the ontology file [`kali_linux_tool_recommendation_ontology.owl`](./kali_linux_tool_recommendation_ontology.owl).
4. Inspect Classes, Object properties, Data properties and Individuals by class.
5. Inspect the SWRLTab rules if the appropriate plugin is installed.
6. Configure a compatible reasoner and examine consistency and inferred relationships.
7. Use DL Query and a compatible SPARQL Query interface to reproduce the research examples.
8. Compare query outputs with the original screenshots and dissertation.
The .owl file may use Turtle serialisation; choose RDF/Turtle explicitly if your ontology software does not detect the format automatically. Plugin and reasoner availability varies by Protégé version.
11. Research Contributions
The MSc project developed and documented:
- A structured ontology representing selected Kali Linux tools and cybersecurity tasks.
- Semantic relationships linking tools, categories and experience levels.
- SWRL rule definitions for selected classification tasks.
- DL and SPARQL approaches to retrieving tool information and relationships.
- A research prototype and evaluation scenarios relevant to cybersecurity education.
These contributions are described within the scope of the MSc project. Broader claims of novelty, external recognition or industry impact would require additional independent evidence.
12. Ethical and Legal Use
The project is intended for learning, research and authorised cybersecurity assessments only. Tool examples and commands should be used solely in environments where the user has permission to test. The presence of a tool recommendation does not constitute permission to assess a third-party system.
13. Limitations
- The ontology covers a selected subset of Kali Linux tools.
- Tool knowledge is maintained primarily through manual ontology editing.
- Some workflow relationships are modelled rather than automatically discovered.
- The prototype operates primarily within Protégé.
- No standalone production interface or API was developed as part of the MSc project.
- User feedback involved a small exploratory group.
- Independent reproduction of the full reasoning workflow remains a future validation task.
14. Future Development
Potential future work includes expanding tool coverage, improving ontology maintenance, adding executable query examples, building a user-friendly interface, testing rule inference across supported reasoners, and carrying out larger independent evaluations.
15. Repository Contents
The repository contains the original MSc dissertation, the ontology file, and screenshots documenting ontology classes, individual tasks, categories and user levels, object and data properties, OntoGraf visualisations, SWRL rules, SPARQL queries and query outputs.
- Ontology: [`kali_linux_tool_recommendation_ontology.owl`](./kali_linux_tool_recommendation_ontology.owl)
- Repository: https://github.com/Effiong-Okon-Antai/kali-linux-knowledge-based-system
16. Research Status
Completed MSc research prototype (2025). The public repository documents the research and provides a foundation for reproducibility and future development. It is not presented as a commercially deployed or independently certified cybersecurity product.
17. Acknowledgement
I acknowledge the academic guidance and supervision of Dr Richard Otuka, Nottingham Trent University, during the MSc Cybersecurity project.
18. Author
Effiong Okon Antai
MSc Cybersecurity — Nottingham Trent University

Research interests: Cybersecurity, Semantic Web Technologies, Knowledge-Based Systems, Digital Forensics and Smart Energy Systems Security.
