---
title: Förbered publicering av Human Resource
description: På den här sidan finns vägledning om hur du förbereder en publicering med Dynamics 365 Human Resources.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 425dfad542cf19e039f8613c5f7bcaacb4b15930
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688867"
---
# <a name="prepare-for-human-resources-go-live"></a>Förbered publicering av Human Resource

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../includes/peap-2.md)]

I det här avsnittet beskrivs hur du förbereder dig inför publicering med ett Dynamics 365 Human Resources-projekt genom att använda Microsoft Dynamics  Lifecycle Services (LCS). 

Den här bilden illustrerar faserna i processen för publicering. 

![Publiceringsprocess.](./media/hr-admin-go-live-prepare-process.png)

I följande tabell anges alla steg i processen, den förväntade varaktigheten och vem som är ansvarig för åtgärden.

| Fas | Åtgärd | Varaktighet/när | Vem | Anteckningar |
| --- | --- | --- | --- |--- |
| 1 | Uppdatera publiceringsdatum i LCS | Senast 2-3 månader i förväg | Partner/kund | Datumen för milstolparna bör ständigt uppdateras. |
| 2 | Slutför och skicka checklista | Efter testning av användargodkännande (UAT) har slutförts | Partner/kund | Följ de instruktioner som finns i [FastTrack publiceringsutvärdering](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment). |
| 3 | Projektutvärdering (FastTrack) | FastTrack-arkitekt* | Arkitekten levererar en bedömning när checklistan har tagits emot och fortsätter med granskningen tills frågeställningarna är förtydligade och eventuella begränsningar. |
| 4 | Projekt studiegrupp (FastTrack) | FastTrack-arkitekt* | |
| 5 | Importer av datapaket | Beror på projektet | Partner/kund | Följ instruktionerna i [översikt över datahantering](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).|
| 6 | Produktionsredo | När alla föregående steg har slutförts | Partner/kund | Partner/kund kan ta kontroll över produktionsmiljön.|
| 7 | Övergångsaktiviteter | Beror på projektet | Partner/kund | |
| 8 | Publicera | Beror på projektet | Kund | |

> [!IMPORTANT]
> * Steg 3 och 4 fylls bara i för kunder som är berättigade till FastTrack.

## <a name="completing-the-lcs-methodology"></a>Slutföra den LCS-metoden

En viktig milstolpe i varje implementeringsprojekt är övergången till produktionsmiljön. Processen för att slutföra ett steg består av två delar: 

- Utför det verkliga arbetet, t.ex. en bristanalys och ett testning av användargodkännande (UAT). 
- Markera motsvarande steg i LCS-metoden som slutförd. 

Det är en god idé att slutföra stegen i metodiken när du gör framsteg med implementeringen. Vänta inte förrän den senaste minuten. Det är i kundens bästa intresse att ha en heltäckande implementering. 

## <a name="uat-for-your-solution"></a>UAT för din lösning

Under UAT-fasen måste du testa alla affärsprocesser som du har implementerat och de anpassningar som du har gjort i en miljö i begränsat läge i implementeringsprojektet. För att säkerställa en lyckad publicering bör du tänka på följande när du fyller i UAT-fasen: 

- Vi rekommenderar att din UAT-process startar med en ren och ny miljö där data från DIN GOLD-konfiguration kopieras till miljön innan UAT-processen startas. Vi rekommenderar att du använder produktionsmiljön som din GULD-miljö tills du går-live, då miljön blir produktion.
- Testärenden täcker hela kraven. 
- Testa genom att använda migrerade data. Dessa bör inkludera data som exempelvis medarbetare, jobb och befattningar. Ta även med ingående balanser, som periodiseringar av tjänstledighet och frånvaro. Slutligen ska du inkludera öppna transaktioner, t.ex. aktuella förmånsregistrering. Slutför testningen med alla datatyper, även om datauppsättningen inte har slutförts. 
- Testa genom att använda rätt säkerhetsroller (standardroller och anpassade roller) som tilldelas användare. 
- Se till att lösningen följer eventuella företags- och branschspecifika föreskrifter. 
- Dokumentera alla funktioner och få godkännande och undertecknade av kunden. 

## <a name="mock-go-live"></a>Testlansering

Innan du lanserar måste du utföra en testlansering för att testa vilka steg som krävs för att ta steget från dina äldre system till det nya systemet. Du ska utföra din testlansering i en sandbox-miljö och ta med alla steg i din omställningsplan.

- Vi rekommenderar att du använder produktionsmiljön som GULD-konfigurationsmiljö före lansering.
- Se till att du har en stark styrningsprocess på plats för att skydda produktionsmiljön från oavsiktlgia transaktioner eller uppdateringar före lanseringen.
- När du är klar att utföra UAT eller testlanseringen uppdaterar du sandbox-miljön från produktionsmiljön. Mer information finns i [Kopiera en isntans](hr-admin-setup-copy-instance.md).
- Testa varje steg i din övergångsplan i sandbox-miljön och validera den sedan sandbox-miljön genom att utföra stickprov eller tester från dina UAT-skript i miljön.
  - Testerna ska omfatta alla datamigreringar, inklusive de omvandlingar som behövs för lanseringen.
  - Processen bör inkludera en övningsavstängning av alla äldre system.
  - Se till att inkludera alla integrationsövergångssteg eller externa systemsteg i din testövergång.
- Om det skulle uppstå problem under testomställningen kan det bli nödvändigt med en andra testomställning. Därför rekommenderar vi att du planerar för två testomställningar i projektplanen.

## <a name="fasttrack-go-live-assessment"></a>FastTrack publiceringsutvärdering

Kunder som är kvalificerade för FastTrack och som är engagerade i en FastTrack lösningsarkitekt slutför en publiceringsutvärdering med Microsoft FastTrack. Mer information:  [Microsoft FastTrack](/dynamics365/fasttrack/). 

Ungefär åtta veckor före publiceringen uppmanas du att fylla i en [checklista för publiceringen i FastTrack](https://go.microsoft.com/fwlink/?linkid=2146013).

Projektledaren eller en nyckelprojektmedlem måste slutföra checklistan för publicering under fasen för förpublicering av projektet. Vanligtvis slutförs checklistan fyra till sex veckor före föreslagen publicering när UAT är slutförd eller nästan klar. 

När du är klar med checklistan för publicering skickar du den med e-post till din FastTrack lösningsarkitekt. Ta alltid med en nyckelintressent från kunden och implementeringspartnern på e-postmeddelandet. 

När du har skickat in checklistan granskar din FastTrack lösningsarkitekt projektet och tillhandahåller en utvärdering som beskriver de potentiella riskerna, bästa metoderna och rekommendationerna för en lyckad publicering av projektet. I vissa fall kan lösningsarkitekten betona riskfaktorer och be om en riskhanteringsplan. 

## <a name="see-also"></a>Se även

[Frågeställningar och svar om publicering](hr-admin-go-live-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
