---
title: Nyheter och ändringar i Dynamics 365 Talent (14 februari 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 32f3bab38233833498ed566fa1558a023b3bc0dd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462600"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-14-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (14 februari 2019)

Det här ämnet beskriver nya eller ändrade funktioner i Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract
Den här versionen innehåller mindre felkorrigeringar.

## <a name="changes-in-onboarding"></a>Ändringar i Onboard
Den här versionen innehåller mindre felkorrigeringar.
 
## <a name="changes-in-core-hr"></a>Ändringar i Core HR 
**Skapa 8.1.2146**

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a>Entiteten Medarbetarens fasta kompensation exporterar inte alla poster
Med denna ändring kommer entiteten **Medarbetarens fasta kompensation** nu att exportera alla poster. Entiteten kan användas för att skapa och uppdatera befintliga fasta kompensationsposter för medarbetare. 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a>Anställningens slutdatum tar inte hänsyn till medarbetarens prioriterade tidszon
Slutdatum för anställning tar nu hänsyn till användardefinierad tidszon när du skapar eller avslutar anställning hos ett företag.
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a>Adresser i Storbritannien visas i analyser som adresser i östra Schweiz
I denna version har en ändring gjorts för att korrigera felaktiga inställningar av adresser i rapporten **personalhantering** ”personalstyrka per plats”.
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a>Uppsägningskod fylls inte i på tilldelningsposten för arbetarens befattning när den avslutar befattningen
En ändring har gjorts till standard för koden "Uppsägningsorsak" vid avslut av en anställds befattningstilldelning.

### <a name="new-entity-created-for-job-compensation-levels"></a>Ny entitet som skapats för jobbkompensationsnivåer
En ny entitet för datahanteringsramverk (DMF) skapades. Entiteten skapar och uppdaterar till kompensationsnivåer, marknadsvärde och urvalsundersökningar för varje jobb som är definierat i systemet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]