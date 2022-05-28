---
title: Hantera rekryteringsprocesser
description: Det här avsnittet beskriver ett begrepp som rekryterare kan använda när de spårar stegen i en rekryteringsprocess.
author: twheeloc
ms.date: 01/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eb7cc1db906ba0cd07caaa1d82a12182f78b19ba
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735386"
---
# <a name="manage-recruiting-processes"></a>Hantera rekryteringsprocesser

> [!IMPORTANT]
> Rekryteringsfunktionen i det här avsnittet kallas för rekryteringsprojekt och är fokuserad på sökande, ansökningar och rekryteringsprojekt. 


Denna artikel beskriver ett begrepp som rekryterare kan använda för att följa stegen i en rekryteringsprocess, inklusive försök att annonsera lediga jobberbjudanden och att rekrytera sökande, spåra sökande och ansökningsinformation, intervjua sökande och välja en eller flera kandidater till lediga befattningar i din organisation.

## <a name="overview"></a>Översikt

Rekryteringsprojekt kan hjälpa dig att ordna stegen som du ska utföra när du fyller öppna befattningar i en juridisk person. En sökande är en person som söker anställning inom ditt företag. En ansökan är en sökandes uttryckta intresse att anställas av ett företag och kan vara knuten till ett rekryteringsprojekt för att visa intresse för en viss befattning. En enda sökande göra ha flera ansökningar inom samma juridiska person eller mellan flera företag inom din organisation.

## <a name="recruitment-projects"></a>Rekryteringsprojekt

Rekryteringsprojekt låter rekryterarna spåra förloppet när de försöker bemanna en eller flera lediga befattningar. Rekryteringsprojektet identifierar avdelning och projekt för vilka en eller flera befattningar kan tillsättas. Rekryteringsprojekt spårar även följande information om öppna befattningar:

- Det specifika antalet öppna befattningar
- Den anställande chefen och en alternativ kontakt för befattningen
- Datumet då rekvisitionen godkändes.
- Deadline för ansökning
- Uppskattat startdatum

Rekryteringsprojektet innehåller det värde för **Jobbannons** som används på sidan **Självbetjäning för medarbetare** för att annonsera den öppna befattningen. Öppningen kan visas för anställda endast om rekryteringsprojektet har ett värde på **Jobbannons**, fältet **Visa i självbetjäningen för medarbetare** anges till **Ja**, fältet **Deadline för ansökning** måste ställas in på ett framtida datum, och rekryteringsprojektet måste ha **Projektstatus** på **Startad**. Följande tabell visar möjlig status för flera rekryteringsprojekt och deras beskrivningar.

| Status    | Anger att...                                                                         |
|-----------|-----------------------------------------------------------------------------------------|
| Tidsplanerat | Rekryteringsinsatser förbereds. Rekryteringen har ännu inte påbörjats för detta projekt. |
| Startat   | Ansökningar accepteras nu för jobberbjudanden i det här projektet.                   |
| Färdigt  | Alla jobberbjudanden för det här projektet har fyllts.                                         |
| Avbrutna  | Rekryteringen har annullerats för det här projektet.                                          |

Rekryterare kan också registrera de **Medier** som används att annonsera jobberbjudandet via externa kanaler och även spåra **Utvecklingar** mot projektet eller ansökningarna.

## <a name="applicants"></a>Sökanden

En sökande är en person som söker ett jobb inom ditt företag. Sökande delas bland alla juridiska personer i organisationen. Därför har du en stor talangpool att söka i. Du kan underhålla kompetenser, referenser, logibegäran och personuppgifter för sökande. När du skapar en sökandepost, skapas en personpost för den sökanden i den globala adressboken. På sidan **Sökande** kan du uppdatera följande information om globala adressboken för kontakter som är sökande:

- Adressinformation
- Kontaktinformation
- Information om identifieringen
- Namnuppgifter
- Personuppgifter

## <a name="applications"></a>Ansökningar

Du kan registrera information från mottagna jobbansökningar på sidan **Ansökan**. En Ansökan skall den sökande uttryckta intresse för en befattning inom din organisation. För att skapa en ansökan måste den sökande redan finnas som en sökande eller person i ditt system.

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

En ansöknings korrespondensåtgärd bestämmer det dokument eller den e-postmall som du använder för att kommunicera med den sökande, som skickade in ansökan. Du kan associera **Ansökningsbokmärken** med korrespondensåtgärder, vilket låter dig använda värden från projektsidorna, **Ansökan**, **Sökande**, **intervju** och **Rekryteringsprojektsidor** i din kommunikation med de sökande. Genom att skapa **E-postmallar för ansökningar** för korrespondensåtgärder kan du snabbt skicka e-post till sökande som har en ansökan med en specifik kombination av status och korrespondensåtgärd. Du kan exempelvis skicka ett bekräftelsemail till alla sökande med **Status** för **inlevererad** och **Korrespondensåtgärd** **inlevererad**. När du har skickat e-postmeddelandet kan du automatiskt uppdatera statusen för ansökningarna.

## <a name="application-routing"></a>Ansökningsflöde

Om en ansökning måste granskas av flera medarbetare kan du använda sidan **Ansökningsflöde** för att skapa en cirkulationslista för medarbetarna i syfte att hantera processen. 

## <a name="interviews"></a>Intervjuer

**Intervjuer av sökande** kan schemaläggas från sidan **Ansökningar**. Använd knappen **Skicka mötesinformation** du vill skicka en kalenderfil med intervjuschemainformation till sökande och intervjuare.

## <a name="skill-mapping"></a>Kompetensmappning

**Kompetensmappning** och **Kompetensmappningsprofiler** kan användas för att identifiera de jobbsökande som kan passa ett jobberbjudande.

## <a name="hiring-applicants"></a>Anställa sökande

Använd sidna **Ansökningar** när du anställer en sökande. När du anställer en sökande, kommer ansökningsposten har statusvärdet **Anställd** och sökandens globala adressbokspost är kopplad till den nya medarbetarposten. Ändringar av informationen om den globala adressboken för den nya medarbetarposten visas även i ansökningsposten. Detta kan hjälpa till att minska registreringen av information om den nya arbetaren någonsin skulle ansöka om ett annat jobb inom ditt företag. Om du vill anställa en befintlig arbetare på en ny befattning klickar du på **Byt befattning** i listrutan **Ansökningsstatus** för att initiera flytten.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
