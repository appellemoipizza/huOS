\# architecture



huos is designed as a layered local-first system.



the goal is structural clarity, deterministic storage, and optional ai assistance without dependency.



---



\## system layers



huos is composed of four distinct layers:



1\. storage layer  

2\. interface layer  

3\. ai layer  

4\. governance layer  



each layer has a single responsibility.



---



\## storage layer



\- sqlite database (`entries.db`)

\- single-table design (`entries`)

\- wal journaling enabled

\- automatic backups

\- deterministic writes (explicit confirmation before commit)



the storage layer is the source of truth.



no ai component has write authority outside confirmed user actions.



---



\## interface layer



\- python cli

\- optional web interface

\- fast startup (no ai calls at boot)

\- lazy loading for classification only



the interface exists to:



\- capture entries

\- retrieve entries

\- display statistics

\- manage edits and links



---



\## ai layer



\- ollama (local inference runtime)

\- phi-3.5 model for classification



ai assists by:



\- suggesting pillar

\- generating one-sentence summary

\- providing confidence score



ai output is constrained and validated before persistence.



all inference runs locally.



---



\## governance layer



\- stable pillar model

\- strict schema discipline

\- controlled feature expansion

\- versioned changelog



schema changes are additive only.  

breaking changes are avoided.



---



\## data flow



capture → ai classification → recap → save → stats update



writes occur only after explicit confirmation.



---



\## design decisions



\- single-table schema for simplicity and portability

\- single-parent lineage (`derived\_from`) for clarity

\- multi-link cross references (`linked\_to`) for flexibility

\- local-first to eliminate external dependency

\- minimal boot overhead to preserve responsiveness

