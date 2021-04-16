---
title: Utöka en kategorilandningssida
description: I det här avsnittet beskrivs hur du berikar kategorisidor i Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5e18439fc0e91619cade33b83b87be0d5c4d1040
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799021"
---
# <a name="enrich-a-category-landing-page"></a>Utöka en kategorilandningssida

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du berikar kategorisidor i Dynamics 365 Commerce.

näthandel ger en standardsida för kategori landningssidor som används när kategoridata visas. En standardkategorisida innehåller obligatoriska element, t.ex. förfinare, kategoriserad produktplacering, sorteringsalternativ, en alternativ sammanfattning och sidbrytningskontroller. 

I stället för att använda standardkategorisidan kanske du vill använda en landningssida med "utökad" kategori som har mer innehåll och fler specifika element. Ett typiskt berikande kan innebära att man lägger till kategorispecifikt marknadsföringsinnehåll på kategorisidan. Det här innehållet kan omfatta produktplacering i flera kategorier för säljsyfte, redaktionella listor, bilder, videor och annan text. Du kan antingen ändra standardkategori sidan eller definiera en annan kategorisida för en viss kategori.

![Utöka en kategorilandningssida](./media/CategoryLandingPages.png)

I Commerce webbplatsskaparen innehåller sidan **produkter** en lista med kategorier från den kanal som har tilldelats webbplatsen. Om du har valt statusen **berikad** för en kategorisida har den kategorisidan berikats. I annat fall används standardkategorisidan och innehållet för kategorin. Du kan förhandsgranska både de berikade och icke-funktionella kategorisidorna för en kategori genom att markera kategorinamnet.

Om du vill utöka en kategorisida gör du följande.

1. På sidan **produkter** väljer du namnet på den kategori som du vill utöka kategorisidan för. Standardkategorisidan för den valda kategorin öppnas i sidredigeraren.
2. Välj **berika kategorisida**.
3. Välj en mall för den berikade kategorisidan. Om du bara gör mindre ändringar kan du välja standardkategorisidan. Du kan också välja en specifik mall för kategorisidan. När du väljer mallen öppnas sidredigeraren och den valda mallen används för att skapa en ny kategori sida för den valda kategorin. Sidan är utcheckad till dig och du kan nu göra dina ändringar.

> [!NOTE]
> Moduler som använder kategorispecifikationsdata använder data från den valda kategorin. Inställningarna för den mall som du väljer avgör vilka ändringar du kan göra.

## <a name="additional-resources"></a>Ytterligare resurser

[Ändra en befintlig webbplatssida](modify-existing-page.md)

[Lägga till en ny webbplatssida](add-new-page.md)

[Välj sidlayouter](select-page-layouts.md)

[Hantera SEO-metadata](manage-seo-metadata.md)

[Spara, förhandsgranska och publicera en sida](save-preview-publish-page.md)

[Utöka en produktsida](enrich-product-page.md)

[Kontrollera tillgängligheten för sidinnehåll](verify-accessibility.md)

[Skapa dynamiska näthandelssidor baserade på URL-parametrar](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
