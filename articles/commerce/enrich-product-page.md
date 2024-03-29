---
title: Utöka en produktsida
description: I denna artikel beskrivs hur du kan berika en produkt i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: f01dcc2518fe861339b4984522582ed3de7aa6ad
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282145"
---
# <a name="enrich-a-product-page"></a>Utöka en produktsida

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du kan berika en produkt i Microsoft Dynamics 365 Commerce.

Som standard använder webbplatsen en allmän sida för att visa produktdata. Den här sidan innehåller grundläggande information om produkten och de kontroller som krävs för att sälja den. Du kan dock komplettera den information som kommer från skalningsenhet för handel med ytterligare bilder eller text för en viss produkt. Denna process kallas för att hantera produktsidan.

I många fall vill du använda särskilda ytterligare innehåll för dina produkter. När du går till **Butik och handel** i utvecklingsverktyget visas en lista med produkter från den kanal som har tilldelats till webbplatsen. I den här listan visar kolumnen **berikad** om produktsidan för en produkt har berikats. Om en bockmarkering visas i kolumnen finns en berikad produktsida för produkten. Om ingen bockmarkering visas används produktens standardproduktsida och innehåll. Du kan förhandsgranska både de berikade och icke-berikade produktsidorna genom att markera produktnamnet i listan.

## <a name="enrich-a-product-page"></a>Utöka en produktsida

Om du vill utöka en produktsida följer du stegen nedan.

1. Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).
1. I navigeringsfönstret till vänster, välj **Produkter**.
1. Välj en produkt som inte har någon berikad produktsida.
1. I åtgärdsfönstret, välj **Berika produktsida**.
1. Välj **PDP-mall** och välj sedan **OK**.
1. I dispositionsträdet för sida till vänster expanderar du platsen **Huvud**.
1. Markera knappen med punkter (**...**) för platsen **Huvud** och välj sedan **Lägg till modul**.
1. Välj **Behållare 2** och välj sedan **OK**.
1. Markera knappen med punkter för **Behållare 2** och välj sedan **Lägg till modul**.
1. Välj **Funktion** och välj sedan **OK**.
1. I fönstret egenskaper till höger i fältet **oformaterad text** anger du den uppdaterade beskrivningen av produkten.
1. I fältet **Rubrik** anger du rubriktexten och väljer sedan **OK**.
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. I fältet **kommentarer** anger du **Berika en produkt** och sedan **OK**.
1. Välj **Förhandsgranska** om du vill förhandsgranska den berikade produktsidan. När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.
1. Markera **Publicera**.

## <a name="additional-resources"></a>Ytterligare resurser

[Ändra en befintlig webbplatssida](modify-existing-page.md)

[Lägga till en ny webbplatssida](add-new-page.md)

[Välj sidlayouter](select-page-layouts.md)

[Hantera SEO-metadata](manage-seo-metadata.md)

[Spara, förhandsgranska och publicera en sida](save-preview-publish-page.md)

[Utöka en kategorilandningssida](enrich-category-page.md)

[Kontrollera tillgängligheten för sidinnehåll](verify-accessibility.md)

[Skapa dynamiska näthandelssidor baserade på URL-parametrar](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
