# Uživatelská specifikace

## Role

Každý uživatel platformy má přiřazenou roli. Tyto role by se navzájem měly
vylučovat -- jako školitel bych např. neměl mít možnost plnit modul. Uživatel
ale může mít víc rolí zároveň, např. manažer může zároveň být i školitel.

### Rezident

Jako rezidentovi mi mohou být přiřazeny moduly, které mohu plnit žádáním o
potvrzení jednotlivých úkolů.

### Školitel (učitel v nahrávce)

Jako školitel mohu potvrzovat mně přiřazeným rezidentům úkoly v modulu.

*Jak přesně funguje toto přiřazování? Jsou mi přiřazeni rezidenti? Rezidenti v
rámci jednoho modulu? Modul a tranzitivně potom všichni rezidenti v něm? Kdo mi
moduly a rezidenty přiřazuje? Toto celé je ještě potřeba dořešit.* 
(P: ja bych rekl ze manazer priradi rezidenty do kurzi a priradi skolitele. 
tudiz jedina funkcionalita skolitele je skutecne jenom potvrzovat zadosti)

### Manažer

Jako manažer vidím v systému mně přiřazené školitele, jejich rezidenty a postup
těchto rezidentů.

*Mohu jako manažer přiřazovat rezidenty do kurzů? A co rezidenty ke
školitelům?* (P: ano)

*Jaký význam má role manažera? Jeho existenci je nutné lépe motivovat.* (P: "spravci" celeho systemu potvrovani)

### Administrátor

Jako administrátor systému mohu cokoliv, zejména však vytvářet kurzy a
přiřazovat k nim uživatele. (P: to muze hlavne i manazer, administrator potom je hlavne k CRUD operacema nad uctama)

## Moduly

Modul je základní jednotkou platformy a minimálně musí mít:

- název;
- autora;
- kompetence;
- prerekvizity.
- deadline!

- verze, platnost, garant, rezident, školitel ... (vzato z pdfka)

Modul je tvořen úkoly, viz sekce níže. Ty mohou být rozděleny na sekce, např,
odborné znalosti, praktické dovednosti, výkony, observace...

*Jak má být u modulů řešena návaznost? Jsou prerekvizity pouze slovní, nebo se
zadávají i moduly, které je nutné splnit před?* (P: druha varianta, ID modulu prerekvizitnich)

*Jak si mám představit, že každý modul může mít vlastního administrátora? Viz
nahrávka z meetingu.* (P: mozna garant? jak je napsany v pdfku. nejspise nekdo, kdo ho jako jediny bude moct upravovat)

## Úkoly

Rezident během plnění modulu žádá školitele o potvrzení jednotlivých úkolů.
Nabízí se dva způsoby, jak toto provádět:

- Rezident označí, co chce potvrdit. Zobrazí se mu QR kód,
  který školitel naskenuje a tím rezidentovi vybrané úkoly potvrdí.
- Rezident označí, co chce potvrdit. Školitel dostane oznámeni,
  které odklikne a tím se rezidentovi vybrané úkoly potvrdí.

*Je nutné lépe motivovat, proč by si měl rezident o potvrzení žádat. Pokud je
školitel na místě a vidí práci rezidenta, pak může příslušné úkoly potvrdit sám
od sebe.* (P: mechanismus "uznani" i bez zadosti?)

*Jak ošetřit případ, kdy rezident bude chtít podvádět a pokusí se nechat si
potvrdit i úkoly, které neprovedl?* (TODO)

Některé úkoly může schválit jen školitel, kterého má rezident přiřazeného. Jiné
může schválit kdokoliv s potřebnou rolí.

*Není zřejmé, k čemu je toto dobré. Nutno podložit příklady scénářů.* (real TODO, jako easy na implemetaci ale proc?)

Úkoly nemusí být plněny postupně -- neexistuje mezi nimi návaznost.

*Co může školitel do potvrzení zadat? Splněno? Číselné skóre?* (P: asi staci jenom bool 0-1)

## Technické poznámky

Platforma bude realizována jako webová služba. Aplikace není potřeba, možnost
přístupu z telefonu je však žádoucí.

Tvorba modulů bude probíhat ve vlastním editoru.

Moduly by mělo jít vytvořit také jako šablony. Vybrané šablony mohou být do
platformy zahrnuty jako výchozí.

## Slovník

| Termín         | Význam                                        |
|----------------|-----------------------------------------------|
| modul          | kurz                                          |
| kompetence     | co splnění kurzu rezidenta opravňuje          |
| prerekvizity   | předpoklady pro zahájení kurzu                |
| rezident       | žák                                           |
| školitel       | učitel                                        |
