\# data model



huos uses a single-table sqlite schema.



the goal is structural simplicity and long-term stability.



---



\## table: entries



fields:



\- id (primary key)

\- pillar

\- created\_at

\- derived\_from

\- linked\_to

\- title

\- summary

\- body

\- type



---



\## field explanations



\### id

unique identifier for each entry.



---



\### pillar

one of five canonical domains:



\- cognition

\- physiology

\- identity

\- direction

\- creation



each entry belongs to exactly one pillar.



---



\### created\_at

timestamp generated at creation.



---



\### derived\_from

nullable single-parent lineage reference.



used for chronological evolution of ideas.



---



\### linked\_to

comma-separated list of entry ids.



used for cross-referencing related entries without enforcing hierarchy.



---



\### title

short human-readable label. (ai-generated)



---



\### summary

single sentence summary (ai-generated).



---



\### body

main content of the entry.



---



\### type

lightweight classification field.



used for tagging without expanding ontology.



---



\## why single table



\- easier portability

\- simpler backups

\- lower cognitive overhead

\- faster iteration during early lifecycle



join tables may be introduced in later versions if relational complexity increases.

