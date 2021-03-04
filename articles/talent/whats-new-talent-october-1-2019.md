---
title: Nyheter och ändringar i Dynamics 365 Talent (1 oktober 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 69c0a805027f215b2a2a42d826ee7a346cfdd511
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529670"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-1-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (1 oktober 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2509. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="streamlined-employee-entry-and-navigation"></a>Strömlinjeformad medarbetarinmatning och navigering

Den här funktionen är nu tillgänglig i alla miljöer med begränsat läge. Om du vill aktivera den här funktionen navigerar du till **Systemadministration > Länkar > Inställningar > Systemparametrar > Förhandsfunktioner**. Välj **Förbättrade arbetarformulär och navigering**. Dessa ändringar aktiveras för alla användare. Du kan stänga av det här alternativet när du vill.

Mer information finns i [strömlinjeformad medarbetarinmatning och navigering](./streamlined-employee-entry.md) För att se en video med ändringarna, se [Dynamics 365 for Talent 2019 släpp av påfyllnad 2 - översikt](https://aka.ms/ROGT19RW2ROV).

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>Du kan aktivera förhandsgranskningsfunktioner i begränsade miljöer och testmiljöer

När du etablerar en ny instans av Talent kan du ange om instanstypen är produktion eller begränsat läge. Med instanser Begränsat läge kan tidig test av nya funktioner göras. Om du vill uppdatera en av dina befintliga förekomster till instanstypen Begränsat läge kontaktar du Support för att initiera ändringsbegäran.

Mer information om hur du ändringar publiceras finns i [Etablera Talent](./provisioning-talent.md).

### <a name="compensation-date-defaults-to-a-different-date-than-the-position-assignment-337694"></a>Kompensationsdatum är som standard ett annat datum än befattningstilldelningen (337694)

Med denna ändring är ersättningsstartdatum standardvärdet för startdatum för positionstilldelning.

### <a name="not-able-to-end-compensation-along-with-its-position-assignment-328993"></a>Det går inte att avsluta kompensationen tillsammans med befattningstilldelningen (328993)

Med den här ändringen kan du avsluta kompensationen när du avslutar befattningstilldelningen genom att använda **Avsluta tilldelning** på sidan **Befattningstilldelningar för arbetare** med personalåtgärder aktiverade.

### <a name="bank-account-validation-requires-routing-and-account-numbers-in-all-locations-340403"></a>För bankkontovalidering krävs organisations- och kontonummer på alla platser (340403)

Med den här veckans ändringar har ett nytt konfigurationsalternativ lagts till för att inaktivera krävd validering av **organisationsnummer** och **kontonummer**. 

### <a name="attachments-are-not-enabled-in-mss-performance-journals-for-performance-feedback-341794"></a>Bilagor är inte aktiverade i MSS-prestandajournaler för återrapportering av resultat (341794)

Med den här veckans frisläppning är bilagor aktiverade för återrapporteringsartiklar på sidan resultatjournal.

### <a name="leave-request-details-dont-sync-from-common-data-service-to-talent-369608"></a>Information om att lämna begäran synkroniseras inte från Common Data Service till Talent (369608)

Med dessa ändringar lämnar du information om begäran som uppdateras i Common Data Service synkroniserar tillbaka till Talent.

### <a name="job-description-doesnt-display-for-the-job-in-the-skill-gap-analysis-page-369398"></a>Jobbeskrivning visas inte för jobbet på sidan Analys av kompetenslucka (369398)

I den här veckans version visas beskrivningen när du väljer jobbet på sidan **Analys av kompetenslucka**.

## <a name="coming-soon"></a>Kommer snart

### <a name="print-performance-reviews"></a>Skriv ut resultatöversyner

Medarbetare, chefer och personalansvariga kan skriva ut en medarbetares resultatöversyn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]