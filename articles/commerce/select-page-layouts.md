---
title: Välj sidlayouter
description: Denna artikel beskriver hur du skapar och väljer sidlayouter i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: c01be029a79efe8c3fac6203db51dd1a5a8516e3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282088"
---
# <a name="select-page-layouts"></a>Välj sidlayouter


[!include [banner](includes/banner.md)]

Denna artikel beskriver hur du skapar och väljer sidlayouter i Microsoft Dynamics 365 Commerce.

## <a name="create-layouts-for-an-existing-page"></a>Skapa layouter för en befintlig sida

> [!NOTE]
> Du kan bara skapa layouter för en befintlig sida om sidan har minst två moduler under huvudplatsen.

Om du vill skapa layouter för en befintlig sida följer du stegen nedan.

1. Gå till **sidor** och sök efter den befintliga sidan i listan. Använd sökfunktionen som du behöver.
1. Markera sidan, välj **redigera** om du vill checka ut den och välj sedan namnet på sidan för att öppna den. Gör en notering av modulens ordning.
1. Välj **Spara som ny layout**.
1. Ange ett namn på layouten och välj sedan **OK**.
1. Välj **konvertera till inbäddad layout**.
1. Ändra ordning på modulerna efter behov och anteckna den nya ordningen.
1. Välj **Spara som ny layout**.
1. Ange ett namn på layouten och välj sedan **OK**.
1. Välj **ändra layout**, välj den första layout som du skapade och välj sedan **OK**. Gör en notering av modulens ordning. Ändra den så att den matchar den modulordning som sparades med layouten.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den. 

## <a name="select-a-different-layout-for-an-existing-page"></a>Välja en annan layout för en befintlig sida

> [!NOTE]
> Du kan bara välja en annan layout för en befintlig sida om mallen som användes för att skapa sidan har mer än en layout.

Om du vill välja en annan layouter för en befintlig sida följer du stegen nedan.

1. Gå till **sidor** och sök efter den befintliga sidan i listan. Använd sökfunktionen som du behöver.
1. Markera sidan, välj **redigera** om du vill checka ut den och välj sedan namnet på sidan för att öppna den.
1. Välj **Ändra layout**.
1. Välj den nya layouten för sidan och välj sedan **OK**. Sidredigeraren uppdateras för att visa den nya layouten.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Ändra en befintlig webbplatssida](modify-existing-page.md)

[Lägga till en ny webbplatssida](add-new-page.md)

[Hantera SEO-metadata](manage-seo-metadata.md)

[Spara, förhandsgranska och publicera en sida](save-preview-publish-page.md)

[Utöka en produktsida](enrich-product-page.md)

[Utöka en kategorilandningssida](enrich-category-page.md)

[Kontrollera tillgängligheten för sidinnehåll](verify-accessibility.md)

[Skapa dynamiska näthandelssidor baserade på URL-parametrar](create-dynamic-pages.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
