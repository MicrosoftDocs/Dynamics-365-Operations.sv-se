---
title: Skapa ett avskrivningsförslag
description: Den här artikeln beskriver hur avskrivningsbatchförslag fungerar och förklarar hur man föreslår avskrivning för anläggningstillgångar.
author: abruer
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1f39a1412c6f96fe0a8261602a88a6a3c3cd6b8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858508"
---
# <a name="create-a-depreciation-proposal"></a>Skapa ett avskrivningsförslag

[!include [banner](../../includes/banner.md)]

Den här artikeln beskriver hur avskrivningsbatchförslag fungerar och förklarar hur man föreslår avskrivning för anläggningstillgångar. I denna uppgift används USMF-demonstrationföretaget och revisorrollen.


## <a name="create-a-depreciation-proposal"></a>Skapa ett avskrivningsförslag
1. I navigeringsfönstret går du till **Anläggningstillgångar > Journalposter > Skapa avskrivningsförslag**.
2. I fältet **Journalnamn** väljer du ett alternativ i den nedrullningsbara menyn.
3. I fältet **Till-datum**, anger du ett datum.

    - Välj alternativet **Summera avskrivning** för att summera månadsvisa avskrivningar till en journalrad.  
    - Till exempel om värdet för Till-datum är 31 mars 2015 skapas följande beskrivning: ”avskrivning sedan 31 januari 31 2015”. Fältet **Datum** på de föreslagna journalraderna ställs sedan in till 31 mars 2015.  
    - Avskrivningsförslaget kan filtreras per tillgång, tillgångsgrupp eller andra kriterier med hjälp av alternativet **Filter**.  
    - När du använder formuläret **Skapa förvärvs- eller avskrivningsförslag för anläggningstillgångar**, kan du ange avskrivning i batchar. Detta rekommenderas för större förslag som kräver mer systemresurser. Om du väljer batchalternativet, kan du fortfarande använda slutföra andra uppgifter under den tidsperioden. När du föreslår avskrivning på detta sätt, beräknas avskrivningen för värdemodeller för anläggningstillgångar.  

4. Välj **Skapa journal**.

## <a name="review-depreciation-entries"></a>Granska avskrivningposter
1. I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar**.
2. Hitta och markera önskad post i listan.
3. Markera **rader**
4. Vald **bokföring**



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
