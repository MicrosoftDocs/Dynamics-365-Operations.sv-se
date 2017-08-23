---
title: Kredit och inkasso i Kundreskontra
description: "Information om kundreskontrasamlingar hanteras i en central vy med hjälp av Microsoft Dynamics 365 for Finance and Operations, Enterprise edition-samlingssidan. Kredit- och inkassoansvariga kan använda denna centrala vy för att hantera inkasseringar. Inkassohandläggare kan börja inkassoprocessen från kundlistor som genereras med hjälp av fördefinierade inkassokriterier eller från sidan Kunder."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustAgingSnapshot, CustBankAccounts, CustCollections, CustCollectionsActivitiesListPage, CustCollectionsAgent, CustCollectionsCaseListPage, CustCollectionsPool, CustCollectionsPoolsListPage, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3061
ms.assetid: fd851520-8d93-434b-845b-be127d6ac3a6
ms.search.region: Global
ms.author: Shiva.Pandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1982e495f740d6061b9574aa9f40f38180e8d110
ms.openlocfilehash: 282084b9d4e63795ec475690e5b22e06c23bb704
ms.contentlocale: sv-se
ms.lasthandoff: 08/03/2017

---

# <a name="credit-and-collections-in-accounts-receivable"></a>Kredit och inkasso i Kundreskontra

[!include[banner](../includes/banner.md)]


Information om kundreskontrasamlingar hanteras i en central vy med hjälp av Finance and Operations-samlingssidan. Kredit- och inkassoansvariga kan använda denna centrala vy för att hantera inkasseringar. Inkassohandläggare kan börja inkassoprocessen från kundlistor som genereras med hjälp av fördefinierade inkassokriterier eller från sidan Kunder.

Innan du börjar ställa in eller arbeta med kassaavstämningar, ska du förstå följande begrepp:
-   Ögonblicksbilder av åldersfördelningen för kunder innehåller information om åldersfördelade saldon vid en tidpunkt
-   Inkassokundpooler hjälper dig att organisera arbetet
-   Inkassohandläggare kan ha sina egna kundpooler
-   Listsidor organiserar inkassokunder, aktiviteter och fall
-   All information om inkasso för en kund finns på sidan, och du kan vidta åtgärder från den sidan
-   Avfärda, återinsätta eller återföra ränta och avgifter kan göras i ett steg
-   Skapa avskrivningstransaktioner kan göras i ett steg
-   Bearbeta NSF-transaktioner kan göras i ett steg

De olika elementen beskriver varje koncept.

## <a name="customer-aging-snapshots"></a>Ögonblicksbild av åldersfördelningen för kunder
En ögonblicksbild av åldersfördelning består av beräknade åldersfördelningssaldon för en kund vid en viss tidpunkt. Information om ögonblicksbilden av åldersfördelning visas på listsidan Åldersfördelade saldon och på sidan Inkasso. En ögonblicksbild av åldersfördelning måste skapas innan du kan visa information om listsidan Inkasso. 

För varje kund innehåller en ögonblicksbild av åldersfördelning en ögonblicksbild av åldersfördelning med rubrik och detaljposter som motsvarar varje åldersfördelningsperiod i åldersfördelningsperioddefinitionen. 

Ögonblicksbild av åldersfördelninghuvudet innehåller totalt förfallet belopp, kreditgräns, följesedelbelopp, försäljningsorderbelopp, antalet omtvistade transaktioner och totalbelopp av de omtvistade transaktionerna för kundkontot. Alla öppna transaktioner för kunden inkluderas i beräkningen av dessa belopp. Det totala beloppet, kreditgränsen, följesedelbeloppet och försäljningsorderbeloppet visas i faktaboxen Kreditinformation på sidan Inkasso. 

