---
title: Utöka en kategorilandningssida
description: I det här avsnittet beskrivs hur du berikar kategorisidor i Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ca31ec7d2eee7d2b0c863506338341a870ff07ee
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269853"
---
# <a name="enrich-a-category-landing-page"></a>Utöka en kategorilandningssida


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du berikar kategorisidor i Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

E-handel ger en standardsida för kategori landningssidor som används när kategoridata visas. En standardkategorisida innehåller obligatoriska element, t.ex. förfinare, kategoriserad produktplacering, sorteringsalternativ, en alternativ sammanfattning och sidbrytningskontroller. 

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
