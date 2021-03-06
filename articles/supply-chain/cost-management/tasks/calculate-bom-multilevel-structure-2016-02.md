---
title: Beräkna en strukturlista genom att använda en enda nivå (februari 2016)
description: Denna procedur beskriver hur du beräknar kostnaden för en färdig produkt genom att använda flera olika nedbrytningsnivåer baserade på arket för kostnadsredovisning.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 859f7b7c828dcdad1aa836044d2cc26847630f1e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821427"
---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016"></a>Beräkna en strukturlista genom att använda en enda nivå (februari 2016)

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]