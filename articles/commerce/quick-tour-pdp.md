---
title: Översikt över sidor med produktinformation
description: Det här ämnet innehåller en översikt över sidor för produktdetaljer (PDP) i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b0f50b4e7b78f4a5b9fe674a101476879923e10d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979838"
---
# <a name="product-details-pages-overview"></a>Översikt över sidor med produktinformation

[!include [banner](includes/banner.md)]

Det här ämnet innehåller en översikt över sidor för produktdetaljer (PDP) i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En PDP innehåller detaljerad information om en produkt och kunder kan välja produktalternativ som storlek, stil och färg. En PDP ska visa all produktinformation som en kund behöver för att fatta ett köpbeslut.

Illustrationen nedan visar ett exempel på en PDP.

![Exempel på en sida med produktinformation](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a>Moduler för sidhuvud och sidfot

Den övre delen av PDP har en rubrik som visar alla produktkategorier och andra sidor som återförsäljaren vill att kunderna ska bläddra i. Sidans nedre del har en sidfot som innehåller snabblänkar till olika ämnen som kan vara intressanta för kunderna.

## <a name="buy-box-module"></a>Modul för inköpsruta

Den viktigaste modulen på ett PDP är modulen för inköpsruta som visas som det första objektet i huvudavsnittet på sidan. En modul för inköpsruta innehåller viktig produktinformation, till exempel produktnamn, produktbeskrivning, produktpris, produktbilder och produktklassificeringar.

Med modulen inköpsruta kan kunden välja produktalternativ (t.ex. storlek, stil och färg) och lägga till produkten i vagnen. Kunden kan också köpa produkten online och välja den i en butik. Modulerna köpa online och hämta i butik använder integration med Bing Maps API:er (Application Programming Interfaces) för att hitta närliggande butiker eller butiker på en annan plats som kunden anger.

En modul för inköpsruta kräver ett produkt-ID. Detta ID hämtas från sidans kontext. Om en modul för inköpsruta läggs till på en sida där sidkontexten inte innehåller något produkt-ID, återges informationen inte på rätt sätt.

## <a name="product-specifications-module"></a>Modul för produktspecifikationer

Modulen för produktspecifikationer kan användas för att visa mer information om produkten. Dessa detaljer hämtas från produktattribut i handel. Modulen produktspecifikationer visar alla attribut där egenskapen **synlig** är inställd på **sant**. Det kräver ett produkt-ID för att hämta produktattribut.

## <a name="recommendations-module"></a>Rekommendationsmodul

Rekommendationsmodulen är en viktig modul på en PDP. Medan kunder bläddrar efter produkter, bör fler produktalternativ presenteras för dem, så att de kan hitta rätt produkter och göra inköp. Rekommendationer hjälper kunder att enkelt hitta relaterat innehåll och fortsätta att handla.

Det finns olika typer av rekommendationslistor:

- Listan **personer gillar också** baseras på maskinutbildning. Den använder transaktionshistorik för andra kunder för att ge rekommendationer. Den här listan genereras av rekommendationstjänsten och liknar listan "kunder som köpt detta har också köpt...". Ett produkt-ID krävs för att listan ska kunna skapas.
- En **relaterad** lista kan konfigureras för en produkt i Commerce. För till exempel en handväska i brunt läder kan flera handväskor som är läderbaserade eller utformade för resor konfigureras för den relaterade listan. Andra typer av relaterade listor, till exempel **tillbehör** och **Fler som den här**, kan också konfigureras i Commerce. Ett produkt-ID krävs för att listan ska kunna skapas. Om den läggs till på en startsida, där sidkontexten inte innehåller något produkt-ID, kommer listan att vara tom.
- Algoritmskapade rekommendationslistor, t.ex. **Trend**, **Bästsäljande** och **Ny** kan användas på PDP. Även om dessa listor kanske inte är direkt relaterade till produkten i PDP är de ett annat sätt att hjälpa kunderna att hitta produkter som kan vara intressanta för dem. Dessa typer av listor kräver inget produkt-ID. De är generiska listor som skapas baserat på köpmönster på webbplatsen.
- Redaktionella listor är manuellt granskade listor. En återförsäljare kan till exempel välja att manuellt granska listor över produkter som den vill visa.

## <a name="ratings-and-reviews-modules"></a>Moduler för omdömen och moduler

Tre moduler kan användas för att visa och lägga till recensioner:

- **Recensioner** – Den här modulen anger omdömen och recensioner visas omdömen och recensioner som andra kunder har gett. Kunder kan sortera och filtrera recensionerna. Den här modulen gör det också möjligt för kunder som eller som vill granska recensioner och rapportera problem.
- **Skriv recension** – i den här modulen kan kunderna skriva sina egna recensioner av en produkt.
- **Omdömeshistogram** – i den här modulen finns ett histogram över trender för omdömen för en produkt.

Mer information finns i [Översikt över omdömen och recensioner](ratings-reviews-overview.md).

## <a name="marketing-modules"></a>Marknadsföringsmoduler

Om marknadsföringsinnehållet är unikt för en viss produkt kan en marknadsföringsmodul läggas till i PDP. Du kan lägga till marknadsföringsmaterial i ett PDP genom att "berika" sidan. Mer information finns i [utöka en produktsida](enrich-product-page.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startsidan](quick-tour-home-page.md)

[Översikt över sidor för kundvagn och kassa](quick-tour-cart-checkout.md)

[Översikt över sidor för kontohantering](quick-tour-account-management.md)

[Utöka en produktdetaljsida](enrich-product-page.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]