För varje åldersfördelningsperiod i åldersfördelningsperioddefinitionen skapas en ögonblicksbild av åldersfördelningdetaljpost. Varje ögonblicksbild av åldersfördelningdetaljpost innehåller åldersfördelningsperiod-ID och det totala beloppet för transaktioner med data som infaller under åldersfördelningsperioden. Transaktioner tilldelas en åldersfördelningsperiod, till exempel 30 dagar förfallen. Datumet är relativt till åldersfördelningen som det datum som anges, när du skapar ögonblicksbilden av åldersfördelning. Information om ögonblicksbilden av åldersfördelning visas ifaktaboxen Åldersfördelade saldon och på sidan Inkasso.

## <a name="collections-customer-pools"></a> Kundinkassopooler 
Kundpooler är frågor som definierar en grupp med kundposter som kan visas och hanteras för samlingar eller åldersfördelningsprocesser. Använd kundpooler för att filtrera information på listsidorna Åldersfördelade saldon, Inkassoaktiviteter och Inkassoärenden. Du kan även använda kundpooler för att filtrera de kundkonton som är inkluderade när ögonblicksbilder av åldersfördelning skapas.

## <a name="collections-agents"></a>Inkassohandläggare
Som standard kan Microsoft Dynamics 365 for Finance and Operations-användare visa all kundinformation på listsidorna för inkasso. Du kan använda inkassohandläggareposter för att bestämma kundpoolerna som är tillgängliga för att filtrera information om listsidorna för Inkasso och sidan Inkasso. 

En inkassohandläggare är en person som arbetar med kunder för att säkerställa att betalningarna samlas in i tid. I Finance and Operations är inkassohandläggare arbetare som tilldelas till användare på sidan Användarinställningar.

## <a name="collections-list-pages"></a> Listsidor för Inkasso 
Följande listsidor hjälper dig att ordna information om inkasso.
-   Åldersfördelade saldon - kolumnerna på listsidan visar kundsaldon och föråldrade belopp per åldersfördelningsperiod. Den här informationen lagras i en ögonblicksbild över åldersfördelningen. Åldersfördelningsperioderna bestäms av åldersfördelningsperioddefinitionen som används. Åldersfördelningsperioddefinitionen hämtas från kundpoolen, om en sådan har angetts för poolfrågan. Om kundpoolen inte har någon åldersfördelningsperioddefinition används standardåldersfördelningsperioddefinitionen som angetts på sidan Parametrar för kundreskontra. Om ingen standardåldersfördelningsperioddefinition har angetts, används den första åldersfördelningsperioddefinitionen på sidan Definitioner för åldersfördelningsperiod.
-   Inkassoaktiviteter – kolumnerna på listsidan visar aktiviteter som identifieras som inkassoaktiviteter. Dessa aktiviteter skapas, genom att använda sidan Inkasso. Använd aktiviteter för att spåra arbetet som du gör med inkasseringar.
-   Inkassoärenden - kolumnerna på listsidan visar information om ärenden som har ärendekategori med ärendetypen Inkasso.

> [!NOTE]
> En ögonblicksbild av åldersfördelning måste skapas innan du kan visa information om listsidan Inkasso. Informationen visas bara för kunder när en ögonblicksbild av åldersfördelning har skapats. Posterna som visas på listsidan kan dessutom filtreras, enligt följande:
<li>Som standard har en Finance and Operations-användare åtkomst till alla kunder som har en ögonblicksbild av åldersfördelning.</li>
<li>Om kundpooler finns, måste en användare anges som en inkassohandläggare för att använda poolerna till att filtrera information om listsidorna för inkasso. Informationen begränsas till de kunder som ingår i den valda kundpoolen.</li>
<li>Om en användare har ställts in som en inkassohandläggare, är endast poolerna som har valts för den inkassohandläggaren tillgängliga på listsidan. Om Tillåt handläggare att visa alla kundpooler har valts på sidan Inkassohandläggare för inkassohandläggaren, är alla pooler tillgängliga för den handläggaren.</li>


## <a name="collections-page"></a> Sidan Inkasso
Använd sidan Inkasso för att visa, hantera och vidta åtgärder om inkassoinformation, aktiviteter och ärenden för kunder. 

