--- 
title: Skapa operationstidsmallar
description: "Arbetstidsmallar definierar arbetstiden under en vecka och används för att generera arbetstider för en tidsperiod."
author: sorenva
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2df37747601618fc3d45734152a05aedd39500a6
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-working-time-templates"></a>Skapa operationstidsmallar

[!include [task guide banner](../../includes/task-guide-banner.md)]

Arbetstidsmallar definierar arbetstiden under en vecka och används för att generera arbetstider för en tidsperiod. I den här proceduren visas om hur du definierar en arbetstidsmall med hjälp av arbetstidsplaneringsegenskaper för att kategorisera arbetstidintervall. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.

1. Gå till Alla arbetsytor > Livscykelhantering för resurs.
2. Klicka på Arbetstidsmallar.

## <a name="create-working-time-template"></a>Skapa arbetstidsmall
1. Klicka på Ny.
2. Skriv ett värde i fältet Arbetstidsmall.
3. Skriv ett värde i fältet Namn.
4. Expandera alternativet Måndag.
5. Klicka på Lägg till.
6. Ange en tid i fältet Från.
    * Ange tiden då arbetet börjar på morgonen.  
7. Ange en tid i fältet Till.
    * Ange tiden när medarbetare tar lunch.  
8. Klicka på Lägg till.
9. Ange en tid i fältet Från.
    * Ange tiden då arbetet återupptas efter efter lunch.  
10. Ange en tid i fältet Till.
    * Ange när arbetsdagen slutar.  

## <a name="replicate-working-times-to-all-week-days"></a>Replikera arbetstider till alla veckodagar
1. Klicka på Kopiera dag.
    * Kopiera arbetstidsdefinitioner från måndag till tisdag.  
2. Klicka på OK.
3. Klicka på Kopiera dag.
    * Kopiera arbetstidsdefinitioner från måndag till onsdag.  
4. Markera ett alternativ i fältet Till veckodag.
5. Klicka på OK.
6. Klicka på Kopiera dag.
    * Kopiera arbetstidsdefinitioner från måndag till torsdag.  
7. Markera ett alternativ i fältet Till veckodag.
8. Klicka på OK.
9. Klicka på Kopiera dag.
    * Kopiera arbetstidsdefinitioner från måndag till fredag.  
10. Markera ett alternativ i fältet Till veckodag.
11. Klicka på OK.

## <a name="define-time-slots-for-special-operations"></a>Definiera tidsluckor för särskilda operationer
1. Expandera alternativet Fredag.
2. Hitta och markera önskad post i listan.
3. Ange eller välj ett värde i fältet Egenskap.
4. Hitta och markera önskad post i listan.
5. Ange eller välj ett värde i fältet Egenskap.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Markera helgdagar som stängda för upphämtning
1. Expandera alternativt Lördag.
2. Välj Ja i fältet Stängd för upphämtning.
3. Expandera alternativet Söndag.
4. Välj Ja i fältet Stängd för upphämtning.


