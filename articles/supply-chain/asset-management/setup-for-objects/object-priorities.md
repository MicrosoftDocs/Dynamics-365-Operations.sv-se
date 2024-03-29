---
title: Servicenivåer för tillgång
description: I denna artikel beskrivs tillgångstjänstenivåer i Tillgångshantering.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f7429b30253f540925e67ff9239667a0a404f26
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908697"
---
# <a name="asset-service-levels"></a>Servicenivåer för tillgång

[!include [banner](../../includes/banner.md)]

 

I denna artikel beskrivs tillgångstjänstenivåer i Tillgångshantering. Tillgångs tjänstenivåer är relaterade till tillgångar och överförs till underhållsbegäran och arbetsorder. De används för att beräkna prioriteten för arbetsorder under arbetsorderplaneringen. Tillgångs tjänstenivåer kan ändras om ändringar krävs.

Mer information om den inställning som är relaterad till beräkningen av bedömningspoäng för arbetsorderplanering finns i [i parametrar för Tillgångshantering](../setup-for-objects/enterprise-asset-management-parameters.md). Du måste konfigurera minst en standardpost för tillgångs tjänstenivån. Den här standardposten används om ingen annan matchning hittas under arbetsorderplaneringen.

**Exempel 1:** Standardtjänstenivå som används om ingen annan matchning hittas. I den här posten väljer du bara en tjänstenivå.

**Exempel 2:** en hög tjänstenivå som används för att tidsplanera jobb för en Volvo lastbilsmotor. I den här posten väljer du en relevant tillgångstyp (t.ex. **lastbilsmotor**), en tillverkare (**Volvo**) och en tjänstenivå.

## <a name="set-up-asset-service-levels"></a>Ställ in tillgångs tjänstenivåer

1. Välj **Tillgångshantering** \> **inställningar** \> **tillgångs tjänstenivåer**.
2. Välj **Ny** för att skapa en post.
3. Beroende på den detaljnivå som krävs för tillgången tjänstenivå, göra relevanta val i fälten **funktionsplats**, **tillgångstyp**, **tillverkare**, **modell**, **tillgång**, **arbetsordertyp** och **tjänstenivå**.

    > [!NOTE]
    > När tillgångs tjänstenivå används för underhållsbegäran arbetsorder går Tillgångshantering igenom alla tillgångs tillgångs tjänstenivåposter för att kontrollera om det finns en möjlig matchning. Den kontrollerar alltid den mest specifika kombinationen först. Med andra ord söker Tillgångshantering först efter en matchning för fältet **arbetsordertyp**. Om ingen matchning hittas söker den efter en matchning för fältet **tillgång** och så vidare. Som du kan se i layouten på sidan **tillgångs tjänstenivåer** innebär detta att, för att hitta den mest specifika kombinationen, kontrollerar Tillgångshantering varje post från höger till vänster för en matchning. Om ingen matchning hittas används den standardpost som inte har några val i dessa fält.

4. I fältet **tjänstnivå** väljer du en siffra som anger tjänstnivån (prioritet).


> [!NOTE]
> Om du ändrar en tillgångs tjänstenivåpost på sidan **tillgångs tjänstenivåer** när du redan har använt den på en arbetsorder, uppdateras tjänstenivån på underhållsbegäran och arbetsorder inte i enlighet med detta.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]