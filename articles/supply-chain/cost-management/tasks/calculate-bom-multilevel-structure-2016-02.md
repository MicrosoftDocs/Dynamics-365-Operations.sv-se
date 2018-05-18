--- 
title: "Beräkna en strukturlista genom att använda flera nivåer (enbart februari 2016)"
description: "Denna procedur beskriver hur du beräknar kostnaden för en färdig produkt genom att använda flera olika nedbrytningsnivåer baserade på arket för kostnadsredovisning."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 16c2cacaf70df5455c3ed49b8dcb5756e89f8cb8
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016-only"></a>Beräkna en strukturlista genom att använda flera nivåer (enbart februari 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Denna procedur beskriver hur du beräknar kostnaden för en färdig produkt genom att använda flera olika nedbrytningsnivåer baserade på arket för kostnadsredovisning. Detta är den sjunde uppgiften i beräkningsserien för strukturlista. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.

1. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
2. Hitta och markera önskad post i listan.
    * Välj produkten BOM_1.  
3. Klicka på Hantera kostnader i åtgärdsfönstret.
4. Klicka på Artikelpris.
5. Klicka på Beräkna artikelkostnad.
    * Du kan behöva klicka på ellipsen (...) om du vill se det här alternativet i huvudmenyn.  
6. Ange eller välj ett värde i fältet Kostnadsredovisningsversion.
    * Välj kostnadsredovisningsversion 20, detta eftersom kostnadstypen är planerad och nedbrytningsläget är multinivå.   Nedbrytningsläget multinivå gäller för planerade kostnader och simuleringar. Det används inte för standardkostnad.  
7. Klicka på OK.
8. Klicka på Visa beräkningsuppgifter.
    * Du kan behöva klicka på ellipsen (...) om du vill se det här alternativet i huvudmenyn.  I detta fall, notera hur BOM_2 har beräknats med hänsyn till råmaterial, bearbetning och omkostnader med totalt 29,40 i stället för standardkostnaden 10, som aktiverades i den inledande uppgiftsguiden i denna serie.  
9. Klicka på fliken för kostnadsredovisning.
    * I fliken för kostnadsredovisning varierar summorna per kostnadsgrupp jämfört med den beräkning som utförts i föregående uppgiftsguide.  
10. Välj "Multi" i nivåfältet.
    * När du väljer multi klassificeras flera kostnader i enlighet med sammansättningen av BOM_2, där 10 härleds från kostnadsgruppen M1 (ITEM_C) och 15,60 härleds från tillverkningen, där kostnadsgruppen är L2. Indirekta kostnader kan också variera.  
11. Stäng sidan.
12. Stäng sidan.


