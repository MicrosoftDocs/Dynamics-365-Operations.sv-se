---
title: Kostnadsredovisningsterminologi
description: Detta ämne definierar de grundläggande villkoren som används i kostnadsredovisning.
author: ShylaThompson
ms.date: 08/31/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostAccountingLedger
audience: Application User
ms.reviewer: roschlom
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f61ae7a6657eaad3510833c17f342b7266be247aec2a9bfe80b97172f662ae0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774387"
---
# <a name="cost-accounting-terminology"></a>Kostnadsredovisningsterminologi

[!include [banner](../includes/banner.md)]

Detta ämne definierar de grundläggande villkoren som används i kostnadsredovisning.

**Allokeringsunderlag**

Allokeringsunderlaget används för att mäta och kvantifiera aktiviteter som t.ex. använda maskintimmar, förbrukade kilowattimmar eller kvadratmeteryta som utnyttjas. Det används som bas för att allokera kostnader till en eller flera kostnadsbärare.

**Kostnadsredovisning**

Kostnadsredovisning låter dig samla in data från olika källor, till exempel huvudbok, delredovisningar, budgetar och statistisk information. Du kan sedan analysera, summera och utvärdera kostnadsdata, så att ledningen kan ta bästa möjliga beslut när det gäller prisuppdateringar, budgetar, kostnadskontroll, osv. Källadatan som används för kostnadsanalys hanteras oberoende i kostnadsredovisning. Därför påverkas inte källadatan av uppdateringar i kostnadsredovisning. När du samlar in kostnadsdata från olika källor och särskilt när du importerar huvudkontona från huvudboken som kostnadselement finns det dataredundans, eftersom samma data finns i både huvudbok och i kostnadsredovisning. Den här redundansen krävs, eftersom du använder ekonomisk hantering för extern rapportering och kostnadsredovisning för intern rapportering.

**Huvudbok för kostnadsredovisning**

Det styr processer och policyer för kostnadsberäkning efter kalender, valuta och kostnadselement. 

**Kostnadspost**

Kostnadsposter är resultatet av en överföring via datakopplingar från huvudboksposter, kostnadsallokeringar och bokförda kostnadsposter i kostnadsjournaler.

**Kostnadsobjekt**

Alla typer av objekt som väljs för kostnadskontroll. Bokföringar sker antingen direkt till kostnader eller intäkter, eller också fördelas dessa till kostnadsbärare. Bland typiska kostnadsbärare finns exempelvis:

-  Produkter
-  Projekt
-  Avdelningar
-  Kostnadsställen

Företagsledningen använder kostnadsobjekt till att kvantifiera kostnader och även till att köra lönsamhetsanalyser.

**Kostnadselement**

Används som en funktion för att spåra och sortera kostnader. Det finns två typer av kostnadselement: primära och sekundära.

Primära kostnadselement representerar kostnadsflödet från ekonomisk redovisning till kostnadsredovisning. Strukturen motsvarar vanligtvis resultaträkningsstrukturen i redovisningen, där ett kostnadselement kan motsvara ett huvudkonto. Alla rubrikkontona måste representeras som kostnadselement beroende på företagets behov. 

De sekundära kostnadselementen representerar det interna kostnadsflödet eftersom dessa kostnader endast används inom kostnadsredovisningen. De används i reglerna för kostnadssummering för att aggregera kostnader i meningsfulla grupper som används i omkostnadsberäkningar. 

**Kostnadsklassificering**

Kostnadsklassificering grupperar kostnader grupperar enligt deras egenskaper. Till exempel kan kostnader grupperas efter element, spårbarhet och beteende.

-   **Efter element** Material, arbete och utgifter.
-   **Efter spårbarhet** – Direkta kostnader och indirekta kostnader. Direkta kostnader tilldelas direkt till kostnadsobjekt. Indirekta kostnader är inte direkt spårbara till kostnadsobjekt. Indirekta kostnader allokeras till kostnadsobjekt.
-   **Efter beteende** Fast, variabel och halvvariabel.

**Kostnadsbeteende**

Kostnadsbeteende klassificerar kostnader enligt deras beteende i relation till ändringar i viktiga affärsaktiviteter. Om du vill styra kostnader på ett effektivt sätt måste cheferna förstå kostnadsbeteendet. Det finns tre typer av kostnadsbeteendemönster: fast, variabel och halvvariabel.

