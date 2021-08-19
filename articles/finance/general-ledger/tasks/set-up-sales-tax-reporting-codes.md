---
title: Ställ in momsrapporteringskoder
description: Momsrapportkoderna refererar till ett fältnummer som anges i momsrapporten.
author: twheeloc
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b7d12ffa90bde30518780d750e74d20db89f007044f8622480b8bd6e629e00dd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728755"
---
# <a name="set-up-sales-tax-reporting-codes"></a>Ställ in momsrapporteringskoder

[!include [banner](../../includes/banner.md)]

Momsrapportkoderna refererar till ett fältnummer som anges i momsrapporten. De används på landsspecifika rapportlayouter. De används också på rapporten Momsbetalning per kod. Rapporten visar momsbelopp för en kvittningsperiod som summeras för varje rapporteringskod. När du har skapat momsrapporteringskoder kan du referera till koderna på rapportinställningssnabbflikarna, som du når från sidan **Momskod**. 

I den här registreringen används demonstrationsföretaget DEMF.

1. I **Navigeringsfönster**, gå till **Skatt > Inställningar > Moms > Momsrapporteringskoder**.
2. Klicka på **Ny**.
3. Välj den rapportlayout som rapporteringskoden tillhör. Denna layout används för att filtrera de tillgängliga rapportkoderna för en momskod. Varje momskod tillhör en kvittningsperiod som tillhör en skattemyndighet, som använder en rapportlayout.  
4. Ange ett nummer i fältet **Rapporteringskod**.
5. Ange en beskrivning som ska visas på rapporter i fältet **Rapporttext**.
6. Ange en beskrivning för internt bruk i fältet **Kort beskrivning**.
7. Klicka på **Spara**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]