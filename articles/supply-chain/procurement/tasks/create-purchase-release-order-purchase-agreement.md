---
title: Tillämpa ett köpeavtal när du skapar en inköpsorder
description: I den här proceduren visas hur du använder en inköpsavtal när du skapar en inköpsorder.
author: kamaybac
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1913181e85929951ce240ac31a0ac3f1351f6ae51f6ed2790bae577b2100b308
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731257"
---
# <a name="apply-a-purchase-agreement-when-creating-a-purchase-order"></a>Tillämpa ett köpeavtal när du skapar en inköpsorder

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du använder en inköpsavtal när du skapar en inköpsorder. Inköpsavtalet måste tillämpas när du skapar inköpsordern eftersom det finns allmänna villkor som ska kopieras till inköpsorderhuvudet. Uppgiften utförs vanligtvis av en inköpsagent. Som en förutsättning för den här guiden måste du ha ett giltigt inköpsavtal med en produktkvantitetsutfästelse för en leverantör och artiklar. Samma procedur kan användas om du har en inköpsavtal med andra typer av utfästelser.

## <a name="create-a-purchase-order"></a>Skapa en inköpsorder

1. Gå till **Produktion och källa \> Arbetsytor \> Inköpsorderförberedelse**.
1. Välj **Ny inköpsorder** i åtgärdsfönstret.
1. Dialogrutan **Skapa inköpsorder** öppnas. Välj ett **leverantörskonto**. Inspektera och justera de andra adressfälten efter behov.
1. Expandera **Allmänt** snabbflik.
1. Sök och välj det effektiva avtal som du vill använda i fältet **Inköpsavtal**. Alla tillgängliga avtal för leverantören anges här.  
1. Välj **Ja**.
1. Välj **OK**.

## <a name="add-a-line"></a>Lägg till en rad

1. I fältet **Artikelnummer**, skriv ett värde. Om det finns specifika lager- eller platsdimensioner på utfästelsen måste du ange samma värden på inköpsorderraden för att underlätta användningen av avtalet.
1. I fältet **Plats**, klicka på listruteknappen för att öppna sökningen. Webbplatsen kan redan ha fyllts i med standardvärdet från ordern eller från leverantören. Om så är fallet hoppar du över detta steg.  
1. Hitta och markera önskad post i listan.
1. Klicka på länken på önskad rad i valda listan.
1. Ange ett nummer i fältet **Kvantitet**. Validera att priset kopieras från utfästelsen.  

## <a name="look-up-the-commitment"></a>Slå upp utfästelsen

1. Välj **Uppdatera rad**.
1. Välj **Bifogad**. Här kan du få information om inköpsavtalet. Du kan till exempel se priset och om priset och rabatten är fasta, vilket innebär att om du ändrar priset eller rabatten på inköpsordern till ett annat värde än på utfästelsen, så tas länken bort så att inköpsorderraden inte uppfyller utfästelsen. Du kan även se om alternativet Max framtvingas, vilket innebär att kvantiteten på utfästelsen inte kan överskridas genom att summera alla inköp som uppfyller utfästelsen.  
1. Stäng sidan.

## <a name="look-up-the-purchase-agreement"></a>Slå upp inköpsavtalet

1. Välj **Allmänt** i **åtgärdsfönstret**.
1. Välj en **inköpsavtal**.
1. Stäng sidan.
1. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]