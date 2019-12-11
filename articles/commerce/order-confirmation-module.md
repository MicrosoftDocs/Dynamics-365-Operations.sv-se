---
title: Orderbekräftelsemodulen
description: Det här avsnittet handlar om orderbekräftelsemoduler och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698336"
---
# <a name="order-confirmation-module"></a>Orderbekräftelsemodulen

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet handlar om orderbekräftelsemoduler och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En orderbekräftelsemodul används för att visa ett bekräftelsemeddelande på en orderbekräftelsesida när en order har placerats. I orderbekräftelsemodulen visas orderbekräftelsenumret och den kund-e-postadress som tillhandahölls i kassan.

När en order placeras i kassan skickas orderbekräftelsenumret och kundens e-postadress till sidan orderbekräftelse som en frågesträng i sidans URL. Orderbekräftelsemodulen tar emot den här informationen och återger orderstatusen på orderbekräftelsesidan. Orderbekräftelsemodulen kräver den här sidkontexten för att ange orderns status.

## <a name="order-confirmation-module-properties"></a>Egenskaper för orderbekräftelsemodul

| Egenskapsnamn | Värden | Beskrivning |
|---------------|--------|-------------|
| Rubrik       | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | Orderbekräftelsemodulen kan ha en rubrik. Som standard används rubriktaggen **H2** för rubriken. Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven. |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a>Moduler som kan användas på en sida för orderbekräftelsemodul 

- **Rekommendationer** – modulen rekommendationer kan placeras på sidan orderbekräftelse för att föreslå andra produkter till kunden.
- **Marknadsföring** – marknadsföringsmodulen kan lägga till marknadsföringsinnehåll på sidan orderbekräftelse.

## <a name="create-an-order-confirmation-page-module"></a>Skapa en sida för modul för orderbekräftelse

1. Skapa en sidmall som har namnet **orderbekräftelsemall**.
1. Lägg till platsen **Huvud** på standardsida, lägg till orderbekräftelsemodul.
1. Lägg till en rekommendationsmodul i orderbekräftelsemodulen.
1. Spara och förhandsgranska mallen. Modulen för orderbekräftelse ska inte återges eftersom den kräver en kontext för orderbekräftelsenumret.
1. Checka in mallen och publicera den.
1. Använd den mall för orderbekräftelse som du just skapade för att skapa en sida med namnet **sida för orderbekräftelse**.
1. Lägg till standardsidan i siddispositionen.
1. Lägg till platsen **rubrik**, lägg till ett rubrikavsnitt.
1. Lägg till platsen **sidfot**, lägg till ett sidfotavsnitt.
1. På platsen **Huvud**, lägg till orderbekräftelsemodul.
1. I egenskapsfönstret för orderbekräftelsemodulen, lägg till **Orderbekräftelse**.
1. Lägg till en rekommendationsmodul under orderbekräftelsesmodulen och konfigurera den så att den använder inställningarna **Ny** och **Bästsäljande**.
1. Spara och förhandsgranska sidan, checka in den och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Behållaremodul](add-container-module.md)

[Köp en boxmodul](add-buy-box.md)

[Vagnmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Rubrikmodul](author-header-module.md)

[Sidfotmodul](author-footer-module.md)
