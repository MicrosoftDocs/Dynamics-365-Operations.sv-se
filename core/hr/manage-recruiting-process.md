---
title: Hantera en rekryteringsprocess
description: "Denna artikel beskriver ett begrepp som rekryterare kan använda för att följa stegen i en rekryteringsprocess, inklusive försök att annonsera lediga jobberbjudanden och att rekrytera sökande, spåra sökande och ansökningsinformation, intervjua sökande och välja en eller flera kandidater till de lediga befattningarna i din organisation."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 6276655f6e7d09f5bc8862ad456b834d8919e574
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Hantera en rekryteringsprocess
<a id="manage-a-recruiting-process" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Denna artikel beskriver ett begrepp som rekryterare kan använda för att följa stegen i en rekryteringsprocess, inklusive försök att annonsera lediga jobberbjudanden och att rekrytera sökande, spåra sökande och ansökningsinformation, intervjua sökande och välja en eller flera kandidater till lediga befattningar i din organisation.

Översikt
<a id="overview" class="xliff"></a>
--------

Rekryteringsprojekt kan hjälpa dig att ordna stegen som du ska utföra när du fyller öppna befattningar i en juridisk person. En sökande är en person som söker anställning inom ditt företag.  En ansökan är en sökandes uttryckta intresse att anställas av ett företag och kan vara knuten till ett rekryteringsprojekt för att visa intresse för en viss befattning.  En enda sökande göra ha flera ansökningar inom samma juridiska person eller mellan flera företag inom din organisation.

Rekryteringsprojekt
<a id="recruitment-projects" class="xliff"></a>
--------------------

Rekryteringsprojekt låter rekryterarna spåra förloppet när de försöker bemanna en eller flera lediga befattningar.  Rekryteringsprojektet identifierar avdelning och projekt för vilka en eller flera befattningar kan tillsättas. Rekryteringsprojekt spårar även följande information om öppna befattningar:
-   Det specifika antalet öppna befattningar
-   Den anställande chefen och en alternativ kontakt för befattningen
-   Datumet då rekvisitionen godkändes.
-   Deadline för ansökning
-   Uppskattat startdatum

Rekryteringsprojektet innehåller den **Jobbannons** som används på **Självbetjäning för medarbetare** för att annonsera den öppna befattningen. Om du vill visa jobberbjudandet för medarbetare måste rekryteringsprojektet ha en **Jopbbannons**, fältet **Visa i självbetjäningen för medarbetare** måste anges till Ja, **Deadline för ansökning**  måste ställas in på ett framtida datum, och rekryteringsprojektet måste ha **Projektstatus** Startad. Följande tabell visar möjlig status för flera rekryteringsprojekt och deras beskrivningar.

| **Status**    | **Anger att...**                                                                  |
|-----------|------------------------------------------------------------------------------------------|
| Tidsplanerat | Rekryteringsinsatser förbereds.  Rekryteringen har ännu inte påbörjats för detta projekt. |
| Startat   | Ansökningar accepteras nu för jobberbjudanden i det här projektet.                    |
| Färdigt  | Alla jobberbjudanden för det här projektet har fyllts.                                          |
| Avbrutna  | Rekryteringen har annullerats för det här projektet.                                           |

Rekryterare kan också registrera de **Medier** som används att annonsera jobberbjudandet via externa kanaler och även spåra **Utvecklingar** mot projektet eller ansökningarna.

Sökanden
<a id="applicants" class="xliff"></a>
----------

En sökande är en person som söker ett jobb inom ditt företag.  Sökande delas mellan alla juridiska personer i din organisation vilket ger dig ett stort antal användare att söka bland. Du kan underhålla kompetenser, referenser, logibegäran och personuppgifter för sökande. När du skapar en sökandepost, skapas en personpost för den sökanden i den globala adressboken. På sidan **Sökande** kan du uppdatera följande information om globala adressboken för kontakter som är sökande:
-   Adressinformation
-   Kontaktinformation
-   Information om identifieringen
-   Namnuppgifter
-   Personuppgifter

