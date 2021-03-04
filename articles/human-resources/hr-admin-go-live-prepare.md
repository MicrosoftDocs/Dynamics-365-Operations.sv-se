---
title: Förbered publicering av Human Resource
description: På den här sidan finns vägledning om hur du förbereder en publicering med Dynamics 365 Human Resources.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 59d7274c3b40e78209d90960c4514321b736876a
ms.sourcegitcommit: b40d6ce45aeb07724fc41d1a41923970b007fbcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2020
ms.locfileid: "4420665"
---
# <a name="prepare-for-human-resources-go-live"></a>Förbered publicering av Human Resource

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du förbereder dig inför publicering med ett Dynamics 365 Human Resources-projekt genom att använda Microsoft Dynamics  Lifecycle Services (LCS). 

Den här bilden illustrerar faserna i processen för publicering. 

![Publiceringsprocess](./media/hr-admin-go-live-prepare-process.png)

I följande tabell anges alla steg i processen, den förväntade varaktigheten och vem som är ansvarig för åtgärden.

| Fas | Åtgärd | Varaktighet/när | Vem | Anteckningar |
| --- | --- | --- | --- |--- |
| 1 | Uppdatera publiceringsdatum i LCS | Senast 2-3 månader i förväg | Partner/kund | Datumen för milstolparna bör ständigt uppdateras. |
| 2 | Slutför och skicka checklista | Efter testning av användargodkännande (UAT) har slutförts | Partner/kund | Följ de instruktioner som finns i [FastTrack publiceringsutvärdering](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment). |
| 3 | Projektutvärdering (FastTrack) | FastTrack-arkitekt* | Arkitekten levererar en bedömning när checklistan har tagits emot och fortsätter med granskningen tills frågorna är förtydligade och eventuella begränsningar. |
| 4 | Projekt studiegrupp (FastTrack) | FastTrack-arkitekt* | |
| 5 | Importer av datapaket | Beror på projektet | Partner/kund | Följ instruktionerna i [översikt över datahantering](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages).|
| 6 | Produktionsredo | När alla föregående steg har slutförts | Partner/kund | Partner/kund kan ta kontroll över produktionsmiljön.|
| 7 | Övergångsaktiviteter | Beror på projektet | Partner/kund | |
| 8 | Publicera | Beror på projektet | Kund | |

> [!IMPORTANT]
> * Steg 3 och 4 fylls bara i för kunder som är berättigade till FastTrack.

## <a name="completing-the-lcs-methodology"></a>Slutföra den LCS-metoden

En viktig milstolpe i varje implementeringsprojekt är övergången till produktionsmiljön. 

För att säkerställa att produktionsmiljön används för publiceringsåtgärder, tillhandahåller Microsoft produktionsinstansen endast när implementeringsfasen närmar sig fasen **Drift**, efter att de obligatoriska åtgärderna i LCS-metoden har slutförts. Mer information om dina miljöer i abonnemanget finns i  [licensguiden för Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). 

Kunderna måste slutföra faserna **analys**, **utforma och utveckla** och **testa** i LCS-metoden innan knappen  **Konfigurera**  för att begära att produktionsmiljön blir tillgänglig. Om du vill slutföra en fas i LCS måste du först slutföra alla nödvändiga steg i den fasen. När alla steg i en fas har slutförts kan du slutföra hela fasen. Du kan alltid öppna en fas igen senare om du måste göra ändringar. Mer information finns i  [Lifecycle Services (LCS) för Finance and Operations-appkunder](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs). 

Processen för att slutföra ett steg består av två delar: 

- Utför det verkliga arbetet, t.ex. en bristanalys och ett testning av användargodkännande (UAT). 
- Markera motsvarande steg i LCS-metoden som slutförd. 

Det är en god idé att slutföra stegen i metodiken när du gör framsteg med implementeringen. Vänta inte förrän den senaste minuten. Klicka inte bara igenom stegen så att du kan få en produktionsmiljö. Det är i kundens bästa intresse att ha en heltäckande implementering. 

## <a name="uat-for-your-solution"></a>UAT för din lösning

Under UAT-fasen måste du testa alla affärsprocesser som du har implementerat och de anpassningar som du har gjort i en miljö i begränsat läge i implementeringsprojektet. För att säkerställa en lyckad publicering bör du tänka på följande när du fyller i UAT-fasen: 

- Testärenden täcker hela kraven. 
- Testa genom att använda migrerade data. Dessa data bör inkludera huvuddata som arbetare, jobb och befattningar. Ta även med ingående balanser, som periodiseringar av tjänstledighet och frånvaro. Slutligen ska du inkludera öppna transaktioner, t.ex. aktuella förmånsregistrering. Slutför testningen med alla datatyper, även om datauppsättningen inte har slutförts. 
- Testa genom att använda rätt säkerhetsroller (standardroller och anpassade roller) som tilldelas användare. 
- Se till att lösningen följer eventuella företags- och branschspecifika föreskrifter. 
- Dokumentera alla funktioner och få godkännande och undertecknade av kunden. 

## <a name="fasttrack-go-live-assessment"></a>FastTrack publiceringsutvärdering

Kunder som är kvalificerade för FastTrack och som är engagerade i en FastTrack lösningsarkitekt slutför en publiceringsutvärdering med Microsoft FastTrack. Mer information:  [Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview). 

Ungefär åtta veckor före publiceringen uppmanas du att fylla i en [checklista för publiceringen i FastTrack](https://go.microsoft.com/fwlink/?linkid=2146013).

Projektledaren eller en nyckelprojektmedlem måste slutföra checklistan för publicering under fasen för förpublicering av projektet. Vanligtvis slutförs checklistan fyra till sex veckor före föreslagen publicering när UAT är slutförd eller nästan klar. 

När du är klar med checklistan för publicering skickar du den med e-post till din FastTrack lösningsarkitekt. Ta alltid med en nyckelintressent från kunden och implementeringspartnern på e-postmeddelandet. 

När du har skickat in checklistan granskar din FastTrack lösningsarkitekt projektet och tillhandahåller en utvärdering som beskriver de potentiella riskerna, bästa metoderna och rekommendationerna för en lyckad publicering av projektet. I vissa fall kan lösningsarkitekten betona riskfaktorer och be om en riskhanteringsplan. 

## <a name="see-also"></a>Se även

[Frågor och svar om publicering](hr-admin-go-live-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]