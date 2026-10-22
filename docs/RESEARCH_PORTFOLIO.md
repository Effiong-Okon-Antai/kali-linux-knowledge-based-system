
# Cybersecurity Research Portfolio

## A Semantically Developed Knowledge-Based System for Deploying Kali Linux Tools

**Researcher:** Effiong Okon Antai  
**Qualification:** MSc Cybersecurity (Merit)  
**Institution:** Nottingham Trent University, United Kingdom  
**Research Supervisor:** Dr Richard Otuka  
**Research Completed:** September 2025  
**Additional Technical Validation:** October 2026

---

## 1. Research Summary

This project investigates the application of Semantic Web technologies to cybersecurity tool selection.

I designed and implemented an ontology-based Knowledge-Based System (KBS) to represent Kali Linux tools, cybersecurity tasks, user experience levels and tool relationships.

The research explores how structured knowledge representation, semantic reasoning and SPARQL queries can assist learners and practitioners in identifying tools relevant to specific cybersecurity activities.

The implementation was developed and evaluated using Protégé as part of my MSc Cybersecurity research.

## 2. Research Problem

Kali Linux contains numerous tools with different technical functions, capabilities and experience requirements.

Selecting suitable tools can be challenging, particularly for learners who are unfamiliar with cybersecurity tool categories and workflows.

This project explores an ontology-based approach to organising this knowledge and retrieving task-relevant tool information.

## 3. Technical Implementation

The research combines the following technologies:

| Technology | Application |
|---|---|
| Protégé | Ontology design and development |
| OWL 2 | Formal cybersecurity knowledge representation |
| RDF | Semantic data representation |
| SWRL | Rule-based tool classifications |
| Pellet | Ontology reasoning |
| Drools | SWRL rule execution |
| SPARQL | Semantic knowledge retrieval |
| Description Logic | Class-based reasoning and queries |
| OntoGraf | Ontology visualisation |

## 4. Ontology Design

The knowledge model represents five principal concepts:

- Tool
- Task
- Category
- UserLevel
- SuggestedTool

Semantic relationships connect tools to cybersecurity activities, categories, experience levels and other tools.

The ontology includes properties such as:

- `isUsedFor`
- `belongsToCategory`
- `requiresSkillLevel`
- `isFollowedBy`

These relationships support structured retrieval and rule-based classification.

## 5. Semantic Reasoning

SWRL rules are used to support selected tool classifications and recommendation-related concepts.

Additional validation using SWRLTab and Drools in October 2026 reported:

| Measurement | Recorded Result |
|---|---|
| SWRL rules exported | 18 |
| OWL classes exported | 31 |
| OWL individuals exported | 63 |
| OWL axioms exported | 522 |
| Inferred axioms reported | 477 |
| Execution time | 464 ms |

The inferred axiom count represents the rule engine's reported output rather than a count of unique tool recommendations.

## 6. SPARQL Query Validation

Five documented SPARQL queries were verified in Protégé.

| Query | Demonstrated Capability | Result |
|---|---|---|
| Password Cracking | Task-based tool retrieval | 3 tools |
| Skill-Level Filtering | Intermediate-level tool retrieval | 3 tools |
| Suggested Tools | SWRL-inferred classifications | Successful |
| Tool Sequencing | Direct tool relationships | 6 relationships |
| Tool Reachability | Direct and indirect relationships | 7 pairs |

### Example: Tool Reachability

The ontology contains the following relationships:

    Nikto → OpenVAS
    OpenVAS → Lynis

A SPARQL property-path query identifies Lynis as indirectly reachable from Nikto:

    Nikto → OpenVAS → Lynis

This demonstrates multi-step semantic connectivity within the knowledge model.

It does not establish that the tool sequence is operationally optimal.

## 7. Research Evaluation

The original MSc dissertation documents six evaluation scenarios involving task-based retrieval, user-level filtering, tool relationships, advanced query conditions, negative testing and performance checks.

Exploratory feedback was collected from five participants:

- Three MSc Cybersecurity students
- Two ethical hacking practitioners

The evaluation was limited in scale and does not constitute independent production validation.

## 8. Research Contributions

The project demonstrates:

1. Ontology-based representation of cybersecurity tools and activities.
2. Semantic relationships between tools, tasks, categories and user levels.
3. SWRL-based classifications and recommendation-related reasoning.
4. DL and SPARQL retrieval of cybersecurity knowledge.
5. Direct and indirect relationship analysis using SPARQL property paths.
6. Documented technical validation and research artefacts supporting reproducibility.

These are contributions within the scope of the MSc research prototype and subsequent technical validation.

## 9. Research Documentation and Evidence

- [Main Research Repository](../README.md)
- [System Architecture](SYSTEM_ARCHITECTURE.md)
- [Testing and Reproducibility Guide](TESTING_AND_REPRODUCIBILITY.md)
- [SPARQL Query Documentation](../queries/README.md)
- [Research Validation Screenshots](../evidence/README.md)
- [Original Research Ontology](../kali_linux_tool_recommendation_ontology.owl)
- [2026 Inferred Ontology](../kali_linux_tool_recommendation_inferred.owl)

## 10. Research Limitations and Future Development

The implementation is a Protégé-based research prototype rather than a commercially deployed cybersecurity product.

Future work may include:

- Expanding the ontology to additional Kali Linux tools.
- Developing a web-based recommendation interface.
- Supporting natural-language cybersecurity task descriptions.
- Improving semantic workflow recommendations.
- Conducting larger independent usability evaluations.
- Integrating more automated knowledge updates.

## 11. Research Status

**2025:** Original MSc research completed.

**October 2026:** Additional SWRL inference testing, five SPARQL query validations and reproducibility documentation.

The additional work is distinguished from the original dissertation research.

---

**Author:** Effiong Okon Antai  
**Research Interests:** Cybersecurity, Semantic Web Technologies, Knowledge-Based Systems, Digital Forensics and Smart Energy Systems Security.