- **Fast kostnad** – En fast kostnad är en kostnad, som inte varierar på kort sikt, oavsett ändringar i aktivitetsnivå. Exempelvis kan en fast kostnad vara en grundläggande rörelseutgift i ett företag som till exempel hyra, som inte kommer att påverkas även om aktivitetsnivån ökar eller minskar.

- **Variabel kostnad** – En variabel kostnad ändras enligt ändringar i aktivitetsnivå. Till exempel är specifika direktmaterialkostnader kopplade till varje produkt som säljs. Ju fler produkter som säljs, desto fler direkta materialkostnader finns det.

- **Halvvariabla kostnader** – Halvvariabla kostnader är delvis fasta och delvis variabla kostnader. Till exempel en avgift för Internetåtkomst inkluderar en månatlig standardåtkomstavgift och en användningsavgift för bredband. Den månatliga standardåtkomstavgiften är en fast kostnad, medan användningavgiften för bredband är en variabel kostnad.

**Kostnadsstyrenhet**

Kostnadskontrollenheten representerar kostnadsstrukturen. Strukturen styr hur kostnadsflödet går i en hierarkisk ordning mellan dimensionerna för kostnadsbärare och dessas respektive kostnadsbärare. 

**Kostnadsfördelning**

Den används för att distribuera kostnader från en kostnadsbärare till en eller flera andra kostnadsbärare genom att tillämpa ett relevant allokeringsunderlag. Kostnadsfördelning och kostnadsallokering skiljer sig åt genom att kostnadsfördelningen alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden, och utan ömsesidig bearbetning.

**Kostnadsfördelning**

Används för att allkokera saldot på en kostnadsbärare till andra kostnadsbärare genom att använda ett allokeringsunderlag. Finance stöder ömsesidig allokeringsmetod. I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt. Systemet avgör automatiskt den korrekta ordningen att utföra allokeringarna i, och att upprepa det. Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag. Allokeringar över flera kostnadsbärardimensioner och deras respektive medlemmar stöds. Allokeringsordern styrs av kostnadskontrollenheten.

**Kostnadsfördelningspolicy**

En kostnadsallokeringspolicy definierar de belopp och kvantiteter som måste allokeras. Allokeringsregler inkluderar regler för allokeringskälla som bestämmer kostnaderna som allokeras, och regler för allokeringsmål som bestämmer var kostnaderna ska allokeras. Exempelvis är alla anläggningsservicekostnader en allokeringskälla som kan allokeras till olika avdelningar i organisationen (det vill säga till allokeringmål).

**Samlade kostnader**

Syfte med regler för kostnadssummering är att aggregera kostnader i meningsfulla grupper. Aggregeringsnivån bestäms av användaren och inbegriper sammansättningen av ett sekundärt kostnadselement. Om kostnadssammansättning inte används, kommer samtliga kostnadselement att allokeras från en kostnadsbärare till en annan

**Policy för kostnadstariff**

Kostnadstariffen används för att beräkna pris per kostnadsobjekt. För att förstå prisets element definierar du policyer för kostnadstariff. Det finns två typer av den kostnadstariff: historisk kostnadstariff och planerad kostnadstariff. En historisk kostnadstariff är en beräknad kostnad som används som en multiplikator för allokeringbasen av ett kostnadsobjekt. Tariffen beräknas utifrån kostnadsallokeringarna i föregående period. En planerad tariff är en användardefinierad tariff.

**Dimensionshierarki**

Det finns två dimensionshierarkier: kategoriseringshierarki och klassificeringshierarki. Hierarkitypen för dimensionskategorisering används för rapporteringsändamål. Den stöder endast dimensioner för kostnadselement. Hierarkitypen för dimensionsklassificering används för att definiera policyer samt för rapporteringsändamål. Den stöder alla dimensioner, till exempel kostnadsobjekt, kostnadselement och statistiska dimensioner. 

**Datakoppling**

Kostnadsredovisning stöder integrering av data från källsystem via en uppsättning datakopplingar. Följande datakopplingar finns:

-  Importerade transaktioner (förkonfigurerade)
-  Dynamics 365 Finance (förkonfigurerad)
-  Dynamics AX (konfiguration krävs)

**Obs:** Transaktioner importerade via datakopplingen baseras på datatabeller.

**Dataprovider**

De flesta källsystem kan innehålla data som matchar en eller flera datakällor i kostnadsredovisningen. Om du vill justera data från källsystemen med datakällan i kostnadsredovisningen, måste en dataleverantör konfigureras. I följande tabell visas vilka dataleverantörer som finns tillgängliga per dataanslutning och datakälla.