Det övre fönstret visar ärenden för den valda kunden. Det mellersta fönstret visar transaktioner för kunden. Det nedre fönstret visar alla aktiviteter för kunden. Du kan skapa inkassoärenden för att spåra inkassoinformation för en eller flera transaktioner och aktiviteter. Informationen i det övre fönstret och lägre fönstret kan filtreras efter fallet. 

Faktaboxar innehåller åldriga saldon och information om kreditgräns för valda kunden. Den här informationen lagras i en ögonblicksbild över åldersfördelningen. Om det behövs kan du uppdatera ögonblicksbilden av åldersfördelning med aktuell information. 

Åtgärdsfönstret innehåller knappar som visar relaterad information för vald kund, ärende, transaktion eller aktivitet. Du kan också utföra vanliga åtgärder till exempel ändra inkassostatusen för en transaktion, skicka e-postmeddelande genom integration med din e-postleverantör, återbetalning till kunder, bearbetning och NSF-betalningar och avskrivning av saldon som inte kan inkasseras.

## <a name="waive-reinstate-or-reverse-interest-and-fees"></a> Avfärda, återinsätta eller återföra ränta eller avgifter
Du kan efterskänka, återinföra eller återföra hela räntefakturor eller avgifter och transaktionränta som är en del av räntefakturor. Du kan göra detta från fliken Inkasso i åtgärdsfönstret på sidan Alla kunder genom att klicka på Räntefaktura, Transaktionsränta eller Avgift. 

Dessa justeringar påverkar endast räntefakturor, och ränta och avgifter som de innehåller. Använd stegen i ”Skapa avskrivningstransaktioner i ett steg" för att skriva av alla avgifter som en kund är skyldig.

Mer information finns i [Skapa en räntekod med ett intervall](tasks/create-interest-code-range.md) och [Bearbeta ränta](tasks/process-interest.md). 

## <a name="create-writeoff-transactions"></a>Skapa avskrivningstransaktioner
Du kan skriva av dåliga skulder genom att klicka på Skriv av i formuläret Inkasso och på listsidorna Åldriga saldon, Kunder och Öppna kundfakturor. 

När du skriver av transaktioner för en kund, markeras alla transaktioner för kunden automatiskt för kvittning. Ett belopp, som skrivs av, beror på nettobeloppet för markerade transaktioner. Avskrivningstransaktionen skapas i en allmän journal och får innehålla maximalt tre typer av journalrader.

-   Den första typen av journalrad innehåller kundavskrivningposten. Om markerade transaktioner innehåller flera kombinationer av valutakod, dimension och bokföringsprofil, skapas en separat journalrad för varje kombination.
-   Den andra typen av journalrad innehåller redovisningsavskrivningsposten. Om markerade transaktioner innehåller flera kombinationer av valutakod, dimension och bokföringsprofil, skapas en separat journalrad för varje kombination.
-   Den tredje typen av journalrad innehåller information för redovisningsavskrivning för moms. Denna journalrad skapas, om konfigurationsnyckeln för separata momsvippen valts på sidan Parametrar för kundreskontra. Om markerade transaktioner innehåller flera kombinationer av konto för utgående moms, dimension och momskod, skapas en separat journalrad för varje kombination.

Avskrivningstransaktionen skapas i transaktionsvalutan.

Mer information finns i [Skapa en avskrivningsjournal för en kund](tasks/create-write-off-journal-customer.md).

<a name="process-not-sufficient-funds-nsf-payments"></a>Bearbeta otillräckliga medel (NSF-betalning) 
--------------------------------------------

Du kan bearbeta NSF-betalningar, genom att klicka på NSF-betalning på sidan Inkasso. När du klickar på den här knappen, annulleras betalningen. Om en NSF-avgift tillämpas för kunden, skapas en avgiftstransaktion i en betalningsjournal. Avgiftsbeloppet baseras på inställningarna för de automatiska avgifterna. De automatiska avgifterna som gäller för NSF-betalningar anges av avgiftsgruppen som valts på sidan Bankkonton för det berörda bankkontot.






