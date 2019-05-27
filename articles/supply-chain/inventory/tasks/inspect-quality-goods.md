---
title: Kontrollera kvaliteten på varor
description: I den här proceduren visas hur du bearbetar en kvalitetsorder.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9e9d750f116db62519ac7148f19bf62050430e9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545415"
---
# <a name="inspect-the-quality-of-goods"></a>Kontrollera kvaliteten på varor

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du bearbetar en kvalitetsorder. Du kan köra den här handboken i demonstrationsdataföretaget USMF. Innan du startar den här exempelproceduren måste du bekräfta inköpsorder ”000016” och bokföra en produktinleverans. Då skapas en kvalitetsorder automatiskt. Kvalitets-inspektioner utförs vanligtvis av en kvalitetsansvarig.


## <a name="select-a-quality-order"></a>Välj en kvalitetsorder.
1. Gå till Lagerhantering > Periodiska uppgifter > Kvalitetshantering > Kvalitetsorder.
2. Markera vald rad i listan.
    * Välj den kvalitetsorder som skapades innan du startade den här proceduren.  

## <a name="record-test-results"></a>Registrera testresultat
1. Klicka på Resultat.
2. Klicka på Redigera.
3. Ange ett nummer i fältet Resultatkvantitet.
4. Markera vald rad i listan.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Resultat.
6. Hitta och markera önskad post i listan.
    * I det här exemplet baseras resultatet på ett fördefinierat resultat. Normalt sett skulle du registrera ett mer specifikt testresultat, till exempel en storlek eller en annan dimension.  
7. Klicka på länken på den valda raden i listan.
8. Klicka på Spara.
9. Stäng sidan.

## <a name="validate-the-quality-order"></a>Validera kvalitetsordern
1. Klicka på Validera.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Validerad av.
    * Välj den användare som utför inspektionen.  
3. Klicka på länken på den valda raden i listan.
4. Klicka på Välj.
5. Klicka på OK.
6. Stäng sidan.

