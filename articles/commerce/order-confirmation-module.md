---
title: Orderinformationsmodul
description: Det här avsnittet handlar om orderinformationsmoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026027"
---
# <a name="order-details-module"></a>Orderinformationsmodul


[!include [banner](includes/banner.md)]

Det här avsnittet handlar om orderinformationsmoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Orderinformationsmodul används för att visa bekräftelseinformationen när en order har placerats. Det visar order bekräftelse-ID, orderns kontaktinformation och annan orderinformation, till exempel de artiklar som har köpts, betalningsinformation och leveransmetoden.

## <a name="order-confirmation-module-properties"></a>Egenskaper för orderbekräftelsemodul

| Egenskapsnamn  | Värden | Beskrivning |
|----------------|--------|-------------|
| Rubrik        | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | Orderbekräftelsemodulen kan ha en rubrik. Som standard används rubriktaggen **H2** för rubriken. Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven. |
| Kontaktnummer | Text | Ett kontaktnummer kan anges för frågor som är relaterade till order. |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a>Moduler som kan användas på en sida för orderinformation

När du skapar en sida för orderinformation kan du lägga till andra relevanta moduler utöver orderinformationsmodulen. Nedan följer några exempel:

- **Rekommendationsmodul** – modulen rekommendationer kan läggs till på sidan för orderinformation för att föreslå andra produkter till kunden.
- **Marknadsföringsmoduler** – valfri marknadsföringsmodul kan läggas till på sidan orderinformation om du vill visa marknadsföringsinnehåll.

## <a name="create-an-order-details-page-module"></a>Skapa en sida för orderinformationsmodul

1. Skapa en sidmall som har namnet **orderinformationsmall**.
1. Lägg till platsen **Huvud** på standardsida, lägg till orderinformationsmodul.
1. Lägg till en rekommendationsmodul i orderinformationsmodulen.
1. Spara och förhandsgranska mallen. Orderinformationsmodulen kommer inte återges eftersom den kräver en kontext för orderbekräftelsenumret.
1. Avsluta redigeringen i mallen och publicera den.
1. Använd den orderinformationsmall som du just skapade för att skapa en sida med namnet **sida för orderinformation**.
1. Lägg till standardsidan i siddispositionen.
1. Lägg till platsen **rubrik**, lägg till ett rubrikavsnitt.
1. Lägg till platsen **sidfot**, lägg till ett sidfotavsnitt.
1. På platsen **Huvud**, lägg till orderinformationsmodul.
1. I egenskapsfönstret för orderinformationsmodulen, lägg till **orderinformation**.
1. Lägg till en rekommendationsmodul under orderinformationsmodulen och konfigurera den så att den använder inställningarna **Ny** och **Bästsäljande**.
1. Spara och förhandsgranska sidan.
1. Avsluta redigeringen av sidan och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Behållaremodul](add-container-module.md)

[Köp en boxmodul](add-buy-box.md)

[Vagnmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Rubrikmodul](author-header-module.md)

[Sidfotmodul](author-footer-module.md)
