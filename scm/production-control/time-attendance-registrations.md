---
title: "Tid- och närvaroregistrering"
description: "Tidsregistreringsarbetare kan ange olika typer av tidregistreringar, till exempel stämpla in, stämpla ut, registrera indirekta aktiviteter och frånvaroregistrering. Den här artikeln beskriver registreringar, deras beräkning, godkännande och användning av arbetsflöde för att lägga till strukturen och godkännande automatiskt till processen för godkännande av tidrapporter."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorker, JmgCalcApprovePickDialog, JmgGroupApprove, JmgGroupCalc, JmgGroupSigningTable, JmgRegistration, JmgTimeCalcParmeters, WorkflowTableListPageRnr
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53351
ms.assetid: 885b0cdf-53d7-4cb4-92fe-da1b9e32b39f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 12193e4c266abc7bf0349ba9a78dbbbd9d00938d
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="time-and-attendance-registration"></a>Tid- och närvaroregistrering

[!include[banner](../includes/banner.md)]


Tidsregistreringsarbetare kan ange olika typer av tidregistreringar, till exempel stämpla in, stämpla ut, registrera indirekta aktiviteter och frånvaroregistrering. Den här artikeln beskriver registreringar, deras beräkning, godkännande och användning av arbetsflöde för att lägga till strukturen och godkännande automatiskt till processen för godkännande av tidrapporter. 

<a name="registrations"></a>Registreringar
-------------

I företag som använder Tid- och närvaroregistrering, måste arbetare registrera tiden som de spenderar på jobbet, samt deras närvaro. Vissa företag kanske bara kräver att medarbetarna registrerar sig när de stämplar in och ut. I andra företag, kanske också anställda måste registrera tidsförbrukning på den verkliga kostnaden för de aktiviteter som de utför, samt pauserna de tar. De avsedda användarna av Tid och närvaro är:
-   Arbetare som måste registrera tid och närvaro regelbundet, till exempel varje dag, varje vecka eller varannan vecka.
-   Handledare, chefer och lönehandläggare som beräknar, godkänner och överför arbetareregistreringar för vidare behandling.

| **Obs!**                                                                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Om du kör Tid och närvaro tillsammans med Tillverkningskörning, kommer alla registreringar på projekt, projektaktiviteter, indirekta aktiviteter samt frånvarokoder, övertid, flextid att registreras och användas för att beräkna lön i båda moduler. |

## <a name="time-registrations-workers"></a> Tidsregistreringsarbetare
För att kunna registrera tid och frånvaro göra måste anställda ställas in som tidsregistreringsarbetare i det företag som de är anställda i.

När inställningar är klara kan arbetarna ange andra typer av registreringar.

-   In- och utstämpling när de kommer till eller går hem från arbetet.
-   Tids- och artikelförbrukning i produktionsjobb.
-   Den tid som används på en maskin på arbetet om maskinen har definierats som en resurs.

| **Obs!**                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| En anställd kan automatiskt tilldelas tidsregistreringar som gjorts på en specifik maskin på arbetsplatsen, om arbetaren väljer att arbeta som assistent på maskinen, när han eller hon startar produktionsjobbet. |

-   Tidsregistreringar på projekt och projektaktiviteter.
-   Om du vill registrera projektavgifter och artikelförbrukning via respektive projektavgiftsjournaler och projektartikeljournaler.
-   Planerad frånvaro.
-   Frånvaro när en anställd kommer för sent till arbetet eller går tidigare än planerat.
-   Arbetsavbrott, antingen manuellt registrerade eller automatiskt beräknade av systemet.
-   Indirekta aktiviteter, som är ej produktiva aktiviteter som en anställd kan engagera sig i under en arbetsdag. Exempel på dessa aktiviteter omfattar möten eller att städa deras arbetsyta.
-   Övertid, som kan registreras antingen som ytterligare timmar, flextid eller övertid.

## <a name="adding-clockout-registrations"></a>Lägg till utstämplingsregistreringar
Om en anställd glömmer utstämpling vid slutet av arbetsdagen, kan den saknade registreringen läggas till, genom att köra ett batchjobb. Systemet jämför instämplingstid och utstämplingstid enligt den kopplade profilen för arbetaren och infogar automatiskt den saknade utstämplingen som matchar profilens sluttid. Både in- och utstämplingsregistreringar är flera viktiga för den efterföljande beräkningen och godkännandet av tidregistreringar, innan de kan överföras till lönesystemet.

## <a name="calculating-registrations"></a>Beräkna registreringar
När en registreringsarbetare tilldelas en beräkningsgrupp som vanligtvis relaterar till ett specifikt team, skift eller arbetsgrupp. Teamchefen eller handledaren validerar vanligtvis registreringar som görs av arbetarna och är därför också ansvarig för att köra dagligen beräkningen för respektive beräkningsgrupper. Som en del av beräkningsprocessen kan teamchefen eller handledaren göra:
-   Korrigera felaktiga registreringar. T.ex. ändra växlingskoder och justera återrapportering av produktionsjobb.
-   Lägga till registreringar. T.ex. skapa utstämplingsregistreringar och frånvarotransaktioner.
-   Ta bort felaktiga registreringar.

