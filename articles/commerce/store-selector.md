---
title: Modul för butiksväljare
description: Det här avsnittet handlar om modulen för butiksväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 460d05ca29d5b8da70a971a649d9edd786f7260d
ms.sourcegitcommit: 15c5ec742d648c5f3506d031a2ab6150dcbae348
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378218"
---
# <a name="store-selector-module"></a>Modul för butiksväljare

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om modulen för butiksväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En modul för butiksväljare används för kundscenariot "Köp online, hämta i butik" "(BOPIS). En lista visas med butiker där en produkt är tillgänglig för upphämtning, samt butikstimmar och produktlager för varje butik.

Modulen butiksväljare kräver en produkts kontext och en sökplats för att hitta butiker. I avsaknad av en sökplats är det standardadressen till kundens webbläsare, förutsatt att kunden godkänner det. Modulen har en inmatningsruta där kunden kan ange en plats (postnummer, ort och delstat) för att hitta butiker som finns i närheten.

Butiksväljarmodulen är integrerad med geokodnings-API för Bing Maps för att konvertera platsen till en latitud och longitud. En Bing Maps API-nyckel krävs och måste läggas till på sidan för delade Commerce-parametrar i Dynamics 365 Commerce.

Modulen butiksväljare kan läggas till i en modul för inköpsruta på sidan produktinformation (PDP) för att visa butiker där en produkt är tillgänglig för upphämtning. Den kan också läggas till i en vagnmodul. När du lägger till i en kundvagn visar modulen butiksväljare visas upphämtningsalternativ för varje vagnradartikel. Med anpassad kodning kan du dessutom lägga till modulen i andra sidor eller moduler via tillägg och anpassningar.

För att BOPIS-scenariot ska fungera bör produkter konfigureras med leveransläget "kundupphämtning". Annars visas modulen inte på respektive sida. Mer information om hur du konfigurerar leveransläget finns i [ställa in leveransmetod](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Följande bild visar ett exempel på en modul för butiksväljare som används på ett PDP.

![Exempel på en modul för butiksväljare](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a>Användning av modul för butiksväljare i e-handel

- En modul för butiksväljare kan användas för sidan produktinformation (PDP) för att hitta butiker i närheten där en produkt är tillgänglig för upphämtning.
- En modul för butiksväljare kan användas på en kundvagnssida för att hitta butiker i närheten där en produkt i kundvagnen är tillgänglig för upphämtning.

## <a name="store-selector-module-properties"></a>Egenskaper för modul för butiksväljare

| Egenskapsnamn             | Värde                 | beskrivning |
|---------------------------|-----------------------|-------------|
| Sök radie | Antal | Definierar sökradien för butiker, i mil. Om inget värde anges används standardsökradien 50 mil.|
|Användarvillkor | URL    |  Det krävs en URL för tjänstvillkors för Bing Maps-tjänsten. |

## <a name="add-a-store-selector-module-to-a-page"></a>Lägg till modulen för butiksväljare till en sida

En modulen för butiksväljare behöver kontexten för en produkt, så den kan bara användas i köp- och vagnmoduler. Modulen för butiksväljare fungerar inte utanför dessa moduler.

- Mer information om hur du lägger till en modulen för butiksväljare i en modul för inköpsruta finns i [modul för inköpsruta](add-buy-box.md). 
- Mer information om hur du lägger till en modulen för butiksväljare i en vagnmodul i [vagnmodul](add-cart-module.md)

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Guidad visning av PDP](quick-tour-pdp.md)

[Guidad visning av kundvagn och kassa](quick-tour-cart-checkout.md)

[Ställ in leveranssätt](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Hantera Bing Maps för din organisation](dev-itpro/manage-bing-maps.md)
