\# changelog



all notable structural changes to huos are documented here.



this file focuses on system architecture and storage evolution.



---



\## 1.0.0



\### highlights



\- fully local-first system (no external saas required)

\- sqlite confirmed as canonical memory layer

\- stable entry schema finalized

\- optional local ai assistance via ollama

\- clear separation between storage, interface, and ai layers



\### final entry schema



\- id

\- pillar

\- created\_at

\- derived\_from

\- linked\_to

\- title

\- summary

\- body

\- type



\### details



\- `derived\_from` remains single-parent lineage link (nullable)

\- `linked\_to` supports multi-id cross-referencing

\- `type` enables lightweight classification without expanding ontology

\- safe schema migration runs automatically at startup

\- cli capture flow stabilized with explicit save confirmation

\- project structure standardized:

&nbsp; - /human\_os

&nbsp; - /system

&nbsp; - /inbox



this version marks the shift from experimental design to stable operational system.



---



\## 0.9.x — local execution phase



\### added



\- python cli prototype

\- sqlite-based storage (`entries.db`)

\- full crud workflow (create, list, search, view, edit, delete)



\### improved



\- deterministic write flow

\- nullable lineage support

\- schema auto-migration checks

\- performance-focused input handling



\### ai integration



\- local ollama runtime support

\- optional ai metadata suggestions

\- manual / ai / ai + review capture modes

\- ai remains assistive, not authoritative



this phase moved huos from concept to working local system.



---



\## 0.8.x — governance simplification



\- converted system layer to markdown

\- removed redundant schema formalism

\- simplified ontology structure

\- reduced conceptual overhead



---



\## 0.7.x — ontology reduction



\- reduced object and relation types to essentials

\- focus shifted from theoretical modeling to practical usage

\- structural enforcement postponed



---



\## 0.6.x — graph model transition



\- replaced hierarchical structure with relational model

\- unified content under entry-based system

\- introduced lineage via `derived\_from`

\- flattened nested hierarchy



---



\## 0.5.x — structural audit



\- simplified hierarchy

\- separated user-mode and admin-mode thinking



---



\## 0.4.x and earlier



\- system layer introduced

\- architecture overview created

\- version tracking started

\- initial ontology and principles defined

