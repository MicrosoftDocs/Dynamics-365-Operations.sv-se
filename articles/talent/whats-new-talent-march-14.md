---
title: Nyheter och ändringar i Dynamics 365 Talent (14 mars 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/14/2019
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
ms.search.validFrom: 2019-03-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 79bb8c0ed3c3f3bee62a8bc384a9d3a15cfe881a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897613"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-14-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (14 mars 2019)

Det här ämnet beskriver nya eller ändrade funktioner i Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract
Den här versionen innehåller mindre felkorrigeringar.

## <a name="changes-in-onboarding"></a>Ändringar i Onboard
Den här versionen innehåller mindre felkorrigeringar.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR
**Skapa 8.1.2186**

### <a name="performance-management-not-working-in-all-scenarios-when-using-duplicate-security-roles"></a>Prestandahantering fungerar inte i alla scenarier när du använder dubbla säkerhetsroller
Ändringar i den här versionen tillåter prestandahanteringsscenarier när du använder färdiga eller duplicerade roller.

### <a name="mass-assign-checklists-to-workers"></a>Masstilldela checklistor till arbetare
Med den här ändringen kan du välja flera medarbetare och masstilldela en eller flera checklistor till dessa medarbetare. 

### <a name="platform-update-24-for-finance-and-operations"></a>Plattformsuppdatering 24 för Finance and Operations
Ytterligare information om plattformsuppdatering 24 för Finance and Operations finns i [Nyheter eller ändringar i Finance and Operations plattformsuppdatering 24 (mars 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24). Betydande förändringar i plattform 24 omfattar: 

- Aviseringar har aktiverats i Talent.
- Det uppdaterade navigeringsfältet justeras med kontorsrubriken.

### <a name="office-location-update-switches-the-context-to-the-top-of-the-worker-list"></a>Uppdateringen av kontorsadress växlar kontext till toppen av arbetarlistan
Med den aktuella versionen flyttas ändrar inte längre kontorsadressen kontexten för arbetare som visas när du tilldelar en kontorsadress.

### <a name="position-assignment-end-date-doesnt-display-correctly-on-worker-hire-and-transfer-actions"></a>Befattningstilldelning och slutdatum visas inte korrekt i arbetarens anställnings- och överföringsåtgärder
Befattningstilldelningens slutdatum visas nu korrekt utifrån användarens prioriterade tidszon när den använder åtgärder.

### <a name="common-data-service-job-entity-doesnt-allow-job-type-and-job-function-fields-to-update"></a>Common Data Service jobbenheten tillåter inte att fälten jobbtyp och jobbfunktion uppdateras
Common Data Service-enheter synkroniseras nu korrekt när de uppdateras med hjälp av Common Data Service.

## <a name="coming-soon"></a>Kommer snart

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Avancerad kompensationssäkerhet (fasta och rörliga)
I många organisationer kan kompensations- och förmånsansvariga endast ha tillgång till vissa kompensationsposter. Posterna kan vara för chefer eller nationella medarbetare. Med den här ändringen kan personalavdelningen hantera och underhålla kompensationsplaner för olika medarbetargrupper i organisationen. Du ska tilldela säkerhetsroller till fasta och variabla planer som bestämmer åtkomsten till planer och medarbetardata relaterade till planerna, till exempel lön eller bonusposter. Endast roller med åtkomst kan bearbeta kompensation för dessa anställda.

###  <a name="email-support-for-alerts"></a>E-support för notifieringar
Med plattformsuppdatering 24 för Finance and Operations kan användare skapa notifieringsregler som automatiskt levererar e-postmeddelanden till kontakter när de utlöses av en händelse.

### <a name="duplicate-employee-check-interface-changes"></a>Dubblettkontroll av medarbetare: gränssnittsändringar
Med denna ändring detekteras dubbletter när du anger namnfält och status visar hur många som hittades. Du kan välja den angivna länken för att öppna en ny sida för att bedöma om du ska använda de identifierade träffarna. Dublettformuläret öppnas inte automatiskt för att undvika att inmatningen avbryts.
