---
title: Ekonomiska dimensionsuppsättningar
description: Detta ämne beskriver ekonomiska dimensionsuppsättningar och innehåller lite tips för hur du optimerar deras användning.
author: yukonpeegs
ms.date: 03/07/2022
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9274e7f85005ab27d9f2b35fbb0be42e216941c9
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2022
ms.locfileid: "8392946"
---
# <a name="financial-dimension-sets"></a>Ekonomiska dimensionsuppsättningar

[!include [banner](../includes/banner.md)]

Detta ämne beskriver ekonomiska dimensionsuppsättningar och innehåller lite tips för hur du optimerar deras användning.

En dimensionsuppsättning är en ordnad lista över ekonomiska dimensioner som kan användas för att sammanfatta redovisningsdata på ett användardefinierat sätt. En primär användning av dimensionsuppsättningar är att definiera en råbalans.

Den enda standarddimensionsuppsättningen är den dimensionsuppsättning som bara innehåller huvudkontot.

På sidan **Uppsättningar för ekonomisk dimension** kan du skapa och hantera ekonomiska dimensionsuppsättningar.

## <a name="dimension-set-balances"></a>Saldon för dimensionsuppsättning

En dimensionsuppsättning kan ha saldon som baseras på dess ekonomiska dimensioner. Saldon finns i redovisningen och baseras på dimensionsuppsättningsdefinitionen. Saldona summeras från redovisningsdatan i syfte att förbättra prestandan när de hämtas (till exempel när en råbalans genereras).

## <a name="create-balances"></a>Skapa saldon

Använd knappen **Skapa saldon** för att initiera saldona för en dimensionsuppsättning som för närvarande inte har några saldon.

> [!NOTE]
> Vi rekommenderar att du begränsar antalet dimensionsuppsättningar som har saldon, detta eftersom saldouppdateringar påverkar alla redovisningsbokföringsaktiviteter.

## <a name="update-balances"></a>Uppdatera saldon

Använd knappen **Uppdatera saldon** för att inkludera den senaste bokföringsaktiviteten för redovisning i saldona. Saldouppdateringar är lätta åtgärder. De får bara bearbeta den bokföringsaktivitet i redovisningen som har skett sedan den senaste uppdateringen.

> [!NOTE]
> Visning av råbalansen framtvingar en uppdatering i syfte att säkerställa att de saldon som visas är aktuella. Överväg att använda ett återkommande batchjobb så att det går snabbt att uppdatera de dimensionsuppsättningar som används mest. På detta sätt minimerar du den tid som råbalansanvändare måste vänta.

## <a name="rebuild-balances"></a>Återskapa saldon

Använd knappen **Återskapa saldon** om du vill skapa saldona från grunden. På det här sättet hjälper du till att säkerställa att de matchar data i redovisningen. Att skapa saldon på nytt kräver mycket bearbetning och ska normalt inte krävas.

> [!NOTE]
> Om det finns ett scenario där saldon regelbundet måste byggas om rekommenderar vi att du kontaktar kundtjänsten. Kundtjänst kan hjälpa dig att ta reda på varför saldon inte matchar datan i redovisningen.

## <a name="clear-balances"></a>Rensa saldon

Använd knappen **Rensa saldon** om du vill ta bort saldon och stoppa ytterligare uppdateringar. Dimensionsuppsättningen kommer inte längre att påverka aktiviteter i redovisningsbokföringen.

## <a name="delete-a-dimension-set"></a>Ta bort en dimensionsgrupp

**Ta inte bort och återskapa** dimensionsuppsättningar som någon form av lösning för att lösa potentiella problem med saldodata för en viss dimensionsuppsättning. Att återskapa en dimensionsuppsättning är kostsamt. Om du vill ha mer hjälp med problem kontaktar du kundtjänsten. 


Mer information finns i [Ekonomiska dimensioner](financial-dimensions.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
