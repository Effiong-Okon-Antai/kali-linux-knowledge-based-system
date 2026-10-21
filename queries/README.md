
# SPARQL Queries — Kali Linux Knowledge-Based System

## Research Project

**A Semantically Developed Knowledge-Based System for Deploying Kali Linux Tools**

**Researcher:** Effiong Okon Antai  
**Programme:** MSc Cybersecurity  
**Institution:** Nottingham Trent University, United Kingdom  
**Research Completed:** August 2025  
**Query Documentation Updated:** 21 October 2026

## 1. Overview

This folder contains SPARQL queries used to demonstrate and validate the semantic capabilities of the Kali Linux Knowledge-Based System (KBS).

The system was developed using OWL, Protégé, SWRL rules, the Drools rule engine and SPARQL.

It supports structured retrieval of cybersecurity tools based on tasks, user skill levels, recommendation classifications and tool-to-tool relationships.

The four query files have been tested in Protégé. Some queries were reconstructed from the original research ontology and screenshots during the October 2026 GitHub documentation process.

## 2. SPARQL Query Files

| Query File | Purpose | Validation Status |
|---|---|---|
| `password_cracking.rq` | Retrieve tools associated with password-cracking tasks | PASS — 3 tools |
| `skill_level_filtering.rq` | Retrieve tools requiring Intermediate skill level | PASS — 3 tools |
| `suggested_tools.rq` | Retrieve rule-based recommendation classifications | PASS — results returned after SWRL inference transfer |
| `tool_sequencing.rq` | Retrieve tool-to-tool workflow relationships | PASS — 6 relationships |

## 3. Password-Cracking Tool Retrieval

**Query File:** `password_cracking.rq`

### Objective

Retrieve cybersecurity tools associated with password-cracking tasks using the `isUsedFor` object property.

### Verified Results

| Tool | Task |
|---|---|
| Hashcat | Password Cracking |
| Hydra | Password Cracking |
| JohnTheRipper | Password Cracking |

**Validation Status:** PASS — 3 tools retrieved.

### Research Significance

This test demonstrates the ontology's ability to connect cybersecurity tasks with relevant tools.

It supports task-based tool discovery and reduces reliance on manually searching through large tool collections.

The results are supported by the original MSc research screenshots.

## 4. Skill-Level Filtering

**Query File:** `skill_level_filtering.rq`

**Validation Date:** 21 October 2026

### Objective

Retrieve cybersecurity tools associated with the Intermediate user skill level using the `requiresSkillLevel` object property.

### Verified Results

| Tool | Skill Level |
|---|---|
| BurpSuite | Intermediate |
| Kismet | Intermediate |
| OWASPZAP | Intermediate |

**Validation Status:** PASS — 3 tools retrieved.

### Research Significance

This test demonstrates that the ontology can retrieve cybersecurity tools according to a defined user skill level.

The capability supports structured tool selection for users with different levels of cybersecurity experience.

The results were verified in Protégé and captured in a screenshot.

## 5. SWRL-Based Suggested Tool Recommendations

**Query File:** `suggested_tools.rq`

**Validation Date:** 21 October 2026

### Objective

Retrieve cybersecurity tools classified under recommendation classes derived from the ontology's semantic structure and SWRL rules.

### Reasoning Procedure

1. Open the research ontology in Protégé.
2. Navigate to SWRLTab.
3. Transfer the OWL knowledge and SWRL rules into the Drools rule engine.
4. Execute the rules using Run Drools.
5. Inspect the inferred axioms.
6. Transfer the inferred axioms into a working copy of the OWL model.
7. Execute the suggested-tools SPARQL query.

### Verified Reasoning Results

| Measurement | Reported Result |
|---|---|
| SWRL rules exported | 18 |
| OWL classes exported | 31 |
| OWL individuals exported | 63 |
| OWL axioms exported | 522 |
| Inferred axioms reported | 477 |
| Rule execution | Successful |
| Inference transfer to OWL | Successful |

The reported 477 inferred axioms represent the rule engine's inference output, not 477 distinct tool recommendations.

### Verified Tool Classifications

