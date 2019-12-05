---
title: Nyheter och ändringar i Dynamics 365 Talent (5 november 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
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
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e6a81209c3c4a95ee51668533d40d4aecc1d58b9
ms.sourcegitcommit: a46fb06138f7f82e973dca3157d30f9b21d3a70b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/08/2019
ms.locfileid: "2778392"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (5 november 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2598. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="copy-a-core-hr-instance"></a>Kopiera en Core HR-instans

Under den här veckans utgåva kan du använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera Microsoft Dynamics 365 Talent: Core HR-databas till ett begränsat läge. Om du har en annan miljö med begränsat läge kan du även kopiera databasen från den miljön till en miljö med begränsat läge. Mer information finns i:

- [Bredare miljöhantering](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) i Dynamics 365:2019 utgivningsvåg 2-plan

- [Kopiera en Core HR-instans](hr-copy-instance.md) i Talent-dokumentationen

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a>Batchjobb för Common Data Service-integration skapas inte när Common Data Service integrationen är aktiverad (388030)

Denna ändring kommer att skapa batchjobb för Common Data Service-integration när den är aktiverad.

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a>HcmPersonImageEntity ändrar inte storlek på personbilden när den överförs (369469)

Denna veckas version ändrar hur bilderna storleks ändras för bättre prestanda när de importeras via datahantering.

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a>En befattning som är tillgänglig för tilldelningsdatum kan infalla tidigare än aktiveringsdatumet (340103)

Med den här ändringen visas en varning om du väljer **Tillgänglig för tilldelningsdatum** som är tidigare än befattningens **aktiveringsdatum**.

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a>Det går inte att skapa en begäran om kompensationsändring i medarbetarsjälvbetjäning för stegbaserade planer (376872)

I den här versionen åtgärdas ett problem när kompensationsändringar begärs via medarbetarsjälvbetjäning för stegbaserade planer. 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a>Orsakskoden synkroniseras inte till Common Data Service om beskrivningen är längre än 30 tecken, så att Core HR tillåter 60 (352682)

Med den här ändringen kommer orsakskoder med fler än 30 tecken att uppdateras i Common Data Service. Ändringar som görs i Common Data Service kommer också att återspeglas i Talent.

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a>Adressintegrationer från Talent till Finance and Operations (351961)

Genom den här versionen åtgärdas problemet att adresser som uppdateras i Talent inte uppdateras i Finance and Operations. Ändringar i adressblock kommer nu att uppdateras.

## <a name="coming-soon"></a>Kommer snart

### <a name="print-performance-reviews"></a>Skriv ut resultatöversyner

Se [Skriv ut resultatöversyner](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) i Dynamics 365: 2019 släpp påfyllnad 2 plan.

### <a name="feature-management-workspace"></a>Arbetsytan Funktionshantering

Funktioner läggs till och uppdateras i alla versioner. Funktionshanteringen är en arbetsyta där du kan visa en lista med funktioner som har levererats i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem.

Mer information om de ändringar som kommer från funktionshantering finns i [översikt över funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
