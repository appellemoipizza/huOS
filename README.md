
# huos

huos (human operating system) is a local-first personal knowledge system designed to structure long-term experience into a stable, queryable format.

it runs entirely on your machine.

no cloud.  
no external storage.  
no hidden services.

this repository contains the interface layer only.  
runtime data and private context files are intentionally excluded.

---

## what it does

huos captures entries into a constrained schema and stores them in sqlite.

each entry belongs to exactly one pillar and follows a fixed structure.  
this keeps retrieval clean and statistics meaningful.

as entries accumulate, the system can surface patterns across time.

this is not a journaling app.  
it is a structured memory system.

---

## entry schema

each entry includes:

- id  
- pillar  
- created_at  
- derived_from  
- linked_to  
- title  
- summary  
- body  
- type  

`derived_from` supports single-parent lineage.  
`linked_to` allows cross-referencing multiple entries.  
`type` enables lightweight classification without expanding the ontology.

the schema is intentionally minimal and stable.

---

## pillar model

huos organizes entries into five domains:

- cognition — reasoning, learning, decision making  
- physiology — sleep, energy, stress, biological state  
- identity — self-concept and narrative continuity  
- direction — goals, priorities, strategic intent  
- creation — execution and tangible output  

each entry belongs to exactly one pillar.  
this constraint preserves clarity.

---

## statistics

huos includes local statistical introspection:

- total entries  
- entries per pillar  
- weekly signal extraction  
- most frequent meaningful word (last 7 days)  
- dominant sensory signal  
- dominant emotional signal  

analysis is lightweight and runs locally.

the goal is awareness, not vanity metrics.

---

## leveling system

huos includes a subtle xp system:

- 10 xp per entry  
- quadratic progression  
- level and xp shown in stats  

this reinforces consistency without turning the system into a game.

---

## ai integration

huos integrates:

- ollama as local inference runtime  
- phi-3.5 as classification model  

the ai:

- suggests a pillar  
- generates a one-sentence summary  
- outputs a confidence score  
- follows a strict json contract  

ai assists structure.  
it does not override user input.

all inference runs locally.

---

## architecture

stack:

- python  
- sqlite  
- ollama + phi-3.5  
- wal journaling  
- automatic backups  
- single-instance lock enforcement  

startup is lightweight:

- no ai calls at boot  
- no unnecessary loading  
- classification runs only when needed  

performance and determinism are prioritized.

---

## execution flow

1. capture entry  
2. optional ai classification  
3. recap screen  
4. save or discard  
5. immediate availability in stats  

---

## deliberate exclusions

this repository does not include:

- entries.db  
- backups  
- private ai context files  
- local configuration files  

this repo represents the distributable surface layer only.

---

## how to run

requirements:

- python 3.10+  
- ollama installed locally  
- phi-3.5 model pulled  

install model:

    ollama pull phi3.5

run cli:

    python hu_os.py

run web interface:

    python web_app.py