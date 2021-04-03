---
title: Ändra rapporteringsrelationer för en befattning
description: I den här proceduren visas hur du ändrar rapporteringsrelationen för en medarbetare.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd884362393674a4f55ea0410548edbb72786fff
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465400"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Ändra rapporteringsrelationer för en befattning

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



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



[!INCLUDE[footer-include](../includes/footer-banner.md)]