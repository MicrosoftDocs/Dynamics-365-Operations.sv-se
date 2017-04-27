---
title: Kostnadsredovisningsterminologi
description: "Detta ämne definierar de grundläggande villkoren som används i kostnadsredovisning."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMCostControlWorkspaceConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 87c13e268ab8825e06095d24e03694cf0f271a63
ms.openlocfilehash: 1ae6b43bdc1812ca822a1abe2a0e823cb797a511
ms.lasthandoff: 03/31/2017


---

# <a name="cost-accounting-terminology"></a>Kostnadsredovisningsterminologi

[!include[banner](../includes/banner.md)]


Detta ämne definierar de grundläggande villkoren som används i kostnadsredovisning.

**Kostnadsredovisning**

Kostnadsredovisning låter dig samla in data från olika källor, till exempel huvudbok, delredovisningar, budgetar och statistisk information. Du kan sedan analysera, summera och utvärdera kostnadsdata, så att ledningen kan ta bästa möjliga beslut när det gäller prisuppdateringar, budgetar, kostnadskontroll, osv. Källadatan som används för kostnadsanalys hanteras oberoende i kostnadsredovisning. Därför påverkas inte källadatan av uppdateringar i kostnadsredovisning. När du samlar in kostnadsdata från olika källor och särskilt när du importerar huvudkontona från huvudboken i Microsoft Dynamics 365 for Operation som kostnadselement finns det dataredundans, eftersom samma data finns i både huvudbok och i kostnadsredovisning. Den här redundansen krävs, eftersom du använder ekonomisk hantering för extern rapportering och kostnadsredovisning för intern rapportering.

**Huvudbok för kostnadsredovisning**

Huvudboken för kostnadsredovisning är ett specialiserat ramverk som bestämmer hur processer, värden och kvantiteter anges och visas för ett visst område i kostnadsredovisning. Huvudboken för kostnadsredovisningen definierar processer och regler för att mäta kostnader för kostnadsobjekt. Det hanterar kostnadstransaktioner och hanterar dokument som registrerar ändringarna i värden och kvantiteter som ger kostnadstransaktioner.

**Kostnadspost**

Kostnadsposter är resultatet av en överföring via datakopplingar från huvudboksposter, kostnadsallokeringar och bokförda kostnadsposter i kostnadsjournaler.

**Kostnadsobjekt**

Kostnadobjekt är en typ av objekt som kostnader allokerats till. Nedan följer några typiska kostnadsobjekt:

-   Produkter
-   Projekt
-   Resurser
-   Avdelningar
-   Kostnadsställen
-   Geografiska regioner

Företagsledningen använder kostnadsobjekt till att kvantifiera kostnader och även till att köra lönsamhetsanalyser.

**Kostnadselement**

Kostnadselement används som en funktion för att följa och kategorisera var kostnader flödar till. Det finns två typer av kostnadselement: primära kostnader och sekundära kostnader. **Primärkostnader** De primära kostnadselementen representerar flödet av kostnader från ekonomisk redovisning till kostnadsredovisning. Kostnadselementstrukturen motsvarar resultaträkningsstrukturen i huvudboken, där ett kostnadselement kan motsvara en huvudkonto. Alla rubrikkontona måste representeras som kostnadselement beroende på företagets behov. Nedan följer några exempel på primära kostnadselement:

-   Kostnader för sålda varor (KSV)
-   Indirekta materialkostnader
-   Personalkostnader
-   Energikostnader

**Sekundärt kostnadselement** 

De sekundära kostnadselementen representerar det interna flödet av kostnader internt eftersom dessa kostnader skapas och används bara i kostnadsredovisning. Sekundära kostnadselement hjälper till att garantera att kostnadskällan kan spåras. Dessa kostnadelement används i kostnadsallokeringar och beräkningar av indirekta kostnader. Nedan följer några exempel på sekundära kostnadselement:

-   Tillverkningskostnader
-   Tillverknings-, material- och marknadsföringsomkostnader

**Kostnadsstyrenhet**

En kostnadskontrollenhet representerar kostnadsstrukturen. Den måste vara kopplad till kostnadsobjektdimensioner i en huvudbok för kostnadsredovisning.

**Version**

Versioner används för att simulera, visa och jämföra olika resultat. Som standard visas alla faktiska kostnader i en basversion som kallas för *faktisk* För budgetar och beräkningar kan du efter behov arbeta med valfritt antal versioner. Du kan till exempel importera budgetdata till en ursprunglig version och sedan ändra budgeten i en reviderad version. För beräkningar kan du skapa flera versioner. I dessa olika versioner kan du sedan skapa beräkningar genom att använda olika beräkningsregler som ska tillämpas för kostnadsallokering.

**Utdrag**

Utdrag för vyer för chefer som är ansvariga för att kontrollera kostnader. Utdrag definieras av en kostnadscontroller och de ger en snabb överblick över faktiska och budgeterade kostnader, och även över avvikelser och beräkningsversioner. För att garantera att chefer bara visar de data som de ansvarar för, har data som visas i boksluten åtkomstregler.

**Datakoppling**

Data kan importeras till kostnadsredovisning från externa system via datakopplingar. Du kan till exempel importera kontostrukturer, dimensioner, redovisningsposter och budgeterade poster. Du kan använda förkonfigurerade datakopplingar eller anpassade kopplingar till att importera data och skapa dataanslutningar.

**Kostnadsklassificering**

Kostnadsklassificering grupperar kostnader grupperar enligt deras egenskaper. Till exempel kan kostnader grupperas efter element, spårbarhet och beteende.

