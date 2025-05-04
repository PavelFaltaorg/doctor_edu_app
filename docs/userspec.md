# Uživatelská specifikace

## Role

Každý uživatel platformy má přiřazenou roli. Tyto role by se navzájem měly
vylučovat -- jako školitel bych např. neměl mít možnost plnit modul. Uživatel
ale může mít víc rolí zároveň, např. manažer může zároveň být i školitel.

### Rezident

Jako rezidentovi mi mohou být přiřazeny moduly, které mohu plnit žádáním o
potvrzení jednotlivých úkolů.

### Školitel

Jako školitel mohu potvrzovat mně přiřazeným rezidentům úkoly v modulu.

*Jak funguje toto přiřazování? Jsou mi přiřazeni rezidenti? Rezidenti v rámci
jednoho modulu? Modul a tranzitivně potom všichni rezidenti v něm? Kdo mi
moduly a rezidenty přiřazuje? Celá tato hierarchie je potřeba dořešit.*

### Manažer

Jako manažer vidím v systému mně přiřazené školitele, jejich rezidenty a postup
těchto rezidentů.

*Mohu jako manažer přiřazovat rezidenty do kurzů? A co rezidenty ke
školitelům?*

*Jaký význam má role manažera? Jeho existenci je nutné lépe motivovat.*

### Administrátor

Jako administrátor systému mohu cokoliv, zejména však vytvářet kurzy a
přiřazovat k nim uživatele.

## Moduly

Modul je základní jednotkou platformy a minimálně musí mít:

- název;
- autora;
- kompetence;
- prerekvizity.

Modul je tvořen úkoly, viz sekce níže. Ty mohou být rozděleny na sekce, např,
odborné znalosti, praktické dovednosti, výkony, observace...

*Jak má být u modulů řešena návaznost? Jsou prerekvizity pouze slovní, nebo se
zadávají i moduly, které je nutné splnit před?*

*Jak si mám představit, že každý modul může mít vlastního administrátora? Viz
nahrávka z meetingu.*

## Úkoly

Rezident během plnění modulu žádá školitele o potvrzení jednotlivých úkolů.
Nabízí se dva způsoby, jak toto provádět:

- Rezident označí, co chce potvrdit. Zobrazí se mu QR kód,
  který školitel naskenuje a tím rezidentovi vybrané úkoly potvrdí.
- Rezident označí, co chce potvrdit. Školitel dostane oznámeni,
  které odklikne a tím se rezidentovi vybrané úkoly potvrdí.

*Jak ošetřit případ, kdy rezident bude chtít podvádět a pokusí se nechat si
potvrdit i úkoly, které neprovedl?*

Některé úkoly může schválit jen školitel, kterého má rezident přiřazeného. Jiné
může schválit kdokoliv s potřebnou rolí.

*K čemu je toto dobré?*

Úkoly nemusí být plněny postupně -- neexistuje mezi nimi návaznost.

*Jaké typy potvrzení mohou úkoly mít? Splněno/nesplněno? Číslo?*

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
