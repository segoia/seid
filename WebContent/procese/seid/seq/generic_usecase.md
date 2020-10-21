participant Cetățean\n(prin AMID) as C
participant Sistem X as X
participant SEID as S

C->X:Accesează serviciul X
X-->S:Cere identificarea cetățeanului\npe baza identității sale digitale
Note over S:Verifică identitatea\n în baza de date proprie
Note left of S:Poate genera alerte interne\nîn cazuri specifice
S-->X:Trimite un răspuns corespunzător
Note over X:Procesează răspunsul primit\nde la SEID
Note left of X:Dacă solicitarea nu este validă
X-->C:Trimite un mesaj de eroare corespunzător
Note left of X:Dacă solicitarea este validă
Note over X:Continuă procesul specific