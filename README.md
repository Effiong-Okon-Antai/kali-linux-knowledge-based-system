Kali Linux Knowledge-Based System for Tool Recommendation
 Overview

This project presents a semantically developed knowledge-based system designed to recommend appropriate Kali Linux tools based on user-defined cybersecurity tasks and skill levels.

It addresses a common challenge in cybersecurity: selecting the right tools efficiently, especially for beginners and intermediate users navigating complex penetration testing environments.

 Objective

The goal of this system is to:

Assist users in identifying suitable cybersecurity tools
Map tasks to relevant Kali Linux tools
Recommend tools based on user expertise (Beginner, Intermediate, Advanced)
Improve learning and operational efficiency in penetration testing
 Problem Statement

Cybersecurity practitioners often face:

Difficulty choosing the right tools for specific tasks
Lack of structured guidance on tool usage
Inefficient workflows due to trial-and-error approaches

This system provides a structured, intelligent solution using semantic technologies.

 Technologies Used
Protégé – Ontology development environment
OWL (Web Ontology Language)
SWRL (Semantic Web Rule Language)
SPARQL Queries
Pellet Reasoner
 System Design
Key Classes:
Tool
Task
Category
UserLevel
SuggestedTool
Key Properties:
isUsedFor
belongsToCategory
requiresSkillLevel
isFollowedBy
SuggestedToolChain
hasCommand
hasDescription
 Tools Covered

The system includes widely used cybersecurity tools such as:

Nmap – Network scanning
Netdiscover – Network discovery
Hashcat – Password cracking
John the Ripper – Password auditing
Hydra – Brute-force attacks
Aircrack-ng – Wireless security testing
Reaver – WPS attack tool
Zenmap – GUI for Nmap
 Example Use Case

Task: Password Cracking
User Level: Intermediate

Recommended Tools:

Hashcat
John the Ripper
Hydra
 System Capabilities
Task-based tool recommendation
Skill-level filtering
Logical tool chaining for workflows
Semantic reasoning for decision support
 Testing & Validation

The system was validated using:

Scenario-based queries
Ontology reasoning (Pellet)
Feedback from MSc-level cybersecurity students

Results showed improved clarity in tool selection and structured workflow understanding.

 Innovation & Contribution

This project demonstrates:

Application of semantic web technologies in cybersecurity
A structured method for tool recommendation and decision-making
Contribution to cybersecurity education and usability

It bridges the gap between theoretical learning and practical tool application.

 Relevance

This system supports:

Cybersecurity learners
Penetration testers
IT professionals

By simplifying how tools are selected and used in real-world scenarios.

 Future Improvements
Integration with real-time cybersecurity tools
AI-based recommendation enhancements
Expansion to enterprise-level security workflows
Web-based interface for accessibility
 Repository Contents
Ontology files (.owl, .ttl)
Project documentation (PDF)
Screenshots of system implementation
Sample queries and outputs
 Author

Effiong Okon Antai
MSc Cybersecurity – Nottingham Trent University

Note

This project was developed as part of an MSc Cybersecurity programme and demonstrates practical application of knowledge-based systems in cybersecurity.

⭐ Acknowledgment

Special thanks to Nottingham Trent University and my academic supervisor for guidance and support throughout this project.
