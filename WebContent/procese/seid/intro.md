## Introducere

Se poate oferi cetățenilor accesul la diverse servicii publice prin intermediul semnăturii digitale avansate, chiar în absența unei cărți digitale de identitate.

Acest lucru se poate realiza prin intermediul unui sistem de eviență a identității digitale(SEID) care asociază identitatea reală a unui cetățean - cea din cartea de identitate - cu o idenditate digitală generată pe telefonul cetățeanului de o aplicație de mobil(AMID).

Odată ce s-a creat această asociere în sistemul SEID, cetățeanul poate folosi aplicația de mobil pentru a accesa diverse servicii publice, folosind respectiva identitate digitală pentru a se autentifica și pentru a semna digital diverse documente, eliminându-se astfel necesitatea semnăturii olografe și, mai ales, prezența fizică la sediul instituțiilor publice.

Un astfel de sistem poate fi implementat rapid, este la fel de sigur din punct de vedere tehnic precum un sistem bazat pe cardul digital de identitate, și nu necesită echipamente suplimentare nici în cazul beneficiarilor nici al prestatorilor de servicii, cetățenii putândul accesa prin intermediul telefonului lor mobil


#### Avantaje: 

* Poate fi implementat imediat, putând fi accesat de toți cetățenii careu au un telefon inteligent cu acces la internet
* Costuri mici - În afară de efortul de implementare și infrastructura hardware, nu exista costuri suplimentare. Nu e nevoie de token-uri digitalte sau cartele SIM pentru folosirea serviciului
* Sistemul poate fi înlocuit în timp, sau poate funcționa ca o alternativa după ce se va trece la cartea electronică de identitate
* Infrastructura dezvoltată în jurul acestui serviciu poate fi folosită în continuare și după ce se va trece la identitatea digitală bazată pe cartea electronică de identitate, putându-se face o tranziție făra întreruperea serviciilor
* Implementarea rapidă a unui proiect pilot, folosind această tehnologie, poate oferi, pe lângă beneficii reale pentru cetățeni, și o înțelegere mai exactă a proceselor și arhitecturii optime ale unui astfel de sistem.

#### Dezavantaje:

* Serviciul nu va putea fi folosit de cei care nu au telefoane mobile inteligente și o minimă cunoaștere a folosirii lor
* Nu va putea fi implementat fără acordul și colaborarea instituțiilor publice

#### Pericole

* Există pericole inerente oricărui sistem digital care lucreaza cu date sensibile, dar acestea pot fi adresate prin reguli foarte stricte de acces, printr-o infrastructură corespunzătoare și o securizare riguroasă a sistemelor
* În cazul în care dezvoltarea sistemului este făcută în circuit închis, există pericolul să aibă o calitate slabă și sa nu genereze suficientă încredere în societate - o soluție pe care o propunem este ca sistemul sa fie dezvoltat în regim open-source, astfel încât oricine dorește și are capacitatea poate să auditeze sistemul și poate contribui la dezvoltarea sa

#### Oportunități

* Mai devreme sau mai târziu va trebui să trecem la semnătura digitală, iar pandemia ne forțează să fie mai devreme. Putem sa dezvoltăm rapid un sistem de care cetățenii pot beneficia foarte repede, dar cu potențial să fie dezvoltat și utilizat pe termen lung.

* Se poate crea o comunitate deschisă care să implementeze sistemul în regim open-source și care, mai apoi, poate ajuta și la digitalizarea altor servicii publice

#### Cerințe esențiale

Cerințele avute în vedere la proiectarea sistemului sunt:

* **Unicitatea** - Odată ce un cetățean s-a înregistrat în SEID, identitatea digitală a acestuia trebuie să fie unic asociată cu identitatea sa reală și nimeni altcineva să nu poată acționa în numele său fără acordul explicit al acestuia
* **Protecția datelor cu caracter personal** - Datele cu caracter personal ale cetățenilor trebuie să fie securizate, atât în timpul stocării lor, cât și în timpul transferului lor, și să nu poată fi accesate de sistemele instituțiilor publice sau terți decât atunci când sunt absolut necesare pentru finalizarea serviciul oferit, și doar în baza legii
* **Accesibilitatea** - Cât mai mulți cetățeni trebuie să poată beneficia, într-un timp cât mai scurt, cu resurse minime, de serviciul de identitate digitală
* **Interoperabilitatea** - Cetățeanul trebuie să-și poată folosi identitatea digitală în relația cu toate instituțiile publice sau private pentru autentificare și semnătură digitală


## Arhitectură

Soluția propusă este concepută în jurul a două componente cheie:

* o aplicație de mobil ce poate asigura cetățenilor o identitate digitală avansată, generată pe telefonul lor personal și sub controlul lor total(AMID)
* o modalitatea de comunicare securizată între aplicația de mobil menționată mai sus și celelalte aplicații ce fac parte din soluție


#### Principii de proiectare

* **Briciul lui Occam** - Nu multiplicăm entitățile inutil. Folosim cât mai puține sisteme și proceduri cât mai simple pentru a îndeplini cerințele
* **Cetățeanul în centrul lucrurilor** - Nu cetățeanul trebuie să facă eforturi pentru a accesa serviciile, ci sistemele trebuie să lucreze pentru ca cetățeanul să beneficieze de serviciile oferite, cu efort minim din partea sa
* **Federalizare** - Sistemele care vor oferi servicii publice vor acționa ca niște noduri descentralizate și autonome, comunicând însă în cadrul unei rețele securizate, în baza unor "smart contracts" cu suport legal, care reglementează clar ce date pot fi accesate de anumite servicii și în ce condiții. Într-o astfel de arhitectură, există o partajare clară a datelor și serviicilor, în funcție de specificul acestora și al instituțiilor care le oferă. Unul din avantajele unei astfel e abordări este că sistemul poate fi mult mai greu de compromis în cazul unui atac din partea unui actor răuvoitor, întrucât datele nu se află toate în același loc și sub controlul unei singure instituții. De asemenea, se evită crearea unei situații de monopol, în care o singură entitate are acces la toate datele cetățenilor.
* **Open-source** - Considerăm că pentru a crește calitatea platformei, interoperabilitate, dar și încrederea la nivelul societății, este important ca dezvoltarea acesteia să se facă în regim open-source


Sistemele care vor face parte din platformă sunt:

* **AMID** - aplicație de mobil care va furniza și gestiona identitatea digitală a cetățeanului și va permite înregistrarea în SEID și accesare altor servicii publice în format digital
* **SEID** - sistem de evidență a identității digitale - gestionează asocierea dintre identitatea reală și identitatea digitală, generată de AMID și oferă suport pentru autentificarea cetățeanului, pe baza ei, în alte siteme
* **Alte sisteme** - Sisteme care oferă servicii publice în format digital și care comunică cu SEID pentru identificarea și autentificarea cetățenilor