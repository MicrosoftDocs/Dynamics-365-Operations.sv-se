---
title: Underhållsarbetare och arbetargrupper
description: I denna artikel förklaras begreppen underhållsarbetare och arbetargrupper inom anläggningstillgångar.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetWorkerGroupCopyFromResourceGroup, EntAssetWorkerGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3a24c880ee76af1490824aef07976b998d9225d0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860911"
---
# <a name="maintenance-workers-and-worker-groups"></a>Underhållsarbetare och arbetargrupper

[!include [banner](../../includes/banner.md)]

 

I denna artikel förklaras begreppen underhållsarbetare och arbetargrupper inom anläggningstillgångar. I Tillgångshantering kan du ansluta underhållsarbetare till funktionsplatser. (Mer information om funktionsplatser finns i [skapa funktionsplatser](../functional-locations/create-functional-locations.md).) Den här funktionen kan vara användbar om du till exempel schemalägger ett underhållsjobb på en dator som finns i funktionsplats 01 och du vill allokera underhållsarbetare från samma plats för att utföra jobbet.

Du kan också skapa underhållsarbetargrupper och associera underhållsarbetare med dem. Den här funktionen är användbar när du gör enkla arbetsorderplaneringar och du vill planera en grupp av underhållsarbetare på en arbetsorder. Du kan använda underhållsarbetare och underhållsarbetsgrupper för att konfigurera önskade underhållsarbetare och ansvariga underhållsarbetare. 


## <a name="create-workers"></a>Skapa arbetare

1. Välj **Tillgångshantering** \> **inställning** \> **arbetare** \> **arbetare**.
2. Välj **Ny** om du vill lägga till en arbetare till listan.
3. I fältet **arbetare** väljer du arbetaren.
4. Ange alternativet **aktiva** till **ja** för att schemalägga arbetaren på arbetsorder.

    På snabbfliken **allmänt** fylls fälten **resurs** och **beskrivning** i automatiskt om en resurs har valts för medarbetaren. Fältet **kalender** fylls också i automatiskt, förutsatt att du har ställt in arbetaren som en resurs och tilldelat en kalender till den resursen på sidan **resurser** (**Organisationsadministration** \> **Resurser** \> **Resurser**).

5. På snabbfliken **grupper** väljer du **Lägg till** och väljer sedan en underhållsarbetsgrupp för arbetaren. En arbetare kan vara kopplad till fler än en grupp.
6. I standardkonfigurationen gäller en arbetares tillhörighet till en grupp från det datum då du lägger till gruppen och den upphör aldrig att gälla. Detta datum visas i fältet **gällande**. För att visa fältet **Giltighet** väljer du **Visa** \> **Alla**. Om medarbetarens tillhörighet till en grupp ska begränsas till en viss period använder du fälten **Giltighet** och **Utgång** för att definiera perioden.
7. På snabbfliken **funktionsplatser** väljer du **Lägg till** och väljer sedan en funktionsplatser för underhållsarbetaren. Ange även vilken plats som är den primära funktionsplatsen för arbetaren.

    > [!NOTE]
    > När du lägger till funktionsplatser till en arbetare, visas alla aktiva tillgångar som är relaterade till dessa funktionsplatser på olika menyalternativ, till exempel **mina aktiva tillgångar** och **mina aktiva funktionsplatser**. De visas också i tillgångsuppslag som visas när du skapar en ny tillgång, underhållsbegäran eller arbetsorder.

    Fälten på snabbfliken **Detaljer** visar antalet underhålls arbetsgrupper och funktionsplatser som den valda underhållsarbetaren är relaterad till.

## <a name="create-worker-groups"></a>Skapa arbetargrupper

1. Välj **Tillgångshantering** \> **inställning** \> **arbetare** \> **underhållsarbetargrupper**.
2. Välj **Ny** om du vill lägga till en arbetargrupp till listan.
3. I fältet **underhållsarbetargrupp** anger du ett grupp-ID.
4. Ange sedan ett namn i fältet **Namn**.
5. På snabbfliken **arbetare** väljer du **Lägg till** och väljer sedan en underhållsarbetsgrupp för arbetargruppen. Information om fälten **giltighet** och **utgång** finns i steg 6 i föregående procedur.
6. Om en resursgrupp ska relateras till den valda gruppen för underhållsarbetare väljer du **kopiera från resursgrupp**. i fältet **grupp** väljer du den resursgrupp som du vill kopiera kalenderinställningar från. Välj sedan i fältet **arbetargrupp** den arbetargrupp som du vill kopiera resursgruppens kalenderinställningar till. Det här steget är endast relevant om du vill att underhållsarbetare ska använda kalendern som är relaterad till en resurs (produktionsgruppen) vid schemaläggning av arbetsorder.

    Fältet på snabbfliken **Detaljer** visar antalet underhållsarbetare som har ställt in den valda underhållsarbetargruppen.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]