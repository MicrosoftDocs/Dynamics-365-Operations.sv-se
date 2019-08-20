---
title: Kontrollera kvaliteten på varor
description: I det här avsnittet beskrivs hur du bearbetar en kvalitetsorder.
author: perlynne
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10acb9aadfeb11ede1d66dd525ace7b70db3bd1c
ms.sourcegitcommit: fbaccf72df82e6b6927f0c9f0d35af0ca3ecbc2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1855696"
---
# <a name="inspect-the-quality-of-goods"></a>Kontrollera kvaliteten på varor

[!include [task guide banner](../../includes/task-guide-banner.md)]

I det här avsnittet beskrivs hur du bearbetar en kvalitetsorder. Du kan köra den här handboken i demonstrationsdataföretaget USMF. Innan du startar den här exempelproceduren måste du bekräfta inköpsorder ”000016” och bokföra en produktinleverans. Då skapas en kvalitetsorder automatiskt. Kvalitets-inspektioner utförs vanligtvis av en kvalitetsansvarig.


## <a name="select-a-quality-order"></a>Välj en kvalitetsorder.
1. I navigeringsfönstret gå till **Moduler > Lagerhantering > Periodiska uppgifter > Kvalitetshantering > Kvalitetsorder**.
2. Välj den kvalitetsorder som skapades innan du startade den här proceduren.  

## <a name="record-test-results"></a>Registrera testresultat
1. Välj **resultat**.
2. Välj **Redigera**.
3. Ange ett nummer i fältet **Resultatkvantitet**.
4. I fältet **Resultat**  väljer du önskad post i listrutan.  
- I det här exemplet baseras resultatet på ett fördefinierat resultat. Normalt sett skulle du registrera ett mer specifikt testresultat, till exempel en storlek eller en annan dimension.  
5. Välj **Spara**.
6. Stäng sidan.

## <a name="validate-the-quality-order"></a>Validera kvalitetsordern
1. Välj **validera**.
2. I fältet **validerad av** väljer du den användare som utför inspektionen i den nedrullningsbara menyn.  
3. Klicka på **Välj**.
4. Välj **OK**.
5. Stäng sidan.

