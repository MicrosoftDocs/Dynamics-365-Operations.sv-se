---
title: Snabbvymodul
description: Denna artikel handlar om snabbvisningsmoduler och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e9066357fda4f5d91c547622ac64d8c4eef253ae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847585"
---
# <a name="quick-view-module"></a>Snabbvymodul

[!include [banner](includes/banner.md)]

Denna artikel handlar om snabbvisningsmoduler och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.

I snabbvisningsmodulen kan användarna snabbt visa produktinformation när de bläddrar bland produkter på en listsida och lägger till en eller flera produkter i kundvagnen från listsidan, detta utan att behöva gå till produktinformationssidan (PDP). Snabbvisningsmodulen ger en översikt över produktinformationen som användarna behöver för att fatta ett beslut om att "lägga till i kundvagnen". Den ger också en länk till PDP, så att användare kan visa ytterligare produktinformation och inköpsalternativ.

Snabbvisningsmodulen stöds av modulerna för [produktsamling](product-collection-module-overview.md) och [sökresultat](search-result-module.md).

> [!IMPORTANT]
> Snabbvisningsmodulen är tillgänglig i från och med Commerce-version 10.0.17.

Följande bild visar ett exempel på en snabbvisningsmodul på en produktlistsida.

![Exempel på en snabbvisningsmodul på en produktlistsida.](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a>Modulegenskaper

Snabbvisningsmodulen stöder delvis samma funktioner som modulen för inköpsruta. Därför liknar egenskaperna för en snabbvisningsmodul egenskaperna hos en modul för inköpsruta.

| Egenskap | Värden | beskrivning |
|----------------|--------|-------------|
| Rubriktagg | **H1**, **H2**, **H3**, **H4**, **H5** eller **H6** | Denna egenskap definierar rubriketiketten för produktrubriken. Om snabbvisningsmodulen finns högst upp på sidan ska den här egenskapen ställas in på **H1** för att uppfylla tillgänglighetsstandarder. |
| Tillåt anpassat pris | **Sant** eller **falskt** | Om egenskapen har angetts som **True** kan användaren ange ett eget pris. |
| Lägsta pris | Heltal | Denna egenskap kan bara användas om egenskapen **Tillåt anpassat pris** angetts som **True**. De definierar det lägsta pris som användaren kan ange (till exempel 1 USD). |
| Maxpris | Heltal | Denna egenskap kan bara användas om egenskapen **Tillåt anpassat pris** angetts som **True**. Den definierar det högsta pris som användaren kan ange (till exempel 1 000 USD). |

## <a name="commerce-site-builder-settings"></a>Inställningar för Commerce-webbplatsbyggaren

I precis som modulen för inköpsruta beaktar snabbvisningsmodulen inställningarna på **Webbplatsinställningar \> Tillägg \> Lägg till produkt i kundvagnen**. Inställningen **Navigera till kundvagnssidan** ignoreras emellertid eftersom detta är inkonsekvent med syftet med snabbvisningsmodulen, nämligen att låta användarna bläddra bland flera produkter på en listsida och lägga till dem i kundvagnen utan att lämna listsidan.

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a>Lägg till en modul för snabbvisning i en produktsamlingsmodul

En snabbvisningsmodul kan läggas till i modulerna för produktsamling och sökresultat.

Om du vill lägga till en snabbvisningsmodul i en produktsamlingsmodul i Commerce-webbplatsbyggaren följer du stegen nedan.

1. Gå till **Sidor** och välj sedan startsidan för Fabrikam-webbplatsen.
1. Gå till valfri modul för **Produktsamlingmodul** på startsidan, välj ellipsen (**...**) och välj sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler** väljer du modulen **Snabbvisning** och sedan **OK**.
1. I egenskapsfönstret i modulen **Snabbvisning** väljer du **Rubrik**. I dialogrutan **Rubrik** anger du fältet **Rubriknivå** som **H2** och väljer sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Modul för inköpsruta](add-buy-box.md)

[Produktsamlingsmodul](product-collection-module-overview.md)

[Sökresultatmodul](search-result-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
