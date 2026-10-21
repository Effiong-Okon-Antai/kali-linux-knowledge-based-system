
# SPARQL Queries — Kali Linux Knowledge-Based System

## Overview

This folder contains SPARQL queries supporting the MSc Cybersecurity research project:

**A Semantically Developed Knowledge-Based System for Deploying Kali Linux Tools**

The queries demonstrate how semantic relationships can support cybersecurity tool retrieval, skill-level filtering, workflow sequencing and rule-based recommendations.

## Query Files

| File | Purpose | Validation Status |
|---|---|---|
| `password_cracking.rq` | Retrieve tools associated with password-cracking tasks | Verified in original MSc screenshots |
| `skill_level_filtering.rq` | Retrieve tools associated with the Intermediate skill level | Requires separate execution verification |
| `tool_sequencing.rq` | Retrieve relationships between tools using `isFollowedBy` | Requires separate execution verification |
| `suggested_tools.rq` | Retrieve tools classified under recommendation classes | Verified after SWRL inference transfer |

## Password-Cracking Query

The original research demonstrates task-based retrieval of:

- Hashcat
- Hydra
- JohnTheRipper

These results were recorded in the original Protégé screenshots.

## Suggested-Tool Recommendations

The recommendation query was successfully tested in Protégé after executing the SWRL rules using the Drools rule engine.

The execution reported:

- 18 SWRL rules exported.
- 477 inferred axioms.
- Successful transfer of inferred axioms into the OWL model.

The subsequent SPARQL query returned tool classifications including:

| Tool | Recommendation Class |
|---|---|
| Hydra | CrackPassword |
| JohnTheRipper | CrackPassword |
| Lynis | AttacksVulnerability |
| Nikto | AttacksVulnerability |
| OpenVAS | AttacksVulnerability |
| Reaver | CrackWireless |
| Kismet | CrackWireless |
| Wifite | CrackWireless |
| BurpSuite | ExploitWebApplication |

These examples are taken from the verified Protégé results.

## Reproducing the Results

1. Open the project's OWL ontology in Protégé.
2. Inspect the classes, properties and individuals.
3. Run the task-based SPARQL queries.
4. For inferred recommendation classifications, open SWRLTab.
5. Transfer the OWL knowledge and SWRL rules into Drools.
6. Execute the Drools rule engine.
7. Inspect the inferred axioms.
8. Work on a separate copy of the ontology before transferring inferred axioms back into the OWL model.
9. Run `suggested_tools.rq` against the resulting inferred ontology.

## Research Provenance

The original MSc research was completed in August 2025.

The executable query files were documented or reconstructed in October 2026 using the original ontology and Protégé research screenshots.

The original screenshots are retained as historical evidence. Newly reconstructed queries are distinguished from queries demonstrated in the original research.

## Responsible Use

All queries and recommendations are intended for education, research and authorised cybersecurity testing.
