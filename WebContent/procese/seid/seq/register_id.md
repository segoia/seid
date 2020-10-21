participant Cetățean\n(prin AMID) as C
participant SEID as S
C->S:Solicită statusul identității\nîn sistemul SEID
Note over S:Verifică starea
S-->C:Trimite starea curentă
Note right of C:Dacă nu este înregistrat
C->S:Trimite o cerere de înregistrare
Note over S:Preia cererea\n de înregistrare
S-->C:Solicită o copie a actului de identitate\nși o semnătură simplă
Note over C: Încarcă o poză a\ncărții de identitate(CI)
Note over C: Adaugă o semnătură simplă
C->S:Trimite poza CI alături de semnătura simplă
Note left of S:Opțional, se poate face și\n identificarea vizuală a cetățeanului\n de către un operator SEID
Note over S:Se verifică cererea
Note left of S:Dacă cererea este validă
Note over S:Asociază identitatea digitală,\ndin aplicația AMID,\n cu identiatea reală, din CI
S-->C:Se trimite confirmarea înregistrării în sistem
Note left of S:Dacă cererea este invalidă
S-->C:Se respinge cererea,\n cu mesajul de eroare corespunzător