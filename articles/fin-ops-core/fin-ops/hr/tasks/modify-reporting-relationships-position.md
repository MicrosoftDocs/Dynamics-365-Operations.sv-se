---
title: Ändra rapporteringsrelationer för en befattning
description: I den här proceduren visas hur du ändrar rapporteringsrelationen för en medarbetare.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a1afd2c1cdc2ebaa303030d01b3bbe5fd2af44f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180063"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Ändra rapporteringsrelationer för en befattning

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du ändrar rapporteringsrelationen för en medarbetare. Rapporteringsrelationen kan användas för att dirigera dokument genom arbetsflödet. Proceduren visar även hur du tilldelar medarbetaren till ytterligare hierarkier. En medarbetare kan till exempel vara en del av en projektteam med en informell rapporteringsrelation till en projektansvarig. Fler rapporteringsrelationer kan definieras för befattningen för att kunna hantera olika projekt eller matrisscenarier. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till Personal > Befattningar > Befattningar.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel fältet Befattning med värdet 000091.
3. Klicka på länken på den valda raden i listan.
4. Expandera avsnittet Rapporter till befattning.
5. Klicka på Nytt om du vill öppna dialogrutan.
6. I fältet Rapporter till fält, ange eller välj ett värde.
7. Klicka på Skapa.
8. Utöka avsnittet Relationer.
9. Klicka på Lägg till.
10. Markera kryssrutan till vänster om rutnätet.
11. I fältet Hierarkinamn, ange eller välj ett värde.
    * Exempel: projekt  
12. I fältet Rapporter till befattning, ange eller välj ett värde.  Exempel: 000437
13. Klicka på Spara.
