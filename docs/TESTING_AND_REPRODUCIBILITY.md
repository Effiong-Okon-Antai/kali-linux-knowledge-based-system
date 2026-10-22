
# Testing and Reproducibility Guide

## Research Project

**Title:** A Semantically Developed Knowledge-Based System for Deploying Kali Linux Tools

**Researcher:** Effiong Okon Antai  
**Original MSc Research:** 2025  
**Additional Validation:** October 2026

## 1. Purpose

This document explains how to examine the ontology, execute semantic reasoning rules and reproduce the documented SPARQL query results.

The implementation is a Protégé-based research prototype.

## 2. Required Software

- Protégé Desktop
- SWRLTab with Drools rule engine support
- Compatible OWL reasoner
- SPARQL query interface

Software and plugin compatibility may vary between versions.

## 3. Research Files

| File | Purpose |
|---|---|
| `kali_linux_tool_recommendation_ontology.owl` | Original 2025 research ontology |
| `kali_linux_tool_recommendation_inferred.owl` | Ontology containing transferred SWRL inferences |
| `queries/` | Five SPARQL query files |
| `evidence/` | Screenshots of validation results |

## 4. Opening the Ontology

1. Launch Protégé Desktop.
2. Select File → Open.
3. Open `kali_linux_tool_recommendation_ontology.owl`.
4. Inspect the Classes, Object properties and Individuals tabs.
5. Open SWRLTab to inspect the rule definitions.

The original ontology should be preserved unchanged for research comparison.

## 5. Executing SWRL Rules

1. Open SWRLTab.
2. Select the Control panel.
3. Click `OWL+SWRL->Drools`.
4. Click `Run Drools`.
5. Examine the reported execution results.
6. Click `Drools->OWL` to transfer inferred assertions when required.

For reproducibility, perform inference transfer on a working copy rather than overwriting the original research ontology.

### Recorded October 2026 Results

| Measurement | Result |
|---|---|
| SWRL rules exported | 18 |
| OWL classes exported | 31 |
| OWL individuals exported | 63 |
| Object property declarations | 5 |
| Data property declarations | 7 |
| OWL axioms exported | 522 |
| Inferred axioms reported | 477 |
| Execution time | 464 ms |

The counts reflect the recorded test environment and may vary in another configuration.

## 6. Executing SPARQL Queries

Open the appropriate ontology in a compatible SPARQL query interface.

Use the files in the `queries/` directory.

### Test 1: Password-Cracking Retrieval

**File:** `queries/password_cracking.rq`

**Expected documented result:** Hashcat, Hydra and JohnTheRipper.

**Recorded outcome:** PASS — 3 tools.

### Test 2: Skill-Level Filtering

**File:** `queries/skill_level_filtering.rq`

**Expected documented result:** BurpSuite, Kismet and OWASPZAP.

**Recorded outcome:** PASS — 3 Intermediate-level tools.

### Test 3: Suggested-Tool Classifications

**File:** `queries/suggested_tools.rq`

Use the inferred ontology or execute SWRL rules and transfer inferred assertions before testing.

**Expected documented result:** Recommendation-related classifications including Hydra as CrackPassword and Nikto as AttacksVulnerability.

**Recorded outcome:** PASS.

### Test 4: Direct Tool Sequencing

**File:** `queries/tool_sequencing.rq`

**Expected documented result:** 6 direct `isFollowedBy` relationships.

**Recorded outcome:** PASS.

### Test 5: Tool Reachability

**File:** `queries/tool_reachability.rq`

**Expected documented result:** 7 reachable tool pairs, including the indirect connection from Nikto to Lynis through OpenVAS.

**Recorded outcome:** PASS.

## 7. Validation Evidence

Screenshots of the recorded tests are available in the [Research Validation Evidence folder](../evidence/README.md).

These screenshots provide evidence of observed Protégé execution results.

## 8. Reproducibility Considerations

- Preserve the original 2025 ontology.
- Distinguish asserted relationships from SWRL-inferred assertions.
- Record the Protégé and plugin versions when repeating tests.
- Ensure the query namespace matches the ontology.
- Use the inferred ontology for tests requiring transferred SWRL assertions.
- Compare actual results against the documented outputs.
- Record any differences rather than changing results to match expectations.

## 9. Limitations

Successful query execution demonstrates retrieval of relationships represented in the ontology.

It does not establish that the model covers every Kali Linux tool or that its recommended sequences are operationally optimal.

The October 2026 validation is additional work and should not be represented as part of the original 2025 dissertation evaluation.

## 10. Related Documentation

- [Main Research README](../README.md)
- [System Architecture](SYSTEM_ARCHITECTURE.md)
- [SPARQL Queries](../queries/README.md)
- [Validation Evidence](../evidence/README.md)

---

**Author:** Effiong Okon Antai
