---
title: Hantera en rekryteringsprocess
description: "Denna artikel beskriver ett begrepp som rekryterare kan använda för att följa stegen i en rekryteringsprocess, inklusive försök att annonsera lediga jobberbjudanden och att rekrytera sökande, spåra sökande och ansökningsinformation, intervjua sökande och välja en eller flera kandidater till de lediga befattningarna i din organisation."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6f4429202efd0506378d681188035c5cc69f56a1
ms.openlocfilehash: 551e15ed31953d6e5fc99a1177c1310194ea95d0
ms.lasthandoff: 03/31/2017


---

# <a name="manage-a-recruiting-process"></a>Hantera en rekryteringsprocess

Det här avsnittet beskriver ett begrepp rekryterare kan du följa stegen i en process rekrytering, bland annat ansträngningarna att annonsera lediga befattningar och rekrytering av sökanden, spårningsinformation sökande och ansökan, intervjuer av sökande och markera en eller flera kandidater att fylla lediga befattningar i organisationen.

<a name="overview"></a>Översikt
--------

Rekryteringsprojekt kan hjälpa dig att ordna stegen som du ska utföra när du fyller öppna befattningar i en juridisk person. En sökande är en person som gäller för anställning för ditt företag.  Ett program är en sökande framfört önskemål i som tillämpas av ett företag och kan knytas till ett rekryteringsprojekt till express är intresserad av en viss öppnas.  En enda sökande kan ha flera program inom samma juridiska person eller mellan flera företag inom din organisation.

<a name="recruitment-projects"></a>Rekryteringsprojekt
--------------------

Rekryteringsprojekt kan rekryterare arbetar mot fyller en eller flera lediga befattningar.  Rekryteringsprojektet identifierar avdelning och projekt för vilka en eller flera positioner är öppna. Rekryteringsprojekt spårar även följande information om öppna befattningar:
-   Det specifika antalet öppna befattningar
-   Den anställande chefen och en alternativ kontakt för befattningen
-   Datumet då rekvisitionen godkändes.
-   Deadline för ansökning
-   Uppskattat startdatum

Rekryteringsprojektet innehåller den **Jobbannons** som används på **Självbetjäning för medarbetare** för att annonsera den öppna befattningen. Om du vill visa jobberbjudandet för medarbetare måste rekryteringsprojektet ha en **Jopbbannons**, fältet ** Visa i självbetjäningen för medarbetare** måste anges till Ja, **Deadline för ansökning**  måste ställas in på ett framtida datum, och rekryteringsprojektet måste ha **Projektstatus** Startad. Nedan visas möjliga rekrytering projektets status och deras beskrivningar.

| **Status**    | **Indicates that…**                                                                  |
|-----------|------------------------------------------------------------------------------------------|
| Tidsplanerat | Rekrytering insatser upprättas.  Rekrytering startat inte har för det här projektet. |
| Startat   | Ansökningar accepteras nu för jobberbjudanden i det här projektet.                    |
| Färdigt  | Alla jobberbjudanden för det här projektet har fyllts.                                          |
| Avbrutna  | Rekryteringen har annullerats för det här projektet.                                           |

Rekryterare kan också registrera de **Medier** som används att annonsera jobberbjudandet via externa kanaler och även spåra **Utvecklingar** mot projektet eller ansökningarna.

<a name="applicants"></a>Sökanden
----------

En sökande är en person som ansöker om ett jobb i företaget.  Sökande delas alla juridiska personer i organisationen som ger dig ett stort antal användare att söka i. Du kan underhålla kompetenser, referenser, logibegäran och personuppgifter för sökande. När du skapar en sökandepost, skapas en personpost för den sökanden i den globala adressboken. På sidan **Sökande** kan du uppdatera följande information om globala adressboken för kontakter som är sökande:
-   Adressinformation
-   Kontaktinformation
-   Information om identifieringen
-   Namnuppgifter
-   Personuppgifter

## <a name="applications"></a>Ansökningar
Du kan registrera information från mottagna jobbansökningar på sidan **Ansökan**. Ansökan skall den sökande framfört önskemål i ett projekt som är öppna i din organisation.  Om du vill skapa ett program måste sökanden redan finnas som en person i ditt system.
Jobbansökningar som skickas in av sökande på webben är antingen begärda ansökningar, som registreras som svar på en jobbannons, eller spontana ansökningar. Begärda ansökningar relateras automatiskt till rekryteringsprojektet där jobbannonsen skapades. Spontana ansökningar är kopplade till rekryteringsprojektet som anges i området **Rekrytering** på sidan **Personalparametrar**.
### <a name="application-status"></a>Ansökningsstatus

Ansökningstatusen anger var en ansökan är i rekryteringsprocessen. Följande tabeller visar möjliga ansökningsstatusar och deras beskrivningar.

| Status    | Anger att...                                                                           |
|-----------|-------------------------------------------------------------------------------------------|
| Mottagen  | Ansökningen togs emot.                                                             |
| Bekräftat | Ett meddelande har skickats till den sökande med ett bekräftelsekvitto på hans eller hennes ansökan.            |
| Intervju | En kallelse till intervju har skickats till den sökande.                                     |
| Avvisad | Ett brev om att tjänsten gått till en annan sökande kan skickas till den sökande.                                          |
| Avbrutna  | En uttagsbekräftelse kan skickas till den sökande. Denna status tilldelas manuellt. |
| Anställd  | Ett anställningserbjudande kan skickas till den sökande.                                         |

### <a name="correspondence-actions"></a>Korrespondensåtgärder

En **Ansöknings** korrespondensåtgärd bestämmer det dokument eller den e-postmall som du använder för att kommunicera med den sökande, som skickade in ansökan. Du kan associera **Ansökningsbokmärken** med motsvarande åtgärder så att du kan använda värden från programmet sökande intervjun och rekrytering projekt sidor i kommunikation med de sökande.  **E-postmallar för ansökningar** kan skapas för motsvarande åtgärder du vill skicka e-post till sökande som har ett program med en viss status och korrespondens åtgärd-kombination. Du kan exempelvis skicka ett e-postmeddelande med bekräftelse för alla program med en **Status** inlevererad och en **korrespondens åtgärden** inlevererad.  När du har skickat e-postmeddelandet har möjlighet att automatiskt uppdatera status för programmen.

## <a name="application-routing"></a>Ansökningsflöde

Om en ansökning måste granskas av flera medarbetare kan du använda sidan **Ansökningsflöde** för att skapa en cirkulationslista för medarbetarna i syfte att hantera processen. 

## <a name="interviews"></a>Intervjuer

**Intervjuer av sökande** kan schemaläggas från den **program** sida.  Använd den **skicka mötesinformation** du vill skicka en kalenderfil med intervjun schemainformation till sökande och intervjuaren.

## <a name="skill-mapping"></a>Kompetensmappning

**Kompetensmappning** och **Kompetensmappningsprofiler** kan användas för att identifiera de jobbsökande som kan passa ett jobberbjudande.

## <a name="hiring-applicants"></a>Anställa sökande

Använd sidna **Ansökningar** när du anställer en sökande. När du anställer en sökande, kommer ansökningsposten har statusvärdet **Anställd** och sökandens globala adressbokspost är kopplad till den nya medarbetarposten. Ändringar av informationen om den globala adressboken för den nya medarbetarposten visas även i ansökningsposten. Detta kan hjälpa till att minska registreringen av information om ny arbetare någonsin gäller för en annan aktivitet inom företaget.  Om du vill anställa en befintlig arbetare till en ny plats klickar du på **flyttar** i den **Ansökningsstatus** listrutan initiera överföringen.




