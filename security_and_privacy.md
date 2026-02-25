\# security and privacy



huos is designed as a local-first system.



---



\## data handling



\- all data stored locally in sqlite

\- no cloud storage

\- no telemetry

\- no remote logging



---



\## ai inference



\- inference runs through local ollama runtime

\- no external api calls

\- no third-party data transfer



---



\## repository exclusions



this public repository does not include:



\- entries.db

\- backups

\- private context files

\- local configuration files

\- development artifacts



sensitive runtime files are excluded via .gitignore.



---



\## backup model



\- automatic local backups

\- wal journaling enabled

\- single-instance lock enforcement



the system prioritizes data integrity and containment.

