--- 
title: "Ställ in momsrapporteringskoder"
description: "Momsrapportkoderna refererar till ett fältnummer i momsrapporten."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: fa32a12e49b6578c41ceb8991237a19ae3f77e17
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

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


