
# Knowledge-Based System Architecture

## Research Project

**Title:** A Semantically Developed Knowledge-Based System for Deploying Kali Linux Tools

**Researcher:** Effiong Okon Antai  
**Institution:** Nottingham Trent University  
**Original Research:** 2025  
**Additional Validation:** October 2026

## 1. Architecture Overview

The research implements an ontology-based Knowledge-Based System (KBS) using Semantic Web technologies.

The system represents cybersecurity tools, tasks, categories and user experience levels as interconnected semantic concepts.

Protégé provides the environment for ontology development, rule execution, reasoning and query testing.

## 2. System Architecture

The conceptual research workflow is:

    Cybersecurity Task or Query
               |
               v
      Ontology Knowledge Base
          (OWL / RDF)
               |
               v
       Semantic Relationships
       and SWRL Rule Definitions
               |
               v
       Reasoning and Inference
        (Pellet / Drools)
               |
               v
        DL / SPARQL Queries
               |
               v
      Retrieved Tool Information
       and Semantic Relationships

This diagram illustrates the research workflow rather than a deployed software application.

## 3. Knowledge Representation Layer

The ontology contains five principal classes:

| Class | Purpose |
|---|---|
| Tool | Represents cybersecurity tools |
| Task | Represents cybersecurity activities |
| Category | Groups tools by functionality |
| UserLevel | Represents experience levels |
| SuggestedTool | Represents recommendation-related concepts |

## 4. Semantic Relationship Layer

The ontology uses object properties to connect its concepts.

| Object Property | Function |
|---|---|
| isUsedFor | Connects tools with cybersecurity tasks |
| belongsToCategory | Connects tools with categories |
| requiresSkillLevel | Associates tools with experience levels |
| isFollowedBy | Represents tool-to-tool workflow relationships |
| SuggestedToolChain | Additional property defined in the original ontology |

These relationships enable semantic queries across the knowledge base.

## 5. Rule-Based Reasoning Layer

SWRL rules support selected tool classifications and recommendations.

The research uses Pellet for ontology reasoning and SWRLTab with Drools for rule execution.

Additional validation in October 2026 reported:

- 18 SWRL rules exported
- 31 OWL classes
- 63 OWL individuals
- 522 OWL axioms exported
- 477 inferred axioms reported
- Successful transfer of inferred assertions

The inferred axiom count is not equivalent to the number of unique tool recommendations.

## 6. Query and Retrieval Layer

SPARQL and Description Logic queries are used to retrieve knowledge from the ontology.

Five SPARQL queries were documented and validated:

| Query | Purpose |
|---|---|
| Password Cracking | Retrieve tools associated with password-cracking tasks |
| Skill-Level Filtering | Retrieve tools associated with a specified user level |
| Suggested Tools | Retrieve recommendation-related classifications |
| Tool Sequencing | Retrieve direct isFollowedBy relationships |
| Tool Reachability | Retrieve direct and indirect isFollowedBy relationships |

## 7. Example: Tool Reachability

The ontology represents these direct relationships:

    Nikto → OpenVAS
    OpenVAS → Lynis

A SPARQL property-path query using `isFollowedBy+` can retrieve the indirect relationship:

    Nikto → OpenVAS → Lynis

This demonstrates multi-step semantic reachability within the ontology.

It does not establish that the sequence is operationally optimal.

## 8. Research Artefacts

The repository contains:

- Original 2025 OWL ontology
- Separate 2026 inferred OWL ontology
- Five documented SPARQL query files
- Research dissertation
- Protégé screenshots
- SWRL reasoning validation evidence

## 9. Research Limitations

The system is a Protégé-based research prototype.

It does not currently provide a production web application or API.

Tool relationships are based on the ontology's represented knowledge and require further evaluation before being treated as operational recommendations.

## 10. Further Development

Potential extensions include:

- A web-based query interface
- Natural-language task input
- Expanded Kali Linux tool coverage
- Automated ontology updates
- Improved workflow recommendation methods
- Interactive graph visualisation
- Independent evaluation with a larger user group

## 11. Supporting Documentation

[Main Research README](../README.md)

[SPARQL Query Documentation](../queries/README.md)

[Research Validation Evidence](../evidence/README.md)

---

**Author:** Effiong Okon Antai
