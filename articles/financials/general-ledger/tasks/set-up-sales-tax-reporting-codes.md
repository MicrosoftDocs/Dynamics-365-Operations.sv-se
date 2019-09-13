---
title: Ställ in momsrapporteringskoder
description: Momsrapportkoderna refererar till ett fältnummer i momsrapporten.
author: twheeloc
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4751256858da417ec9bb1b7d9ccd16fb6bef1cac
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916101"
---
# <a name="set-up-sales-tax-reporting-codes"></a>Ställ in momsrapporteringskoder

[!include [task guide banner](../../includes/task-guide-banner.md)]

Momsrapportkoderna refererar till ett fältnummer i momsrapporten. Dessa används för landsspecifika rapportlayouter och rapporten Momsbetalning per kod om du vill skriva ut momsbelopp för en kvittningsperiod som summeras per rapporteringskod. När du har skapat momsrapporteringskoder kan du referera till dem på rapportinställningssnabbflikarna på momskodsidan. 

I den här registreringen används demonstrationsföretaget DEMF.

1. I **Navigeringsfönster**, gå till **Skatt > Inställningar > Moms > Momsrapporteringskoder**.
2. Klicka på **Ny**.
3. Välj den rapportlayout som rapporteringskoden tillhör. Denna layout används för att filtrera de tillgängliga rapportkoderna för en momskod. Varje momskod tillhör en kvittningsperiod som tillhör en skattemyndighet, som använder en rapportlayout.  
4. Ange ett nummer i fältet **Rapporteringskod**.
5. Ange en beskrivning som ska visas på rapporter i fältet **Rapporttext**.
6. Ange en beskrivning för internt bruk i fältet **Kort beskrivning**.
7. Klicka på **Spara**.

