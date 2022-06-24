---
title: Webbplatsväljarmodul
description: Denna artikel handlar om modulen för webbplatsväljare och beskriver hur du lägger till den på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: ef7753658f878fdf76c6a6beb82ce54e9c12e212
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884613"
---
# <a name="site-picker-module"></a>Webbplatsväljarmodul

[!include [banner](includes/banner.md)]

Denna artikel handlar om modulen för webbplatsväljare och beskriver hur du lägger till den på webbsidorna i Microsoft Dynamics 365 Commerce.

Om ett företag har olika webbplatser på olika marknader, regioner och språk, behöver webbplatsanvändarna ett enkelt sätt att växla mellan platserna och välja sin föredragna webbplats att handla på. I det här scenariot kan du använda modulen webbplatsväljare för att söka på flera webbplatser. En webbplatsväljare rekommenderas även när [geografisk detektering och omdirigering](geo-detection-redirection.md) har implementerats för din näthandelsplats, detta så att kunderna har möjlighet att åsidosätta den webbplatsinställning de anger via modulen [för lands-/regionsinställningar](country-region-picker-module.md). 

Modulen webbplatsväljare måste vara konfigurerad med en lista över platser (marknader, regioner eller språk) som webbplatsanvändarna kan bläddra i. I följande bild visas ett exempel på en modul för webbplatsväljare som finns i rubriken på en webbplatssida.

![Exempel på en modul för webbplatsväljare i sidhuvudet på en webbplatssida.](./media/ecommerce-sitepicker.PNG)

## <a name="site-picker-module-properties"></a>Egenskaper för modul för webbplatsväljare

| Egenskapsnamn | Värde                 | Beskrivning |
|---------------|-----------------------|-------------|
| Rubrik       | Text                  | Rubriken för modulen. |
| Webbplatsalternativ  | Namn, bild, URL      | Den här egenskapen anger ett namn, en länk till webbplatsens startsida och en valfri bild som ska visas för varje webbplats som ingår i modulen. Bilden kan vara en flagga eller en del representation av en marknad, region eller nationella inställningar. |

## <a name="add-a-site-picker-module-to-a-page"></a>Lägg till modulen för webbplatsväljare till en sida

Modulen webbplatsväljare kan läggas till i platsen **webbplatsväljare** i [huvudmodul](author-header-module.md). När modulen för webbplatsväljare har lagts till kan du definiera modulens rubrik och webbplatsalternativ. Vanligtvis finns en rubrikmodul i ett rubrikfragment som kan delas på näthandelssidor för en site. 

Följ de här stegen för att lägga till en webbplatsväljarmodul i en rubrikmodul.

1. I platsen för **Webbplatsväljare** i rubrikfragmentets rubrikmodul väljer du ellips (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler** lägger du till en **Webbplatsväljare**-modul och väljer **OK**.
1. I egenskapsfönstret **Webbplatsväljare** väljer du **Lägg till lista över webbplatsalternativ**. Ett redigerbart **Lista över webbplatsalternativ** visas.
1. Välj **Lista över webbplatsalternativ**. Dialogrutan **Lista över webbplatsalternativ** visas.
1. Under **Webbplatsens namn** anger du den namntext som ska visas i listrutan för webbplatsväljare.
1. Under **Omdirigerings-URL för webbplats** väljer du **Lägg till en länk**. Snabbmenyfönstret **Lägg till en länk** visas.
1. I snabbmenyfönstret **Lägg till en länk** väljer du **Anpassad sida** och väljer **Nästa**.
1. Från listan med webbplats-URL väljer du URL-adressen med den sökväg du skapade när du lägger till kanalen på webbplatsen (`www.adventure-works.com/fr-ca` till exempel) och väljer sedan **Använd**.
1. Välj **OK**.
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. Välj **Publicera** om du vill publicera sidan.

I följande exempel har modulen för webbplatsväljare lagts till på platsen för **webbplatsväljare** i en huvudmodul som finns i ett rubrikavsnitt med namnet **HeaderContainer**.

![Exempel på en modul för webbplatsväljare i rubrikavsnitt.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Rubrikmodul](author-header-module.md)

[Modul för navigeringssökväg](add-breadcrumb.md)

[Modul för navigeringsmeny](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
