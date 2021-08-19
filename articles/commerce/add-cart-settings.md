---
title: Tillämpa inställningar för att lägga till produkt i kundvagnen
description: Detta ämne handlar om inställningar för "Lägg till produkt i kundvagn" och beskriver hur du lägger till dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6299a1c815978ab9f748b6110980e673e1fbae927ed08a5e2e080f89ef063115
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712824"
---
# <a name="apply-add-product-to-cart-settings"></a>Tillämpa inställningar för att lägga till produkt i kundvagnen

[!include [banner](includes/banner.md)]

Detta ämne handlar om inställningar för **Lägg till produkt i kundvagn** och beskriver hur du lägger till dem i Microsoft Dynamics 365 Commerce.

Olika arbetsflöden stöds när en produkt läggs till i kundvagnen på en Dynamics 365 Commerce-näthandelsplats. Till exempel kan webbplatsanvändaren vidarebefordras till kundvagnssidan. Alternativt kan användaren vara kvar på den aktuella sidan men få ett meddelande som bekräftar att produkten har lagts till i vagnen.

Som ett stöd för de olika arbetsflödena finns ett fält för **Lägg till produkt i kundvagnen** via **Inställningar \> Tillägg** i Commerce-webbplatsbyggaren. Välj ett av följande inställningsalternativ om du vill implementera motsvarande arbetsflöde:

- **Navigera till kundvagnssidan** – När användare lägger till en artikel i kundvagnen skickas de till kundvagnssidan.
- **Visa meddelande** – När användare lägger till en artikel i kundvagnen får de ett bekräftelsemeddelande och kan fortsätta att bläddra på sidan för produktinformation (PDP).
- **Visa minivagn** – När användarna lägger till en artikel i kundvagnen visas innehållet i minivagnen. Användarna kan granska alla artiklar i kundvagnen, och de kan gå vidare till kassan om de är klara.
- **Visa meddelanden med hjälp av modulen Meddelanden** – När användarna lägger till en artikel i kundvagnen används meddelandemodulen för att visa ett bekräftelsemeddelande. Meddelandemodulen måste läggas till i sidhuvudet för att detta inställningsalternativet ska fungera.
- **Navigera inte till kundvagnssidan** – När användare lägger till en artikel i kundvagnen blir de kvar på den aktuella sidan.

I följande bild visas ett exempel på inställningarna för **Lägg till produkt i kundvagnen** i webbplatsskaparen.

![Exempel på inställningsalternativ för Lägg till produkt i kundvagnen i webbplatsskaparen](./media/AW_sitesettings.PNG)

> [!IMPORTANT]
> - Webbplatsinställningarna för **Lägg till produkt i kundvagn** är tillgängliga från och med Dynamics 365 Commerce-version 10.0.11. Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt. Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).
> - Inställningsalternativet **Visa minivagn** finns att tillgå från och med Dynamics 365 Commerce-version 10.0.20. Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt. Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

I följande bild visas ett exempel på ett bekräftelsemeddelande om "lades till i kundvagnen" på Fabrikams webbplats.

![Exempel på ett bekräftelsemeddelande om "lades till i kundvagnen" på Fabrikams webbplats](./media/ecommerce-addtocart-notifications.PNG)

I följande bild visas ett exempel på ett bekräftelsemeddelande om "lades till i kundvagnen" på Adventure Works webbplats.

![Exempel på ett bekräftelsemeddelande om "lades till i kundvagnen" på Adventure Works webbplats](./media/AW_minicart.PNG)

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Modul för inköpsruta](add-buy-box.md)

[Modul för butiksväljare](store-selector.md)