Eftersom den registrerade tiden måste matcha arbetarens tidsprofil före beräkning av registreringarna, måste du åsidosätta profilen som arbetstid för en arbetare som har ett undantag till sina vanliga arbetstidsprofil. Då arbetarprofilen är dagskift och arbetaren har gått med på att arbeta nattskift utan övertidsersättning, måste teamchefen eller handledaren åsidosätta standardarbetarprofilen för att beräkna arbetstiden på standardsystemet för pris per natt och inte som övertid. Beräkningen visar också ett fel, om en frånvaroregistrering saknas. Den måste läggas till innan beräkningen kan slutföras.

## <a name="approving-registrations"></a>Godkänna registreringar
På samma sätt som du tilldelar en beräkningsgrupp till en tidsregistreringsarbetare, måste du även tilldela en godkännandegrupp. En beräkningsgrupp utgörs därför typiskt av ett specifikt team, skift eller arbetsgrupp. Du måste godkänna tidsregistreringar som beräknades korrekt – Detta innebär att göra en beräkning utan fel - innan löneposter kan skapas som sedan kan överföras till ett lönesystem. Löneadministratören kommer vanligtvis att göra godkännandet av registreringar, och före godkännandet kan han:
-   Åsidosätta löneavtal för enskilda arbetare.
-   Lägga till manuella bonusar.
-   Ange ytterligare information om frånvaroregistreringar.

| **Obs!**                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Om övertid har beräknats för en viss medarbetare kan övertiden tilldelas specifika jobb under dagen. Detta är relevant om jobbkostnaderna baseras på medarbetarens lön. |

## <a name="approving-registrations-using-workflow"></a> Godkänn registreringar med hjälp av arbetsflödet
Du kan ställa in en godkännandeprocess för arbetsflöde som automatiskt godkänner registreringar, som överensstämmer med arbetsflödesregler som lämnar bara avvikelser som ska hanteras manuellt. Om arbetsflödesgodkännande har aktiverats, skickar teamchefen eller handledaren in beräknade registreringar för godkännande. Arbetsflödesprocessen skapar lämpliga godkännanden och uppgifter och tilldelar dem sedan rätt användare och roller som identifieras i arbetsflödet. Det finns två arbetsflödesgodkännanden för tid och närvaro.

| Arbetsflöde                                  | Syfte                                                                                                   | Registreringstyp                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Totalt antal dagars tid och närvaro            | Arbetsflödet valideras mot registreringar, till exempel det förväntade antalet arbetstimmar för dagen. |                                                                                                                                                                                                                                                       |
| Journalregistreringar för tid och närvaro | Arbetsflödet validerar registreringstypen för varje datum för registreringen.                           | Tid och närvaro •, Instämpling •, Utstämpling •, Frånvaro •, Rast •, Växlingskod •, Projekt •, Projektaktivitet •, Indirekta aktivitetproduktionsjobb •, Kö före •, Inställningar •, Bearbeta •, Överlappa •, Transport •, Kö efter •, Starta hjälpen •, Stoppa hjälpen |

 

## <a name="transferring-approved-registrations"></a>Överför godkända registreringar.
Efter godkännande av registreringarna kan du överföra dem till ett periodiskt lönelistejobb. En överförd registrering bokförs på en aktivitet eller ett jobb som den kopplas till, till exempel en produktionsorder eller ett projekt. Lönetransaktioner skapas för varje arbetare baserat på registreringarna.  

## <a name="reversing-transferred-registrations"></a>Återföra en överförd registrering
Uppgiften att återföra transaktioner – rulla tillbaka dem – kan göras tills tiden när lönelisteperiodens löneöverföring körs. Det innebär att lönedata har överförts till en extern fil. Vid återföring dras alla registreringar tillbaka och alla transaktioner som bokförts på produktionsorder eller projekt utjämnas och blir neutrala.

| **Obs!**                                                 |
|----------------------------------------------------------|
| Den externa filen kan importeras till ett lönesystem. |

## <a name="registrations-in-electronic-timecards"></a>Registreringar i elektroniska tidkort
Arbetare med jobbuppgifter som inte kräver direkt feedback, vilket är fallet vid produktionsjobb, men som arbetar på projektaktiviteter, kan använda elektroniska tidkort. Elektroniskt tidkort erbjuder flexibiliteten att ange registreringar när som helst och på bästa sätt för den dagliga arbetstidsplanen - dagligen, varje vecka, eller när en anställd finns i backofficesystemet igen när han har varit borta. Om du vill använda elektroniska tidkort eller dessa anställda måste du ange, Använda tidskort i arbetardetaljerna. Elektroniskt tidkort aktiverar arbetare för att registrera:

-   Datum
-   Registreringstyp
-   Jobbreferens, som t.ex. projekt, indirekt aktivitet eller produktionsorder
-   Jobbidentifiering
-   Tidsförbrukning
-   Projektavgifter
-   Projektartiklar





