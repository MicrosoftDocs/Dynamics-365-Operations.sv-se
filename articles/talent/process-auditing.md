---
title: Spåra ändringar i rekryteringsdata
description: Med processens granskningsfunktion kan du spåra när kandidater, jobberbjudanden eller jobbansökningar ändras för rapporter eller regelefterlevnadskrav.
author: tracykeya
manager: AnnBe
ms.date: 04/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: c009f82e69bff0e4ea540514de8f9e60eca1e466
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006366"
---
# <a name="track-changes-in-recruiting-data"></a>Spåra ändringar i rekryteringsdata

[!include [banner](includes/banner.md)]

Du kan nu spåra de ändringar som har gjorts för kandidater, jobberbjudanden och jobbansökningar genom att använda granskningsprocess. Detta är användbart för rapporter och regelefterlevnadskrav.

Du kan visa spårade data i Power BI genom att använda OData-kopplingen. Mer information finns i [ansluta till OData-feeder i Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-connect-odata).

## <a name="track-changes"></a>Spåra ändringar
Gör så här om du vill ställa in spårning av ändringar i dina rekryteringsdata:

1. I [Power Apps](https://web.powerapps.com), välj lämplig miljö.

2. Välj **inställningar** (kugghjulsikonen), välj **avancerade anpassningar** och välj sedan **resurser** under **utvecklingsresurser**. 

3. På sidan **utvecklarresurser** kopierar du värdet i fältet **instansens webb-API-värde**. Värdet kan till exempel se ut så här: https://yourorgname.api.crm.dynamics.com/api/data/v9.1/.

4. Du kan sedan fråga data från en av följande entiteter:
  - Historik för jobberbjudande (msdyn_jobopeninghistories)
  - Historik för jobbansökning (msdyn_jobapplicationhistories) 
  - Historik för kandidat (msdyn_candidatehistories)

## <a name="data-reported"></a>Data rapporterad

Följande data är tillgängliga när processgranskning används.

| Data rapporterad | Beskrivning |
| --- | --- |
| Ändrad av (msdyn_ChangedbyId) | Referens till användare |
| Skapades den (createdon) |  Datum och tid i UTC när ändringen inträffade |
| Ändringstyp (msdyn_changetype) | Vilken ändring hände |
| Vanliga värden för kandidater, jobberbjudanden, <br></br>och jobbansökningar | Skapat<br></br>Uppdaterad |
| Historik över jobbansökan | Artefakt tillagd <br></br>Artefakt borttagen |
| Historik för jobberbjudande | ATT GÖRA: post tillagd <br></br>ATT GÖRA: post borttagen <br></br>ATT GÖRA: post uppdaterad <br></br>ATT GÖRA: deltagaren har lagts till <br></br>ATT GÖRA: deltagaren är borttagen |
| Kandidathistorik | Artefakt tillagd <br></br>Artefakt borttagen <br></br>Arbetserfarenhet tillagd <br></br>Arbetserfarenhet borttagen <br></br>Utbildning tillagd <br></br>Utbildning borttagen <br></br>Kompetens tillagd <br></br>Kompetens borttagen <br></br>Tagg tillagd <br></br>Tagg borttagen <br></br>Socialt nätverk tillagt <br></br>Socialt nätverk borttaget <br></br>Persouppgifter tillagda <br></br>Persouppgifter uppdaterade<br></br> |
| Ändrade fält (msdyn_changedfields) | JSON-objekt med ändrade fält i en lista kanske inte lagrar värden för alla fält.<br></br><br></br>För ändringar "Skapade" och "Uppdaterade" listas fälten på den skapade eller ändrade posten.<br></br><br></br>För "tillagda" ändringstyper visas fälten i den underordnade posten i listan.<br></br><br></br>**Exempel:**<br></br><br></br>{<br></br>  "msdyn_applyurl": { "newValue": "" },<br></br>  "msdyn_description": { "valueOmitted": true } <br></br>} |
|Historik över jobbansökan | Jobbansökan (msdyn_JobapplicatonId)<br></br>Status (msdyn_status) <br></br>Statusorsak (msdyn_statusreason) <br></br>Orsak till avvisande (msdyn_rejectionreason) |
| Historik för jobberbjudande | Jobberbjudande (msdyn_JobopeningId) <br></br>Status (msdyn_jobopeningstatus) <br></br>Statusorsak (msdyn_jobopeningstatusreason) |
| Kandidathistorik | Kandidat (msdyn_CandidateId) |
