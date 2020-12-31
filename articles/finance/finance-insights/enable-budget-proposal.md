---
title: Aktivera budgetförslag (förhandsversion)
description: I det här ämnet beskrivs hur du aktiverar funktionen för Budgetförslag i Ekonomiinsikter.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: d8443c4e3e6f3d3a90acedc7c05b2846d6b68369
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646215"
---
# <a name="enable-budget-proposals-preview"></a>Aktivera budgetförslag (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här ämnet beskrivs hur du aktiverar funktionen för Budgetförslag i Ekonomiinsikter.

1. Använd information från miljösidan i Microsoft Dynamics Lifecycle Services (LCS) för att ansluta till den primära instansen av Azure SQL för den miljön. Kör följande Transact-SQL-kommando (T-SQL) för att aktivera förhandsversioner för sandbox-miljön. (Du kanske måste aktivera åtkomst för din IP-adress i LCS innan du kan fjärransluta till Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > Om din distribution av Microsoft Dynamics 365 Finance är en Service Fabric-distribution kan du hoppa över det här steget. Teamet för Ekonomiinsikter ska redan ha aktiverat förhandsversionen för dig. Om funktionen inte visas i arbetsytan **Funktionshantering**, eller om det uppstår problem när du försöker att aktivera den, skickar du e-post till [teamet för förhandsversionen av Ekonomiinsikts-appen](mailto:fiap@microsoft.com).

2. Öppna arbetsytan **Funktionshantering** och gör så här:

    1. Välj **Sök efter uppdateringar**.
    2. Sök efter **Budgetförslag** och aktivera den funktionen.

3. Gå till **Budgetering \> Konfigurera \> Grundläggande budgetering \> Budgetförslag (förhandsversion)** och välj **Aktivera funktion**.

#### <a name="privacy-notice"></a>Sekretesspolicy
Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.