| Tool | Recommendation Class |
|---|---|
| MITMf | AttacksMiTM |
| Lynis | AttacksVulnerability |
| Nikto | AttacksVulnerability |
| OpenVAS | AttacksVulnerability |
| Hydra | CrackPassword |
| JohnTheRipper | CrackPassword |
| Aircracking | CrackWireless |
| Airmonng | CrackWireless |
| Kismet | CrackWireless |
| Reaver | CrackWireless |
| Wifite | CrackWireless |
| BurpSuite | ExploitWebApplication |

**Validation Status:** PASS — recommendation classifications successfully retrieved after SWRL inference transfer.

### Research Significance

This test demonstrates the integration of rule-based reasoning with semantic query retrieval.

SWRL rules generate inferred classifications, which can subsequently be retrieved using SPARQL when the inferred assertions are available in the queried OWL model.

The test demonstrates technical reasoning and retrieval functionality. It does not independently establish recommendation accuracy or real-world deployment.

## 6. Tool Sequencing

**Query File:** `tool_sequencing.rq`

**Validation Date:** 21 October 2026

### Objective

Retrieve tool-to-tool relationships using the `isFollowedBy` object property.

### Verified Results

| First Tool | Next Tool |
|---|---|
| Aircracking | Airmonng |
| Nikto | OpenVAS |
| Nmap | Netdiscover |
| OpenVAS | Lynis |
| Reaver | Wifite |
| Wireshark | Tcpdump |

**Validation Status:** PASS — 6 tool-sequencing relationships retrieved.

### Research Significance

This test demonstrates that the ontology can represent and retrieve predefined relationships between cybersecurity tools.

The results support the research objective of modelling tool workflows through semantic relationships.

The returned sequences reflect relationships stored in the ontology. They have not been independently validated as optimal practical execution orders.

## 7. Overall Validation Summary

| Test | Result | Status |
|---|---|---|
| Task-based tool retrieval | 3 tools | PASS |
| Intermediate skill-level filtering | 3 tools | PASS |
| SWRL rule execution | 477 inferred axioms reported | PASS |
| Suggested-tool classification retrieval | Multiple classifications returned | PASS |
| Tool sequencing | 6 relationships | PASS |

All four documented SPARQL queries produced results during Protégé testing.

These tests demonstrate semantic retrieval and rule-based classification capabilities within the research ontology.

They do not constitute a production security assessment or independent benchmarking study.

## 8. Reproducing the Tests

### Requirements

- Protégé Desktop
- The research OWL ontology
- SPARQL Query tab or compatible plugin
- SWRLTab and Drools rule-engine support for SWRL inference testing

### Procedure

1. Download the OWL ontology from the main repository.
2. Open the ontology in Protégé.
3. Inspect the classes, individuals and object properties.
4. Open the SPARQL Query tab.
5. Copy a query from this folder into the query editor.
6. Click Execute and inspect the results.
7. For suggested-tool classifications, run the SWRL rules first.
8. Transfer inferred axioms into a separate working copy of the ontology.
9. Rerun `suggested_tools.rq` against the updated model.

Results may depend on the ontology version, available plugins and whether inferred assertions have been transferred into the queried model.

## 9. Evidence and Research Provenance

The project originated from MSc Cybersecurity research completed in August 2025.

Original Protégé screenshots and the research ontology document the academic implementation.

Additional SPARQL query files and validation documentation were prepared or reconstructed in October 2026 using the existing research artefacts.

The documentation distinguishes original research evidence from later reproducibility and verification work.

Screenshots provide visual evidence of the reported query outputs and reasoning execution.

## 10. Limitations

- The ontology contains a manually developed collection of cybersecurity tools and relationships.
- The current implementation operates primarily through Protégé.
- There is no production web interface or deployed recommendation API.
- Rule-based classifications depend on the relevant ontology assertions and inference process.
- Tool-sequencing relationships are modelled rather than automatically optimised.
- The demonstrated query results do not establish comprehensive tool coverage or recommendation accuracy.

## 11. Future Improvements

- Expand cybersecurity tool coverage.
- Add automated ontology population and updates.
- Develop a user-friendly recommendation interface.
- Improve validation through additional test scenarios.
- Introduce systematic recommendation accuracy and usability evaluation.
- Explore integration with authorised cybersecurity training environments.

## 12. Responsible Use

This research is intended for cybersecurity education, academic research and authorised security testing.

All penetration-testing tools and techniques should be used only in environments where appropriate permission has been obtained.

## 13. Author

**Effiong Okon Antai**  
MSc Cybersecurity  
Nottingham Trent University, United Kingdom
