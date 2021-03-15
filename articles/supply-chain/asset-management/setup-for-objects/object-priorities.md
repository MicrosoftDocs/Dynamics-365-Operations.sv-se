---
title: Tillgångs tjänstenivå
description: I det här avsnittet beskrivs tillgångs tjänstenivåer i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 83b195add44927d847491e6394e72637323117b3
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021639"
---
# <a name="asset-service-levels"></a>Tillgångs tjänstenivå

[!include [banner](../../includes/banner.md)]

 

I det här avsnittet beskrivs tillgångs tjänstenivåer i tillgångshantering. Tillgångs tjänstenivåer är relaterade till tillgångar och överförs till underhållsbegäran och arbetsorder. De används för att beräkna prioriteten för arbetsorder under arbetsorderplaneringen. Tillgångs tjänstenivåer kan ändras om ändringar krävs.

Mer information om den inställning som är relaterad till beräkningen av bedömningspoäng för arbetsorderplanering finns i [i parametrar för tillgångshantering](../setup-for-objects/enterprise-asset-management-parameters.md). Du måste ställa in minst en standardpost för tillgångs tjänstenivån. Den här standardposten används om ingen annan matchning hittas under arbetsorderplaneringen.

**Exempel 1:** Standardtjänstenivå som används om ingen annan matchning hittas. I den här posten väljer du bara en tjänstenivå.

**Exempel 2:** en hög tjänstenivå som används för att tidsplanera jobb för en Volvo lastbilsmotor. I den här posten väljer du en relevant tillgångstyp (t.ex. **lastbilsmotor**), en tillverkare (**Volvo**) och en tjänstenivå.

## <a name="set-up-asset-service-levels"></a>Ställ in tillgångs tjänstenivåer

1. Välj **tillgångshantering** \> **inställningar** \> **tillgångs tjänstenivåer**.
2. Välj **Ny** för att skapa en post.
3. Beroende på den detaljnivå som krävs för tillgången tjänstenivå, göra relevanta val i fälten **funktionsplats**, **tillgångstyp**, **tillverkare**, **modell**, **tillgång**, **arbetsordertyp** och **tjänstenivå**.

    > [!NOTE]
    > När tillgångs tjänstenivå används för underhållsbegäran arbetsorder går tillgångshantering igenom alla tillgångs tillgångs tjänstenivåposter för att kontrollera om det finns en möjlig matchning. Den kontrollerar alltid den mest specifika kombinationen först. Med andra ord söker tillgångshantering först efter en matchning för fältet **arbetsordertyp**. Om ingen matchning hittas söker den efter en matchning för fältet **tillgång** och så vidare. Som du kan se i layouten på sidan **tillgångs tjänstenivåer** innebär detta att, för att hitta den mest specifika kombinationen, kontrollerar tillgångshantering varje post från höger till vänster för en matchning. Om ingen matchning hittas används den standardpost som inte har några val i dessa fält.

4. I fältet **tjänstnivå** väljer du en siffra som anger tjänstnivån (prioritet).


> [!NOTE]
> Om du ändrar en tillgångs tjänstenivåpost på sidan **tillgångs tjänstenivåer** när du redan har använt den på en arbetsorder, uppdateras tjänstenivån på underhållsbegäran och arbetsorder inte i enlighet med detta.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]