-   **Efter element** Material, arbete och utgifter.
-   **Efter spårbarhet** – Direkta kostnader och indirekta kostnader. Direkta kostnader tilldelas direkt till kostnadsobjekt. Indirekta kostnader är inte direkt spårbara till kostnadsobjekt. Indirekta kostnader allokeras till kostnadsobjekt.
-   **Efter beteende** Fast, variabel och halvvariabel.

**Kostnadsbeteende**

Kostnadsbeteende klassificerar kostnader enligt deras beteende i relation till ändringar i viktiga affärsaktiviteter. Om du vill styra kostnader på ett effektivt sätt måste cheferna förstå kostnadsbeteendet. Det finns tre typer av kostnadsbeteendemönster: fast, variabel och halvvariabel.

- **Fast kostnad** - En fast kostnad är en kostnad, som inte varierar på kort sikt, oavsett ändringar i aktivitetsnivå. Exempelvis kan en fast kostnad vara en grundläggande rörelseutgift i ett företag som till exempel hyra, som inte kommer att påverkas även om aktivitetsnivån ökar eller minskar.

- **Variabel kostnad** - En variabel kostnad ändras enligt ändringar i aktivitetsnivå. Till exempel är specifika direktmaterialkostnader kopplade till varje produkt som säljs. Ju fler produkter som säljs, desto fler direkta materialkostnader finns det.

- **Halvvariabla kostnader** - Halvvariabla kostnader är delvis fasta och delvis variabla kostnader. Till exempel en avgift för Internetåtkomst inkluderar en månatlig standardåtkomstavgift och en användningsavgift för bredband. Den månatliga standardåtkomstavgiften är en fast kostnad, medan användningavgiften för bredband är en variabel kostnad.

**Indirekt kostnad**

Indirekta kostnader refererar till de pågående utgifterna för att driva en verksamhet. De är kostnader som inte kan länkas direkt till specifika företagsaktiviteter. Här följer några exempel på indirekta kostnader:

-   Redovisningsavgifter
-   Avskrivningar
-   Försäkring
-   Intresse
-   Rättsliga arvoden
-   Moms
-   Kostnader för allmännyttiga tjänster

**Kostnadsfördelning**

Kostnadsallokering är processen att tilldela och allokera kostnader baserat på grundorsakerna för de vanliga kostnaderna. Du allokerar kostnadsbelopp och kvantiteter från ett kostnadsobjekt till ett eller flera andra kostnadsobjektet. Till exempel allokeras att alla anläggningsservicekostnader till de olika avdelningar som använder den vanliga kontorsbyggnaden.

**Kostnadsfördelningspolicy**

En kostnadsallokeringspolicy definierar de belopp och kvantiteter som måste allokeras. Allokeringsregler inkluderar regler för allokeringskälla som bestämmer kostnaderna som allokeras, och regler för allokeringsmål som bestämmer var kostnaderna ska allokeras. Exempelvis är alla anläggningsservicekostnader en allokeringskälla som kan allokeras till olika avdelningar i organisationen (det vill säga till allokeringmål).

**Allokeringsunderlag**

Allokeringbasen är grunden som kan användas till att mäta och kvantifiera aktiviteter, som t.ex. datortimmar som används, kilowattimmar som förbrukas, direkta arbetstimmar som spenderas eller kvadratmeteryta som är upptagen. Den används till att allokera kostnader till en eller flera kostnadsobjekt.

**Allokeringsprincip**

En av allokeringprinciperna är att allokera kostnad efter kostnadstariff. Du kan välja att allokera kostnader genom att använda den faktiska periodtariffen eller en historisk tariff. Allokeringen som använder den inbördes metoden hjälper till att garantera att allokeringsbasen bestäms av en serie med samtidiga ekvationer innan allokeringen görs genom att använda den faktiska periodtariffen.

**Samlade kostnader**

Syftet med samlade kostnader är att inkludera alla kostnader för ett visst kostnadsobjekt. Sammansättningsnivån är användardefinierad. Genom att använda samlade kostnader kan du sätta samman kostnadselement som måste allokeras från ett kostnadsobjekt till ett annat. När samlade kostnader inte används, allokeras varje enskilt element av ett kostnadsobjekt till ett annat.

**Policy för kostnadstariff**

Kostnadstariffen används för att beräkna pris per kostnadsobjekt. För att förstå prisets element definierar du policyer för kostnadstariff. Det finns två typer av den kostnadstariff: historisk kostnadstariff och planerad kostnadstariff. En historisk kostnadstariff är en beräknad kostnad som används som en multiplikator för allokeringbasen av ett kostnadsobjekt. Tariffen beräknas utifrån kostnadsallokeringarna i föregående period. En planerad tariff är en användardefinierad tariff.

**Dimensionshierarki**

Dimensionshierarkier används som rapporteringstrukturer när du vill definiera regler för allokering, kostnadstariff och samlade kostnader, visa utdrag eller data i Microsoft Excel, och definiera åtkomst till sammansatta data. Det finns två dimensionshierarkier: kategoriseringshierarki och klassificeringshierarki. En kategoriseringshierarki definieras baserat på kostnadselement, medan en klassificeringshierarki definieras baserat på kostnadsobjekt.

**Statistikdimension**

En statistisk dimension är uttrycket av antal och summor av ett objekt som kan användas som bas för allokeringar eller kostnadstariffberäkningar. Den skapas antingen manuellt eller importeras från källsystem. Exempel på statistiska dimensioner inkluderar antalet medarbetare, antalet licensierade program på varje enhet, kraftförbrukning för varje dator eller kvadratmeter för ett kostnadsställe.

**Statistikpost**

Statistiska poster innehåller registrerade värdet för summor och antal för en viss statistisk dimension. Det registrerade värdet för summor och antal kallas också för storleken.