## Ansökningar
<a id="applications" class="xliff"></a>
Du kan registrera information från mottagna jobbansökningar på sidan **Ansökan**. En Ansökan skall den sökande uttryckta intresse för en befattning inom din organisation.  För att skapa en ansökan måste den sökande redan finnas som en sökande eller person i ditt system.
Jobbansökningar som skickas in av sökande på webben är antingen begärda ansökningar, som registreras som svar på en jobbannons, eller spontana ansökningar. Begärda ansökningar relateras automatiskt till rekryteringsprojektet där jobbannonsen skapades. Spontana ansökningar är kopplade till rekryteringsprojektet som anges i området **Rekrytering** på sidan **Personalparametrar**.
### Ansökningsstatus
<a id="application-status" class="xliff"></a>

Ansökningstatusen anger var en ansökan är i rekryteringsprocessen. Följande tabeller visar möjliga ansökningsstatusar och deras beskrivningar.

| Status    | Anger att...                                                                           |
|-----------|-------------------------------------------------------------------------------------------|
| Mottagen  | Ansökningen togs emot.                                                             |
| Bekräftat | Ett meddelande har skickats till den sökande med ett bekräftelsekvitto på hans eller hennes ansökan.            |
| Intervju | En kallelse till intervju har skickats till den sökande.                                     |
| Avvisad | Ett brev om att tjänsten gått till en annan sökande kan skickas till den sökande.                                          |
| Avbrutna  | En uttagsbekräftelse kan skickas till den sökande. Denna status tilldelas manuellt. |
| Anställd  | Ett anställningserbjudande kan skickas till den sökande.                                         |

### Korrespondensåtgärder
<a id="correspondence-actions" class="xliff"></a>

En **Ansöknings** korrespondensåtgärd bestämmer det dokument eller den e-postmall som du använder för att kommunicera med den sökande, som skickade in ansökan. Du kan associera **Ansökningsbokmärken** med korrespondensåtgärder, vilket låter dig använda värden från projektsidorna, Ansökan, Sökande, intervju och Rekryteringsprojektsidor i din kommunikation med de sökande.  **E-postmallar för ansökningar** kan skapas för korrespondensåtgärder du vill skicka e-post till sökande som har en ansökan med en viss status och korrespondensåtgärdskombination. Du kan exempelvis skicka ett bekräftelsemail till alla sökande med **Status** inlevererad och **Korrespondensåtgärd** inlevererad.  När du har skickat e-postmeddelandet kan du automatiskt uppdatera statusen för ansökningarna.

## Ansökningsflöde
<a id="application-routing" class="xliff"></a>

Om en ansökning måste granskas av flera medarbetare kan du använda sidan **Ansökningsflöde** för att skapa en cirkulationslista för medarbetarna i syfte att hantera processen. 

## Intervjuer
<a id="interviews" class="xliff"></a>

**Intervjuer av sökande** kan schemaläggas från sidan **Ansökningar**.  Använd knappen **Skicka mötesinformation** du vill skicka en kalenderfil med intervjuschemainformation till sökande och intervjuare.

## Kompetensmappning
<a id="skill-mapping" class="xliff"></a>

**Kompetensmappning** och **Kompetensmappningsprofiler** kan användas för att identifiera de jobbsökande som kan passa ett jobberbjudande.

## Anställa sökande
<a id="hiring-applicants" class="xliff"></a>

Använd sidna **Ansökningar** när du anställer en sökande. När du anställer en sökande, kommer ansökningsposten har statusvärdet **Anställd** och sökandens globala adressbokspost är kopplad till den nya medarbetarposten. Ändringar av informationen om den globala adressboken för den nya medarbetarposten visas även i ansökningsposten. Detta kan hjälpa till att minska registreringen av information om den nya arbetaren någonsin skulle ansöka om ett annat jobb inom ditt företag.  Om du vill anställa en befintlig arbetare på en ny befattning klickar du på **Byt befattning** i listrutan **Ansökningsstatus** för att initiera flytten.





