---
title: Ställ in momsrapporteringskoder
description: Momsrapportkoderna refererar till ett fältnummer i momsrapporten.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4543cf7eaa0b1ef8e32d3fdafa2c354cd3739256
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554236"
---
# <a name="set-up-sales-tax-reporting-codes"></a>Ställ in momsrapporteringskoder

[!include [task guide banner](../../includes/task-guide-banner.md)]

Momsrapportkoderna refererar till ett fältnummer i momsrapporten. Dessa används för landsspecifika rapportlayouter och rapporten Momsbetalning per kod om du vill skriva ut momsbelopp för en kvittningsperiod som summeras per rapporteringskod. När du har skapat momsrapporteringskoder kan du referera till dem på rapportinställningssnabbflikarna på momskodsidan. 

I den här registreringen används demonstrationsföretaget DEMF.



1. Gå till Moms > Inställningar > Moms > Momsrapporteringskoder.
2. Klicka på Ny.
3. Välj den rapportlayout som rapporteringskoden tillhör.
    * Denna layout används för att filtrera de tillgängliga rapportkoderna för en momskod. Varje momskod tillhör en kvittningsperiod som tillhör en skattemyndighet, som använder en rapportlayout.  
4. Ange ett fältnummer som refererar till ett fält i en momsrapport.
5. Ange en beskrivning som ska visas på rapporter i rapporttextfältet.
6. Ange en beskrivning för internt bruk i fältet Kort beskrivning.
7. Klicka på Spara.