|  **Datakällor** |  **Dataanslutning för importerade transaktioner** | **Dynamics 365 Finance datakoppling**  | **Datakoppling för Dynamics AX**  |
|---|---|---|---|
| Dimensionsmedlemmar för kostnadselement  |  Ja | Ja  | Ja  |
|  Dimensionsmedlemmar för kostnadsobjekt |  Ja | Ja  | Ja  |
|  Statistikdimensionsmedlemmar | Ja  | Nr  | Nr  |
|  Huvudbok | Ja  | Ja  | Ja  |
|  Budgetposter  | Ja  | Ja  | Ja  |
|  Statistiska mätningar | Ja  | Ja  | Ja  |

**Formel**

Formelallokeringsunderlag låter dig definiera avancerade formler för att uppnå rätt allokeringsbas. Du kan manuellt skapa formelallokeringsunderlag. Du kan använda följande operatorer för att ange formeln.

|  **Symboler** | **Text**  |
|---|---|
|  ( ) | Parenteser  |
|  < |  Mindre än |
|  > |  Större än |
|  + |  Tillägg |
|  – |  Subtraktion |
| *  | Multiplikation  |

Traditionella IF-utlåtanden stöds inte. Du kan emellertid skapa rapporter och kontrollera om de är sanna.

|  **Utdragsvalidering** | **Resultat**  |
|---|---|
|  a > b| Sant  |
|  a > b |  Falskt |

**Indirekt kostnad**

Indirekta kostnader refererar till de pågående utgifterna för att driva en verksamhet. De är kostnader som inte kan länkas direkt till specifika företagsaktiviteter. Här följer några exempel på indirekta kostnader:

-   Redovisningsavgifter
-   Avskrivningar
-   Försäkring
-   Intresse
-   Rättsliga arvoden
-   Skatter
-   Kostnader för allmännyttiga tjänster

**Indirekt kostnad**

Kostnader anges per kostnadsbärare och kostnadselement. Det finns två typer av kvoter: räkenskapsperiod och användardefinierade. Räkenskapsperiodens kostnader beräknas av den övergripande beräkningen. En användarspecifik kvot är användardefinierad och kan användas för att fördela kostnaden mellan olika kostnadsbärare till en förbestämd kvot i den övergripande beräkningen.

**Publicerad**

Om du anger detta fält till Ja kan en användare som tilldelas en av följande roller visa rapporten i arbetsytan Kostnadskontroll:

-  Kostnadsredovisningschef
-  Kostnadsredovisare
-  Ansvarig kostnadsredovisare
-  Kostnadsobjektcontroller

Om du anger detta fält som Nej kan endast användare som tilldelats en av följande roller visa rapporten i arbetsytan Kostnadskontroll:

-  Kostnadsredovisningschef
-  Kostnadsredovisare
-  Ansvarig kostnadsredovisare

**Statistikdimension**

En statistisk dimension och dess medlemmar används för att registrera och kontrollera icke-monetära poster i kostnadsredovisning. Statistiska dimensionsmedlemmar kan användas för två syften:

-  Som en allokeringsbas i policyerna som t.ex. kostnadsdistribution eller kostnadsallokering.
-  För rapportering av icke-monetär förbrukning.

En statistisk dimension är ett uttrycket för ett antal eller en summa av en aktivitet som kan användas som bas för allokeringar eller kvotberäkningar. Den skapas antingen manuellt eller importeras från källsystem. Exempel på statistiska dimensioner inkluderar antalet medarbetare, antalet licensierade program på varje enhet, kraftförbrukning för varje dator eller kvadratmeter för ett kostnadsställe.

**Sats**

Utdrag för vyer för chefer som är ansvariga för att kontrollera kostnader. Utdrag definieras av en kostnadscontroller och ger en snabb överblick över faktiska och budgeterade kostnader, samt även över avvikelser. En chef kan ytterligare fördjupa sig i detaljerna vid behov. För att säkerställa att chefer bara får se de data som de ansvarar för, faller den data som visas i utdragen under åtkomstregler.

**Version**

Versioner används för att simulera, visa och jämföra olika resultat. Som standard visas alla faktiska kostnader i en basversion som kallas för *faktisk* För budgetar och beräkningar kan du efter behov arbeta med valfritt antal versioner. Du kan till exempel importera budgetdata till en ursprunglig version och sedan ändra budgeten i en reviderad version. För beräkningar kan du skapa flera versioner. I dessa olika versioner kan du sedan skapa beräkningar genom att använda olika beräkningsregler som ska tillämpas för kostnadsallokering.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]