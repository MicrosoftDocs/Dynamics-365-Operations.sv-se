---
title: Nyheter och ändringar i Dynamics 365 Talent (29 oktober 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e2d79ee9e182df4a4efe65beb685567b1e7446ce
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897452"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (29 oktober 2019)

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2586. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a>Ta bort parter utan roller ska som standard vara aktiverat (371233)

När du etablerar en ny miljö i Talent aktiveras **Ta bort parterna om ingen roll finns** som standard. När du tar bort en arbetare tas inte den part som är kopplad till arbetaren bort om inte inställningen aktiveras. Den här ändringen begränsar dubblettposter i den globala adressboken när du behöver importera, ändra eller importera om arbetare.

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a>Utkast och avbrutna förfrågningar om tjänstledighet bör tillåtas att tas bort i Common Data Service (376999)

Med den här ändringen kan du nu ta bort tjänstledighetsbegäranden med statusen **utkast** eller **avbruten** i Common Data Service.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Ytterligare listvärden i anpassade fält visas inte i Common Data Service när du klickar på tillämpa på formuläret anpassade fält (379599)

När du lägger till nya listvärden i ett befintligt anpassat fält som redan har synkroniserats med Common Data Service, är de nu tillgängliga i Common Data Serivce när du har tillämpat ändringarna i formuläret **anpassade fält**.

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a>Använd checklistor för registrering över juridiska personer när det finns fler än en anställning (371270)

Under den här veckans frisläppning kan du koppla checklistor till medarbetare med fler än en anställning i **formuläret arbetare > checklistor**.

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a>Funktionen för Öppna anmälan i förhandsversionen har tagits bort

I samverkan med vårt meddelande i blogginlägget [Strategiska investeringar i det Core HR-systemet för att effektivisera verksamheten](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) tar Microsoft bort funktionen för öppna anmälan i den allmänna förhandsversionen. Nya funktioner att publiceras i framtiden. Produktionsanvändning av funktionen för öppna anmälan stöds inte.

## <a name="coming-soon"></a>Kommer snart

### <a name="print-performance-reviews"></a>Skriv ut resultatöversyner

Se [Skriv ut resultatöversyner](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) i Dynamics 365: 2019 släpp påfyllnad 2 plan.

### <a name="feature-management-workspace"></a>Arbetsytan Funktionshantering

Funktioner läggs till och uppdateras i alla versioner. Funktionshanteringen är en arbetsyta där du kan visa en lista med funktioner som har levererats i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem.

Mer information om de ändringar som kommer från funktionshantering finns i [översikt över funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
