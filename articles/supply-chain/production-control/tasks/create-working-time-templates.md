---
title: Skapa operationstidsmallar
description: Arbetstidsmallar definierar arbetstiden under en vecka och används för att generera arbetstider för en tidsperiod.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 130a21d08e4e720f8bf803a5d4b03d315cefc26f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580682"
---
# <a name="create-working-time-templates"></a>Skapa operationstidsmallar

[!include [banner](../../includes/banner.md)]

Arbetstidsmallar definierar arbetstiden under en vecka och används för att generera arbetstider för en tidsperiod. I den här proceduren visas om hur du definierar en arbetstidsmall med hjälp av arbetstidsplaneringsegenskaper för att kategorisera arbetstidintervall. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.

1. Gå till **Arbetsytor > Livscykelhantering för resurser**.
1. Välj **Arbetstidmallar**.

## <a name="create-working-time-template"></a>Skapa arbetstidsmall

1. Välj **Ny**.
1. I fältet **Arbetstidmall** anger du ett värde.
1. Skriv ett värde i fältet **Namn**.
1. Expandera avsnittet **Måndag**.
1. Markera **Lägg till**.
1. Ange en tidpunkt i fältet **Från**.
    * Ange tiden då arbetet börjar på morgonen.  
1. Ange en tidpunkt i fältet **Till**.
    * Ange tiden när medarbetare tar lunch.  
1. Markera **Lägg till**.
1. Ange en tidpunkt i fältet **Från**.
    * Ange tiden då arbetet återupptas efter efter lunch.  
1. Ange en tidpunkt i fältet **Till**.
    * Ange när arbetsdagen slutar.  

## <a name="replicate-working-times-to-all-week-days"></a>Replikera arbetstider till alla veckodagar

1. Välj **Kopiera dag**.
    * Kopiera arbetstidsdefinitioner från måndag till tisdag.  
1. Välj **OK**.
1. Välj **Kopiera dag**.
    * Kopiera arbetstidsdefinitioner från måndag till onsdag.  
1. Välj ett alternativ i fältet **Till veckodag**.
1. Välj **OK**.
1. Välj **Kopiera dag**.
    * Kopiera arbetstidsdefinitioner från måndag till torsdag.  
1. Välj ett alternativ i fältet **Till veckodag**.
1. Välj **OK**.
1. Välj **Kopiera dag**.
    * Kopiera arbetstidsdefinitioner från måndag till fredag.  
1. Välj ett alternativ i fältet **Till veckodag**.
1. Välj **OK**.

## <a name="define-time-slots-for-special-operations"></a>Definiera tidsluckor för särskilda operationer

1. Expandera avsnittet **Fredag**.
1. Hitta och markera önskad post i listan.
1. Ange eller välj ett värde i fältet **Egenskap**.
1. Hitta och markera önskad post i listan.
1. Ange eller välj ett värde i fältet **Egenskap**.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Markera helgdagar som stängda för upphämtning

1. Expandera avsnittet **Lördag**.
1. Välj *Ja* i fältet **Stängd för avhämtning**.
1. Expandera avsnittet **Söndag**.
1. Välj *Ja* i fältet **Stängd för avhämtning**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]