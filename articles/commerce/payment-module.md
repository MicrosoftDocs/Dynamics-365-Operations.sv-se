---
title: Betalningsmodul
description: Det här avsnittet handlar om betalningsmodul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 4267391edaf70ec645933b2c5c08a72735f52894
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818336"
---
# <a name="payment-module"></a>Betalningsmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om betalningsmodul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Betalningsmodulen låter kunder betala för beställningar med kredit- eller betalkort. Betalningsintegration för den här modulen tillhandahålls av Dynamics 365-betalningskoppling för Adyen. För mer information om hur du konfigurerar och konfigurerar betalningskontakten, se [Dynamics 365 betalningsanslutning för Adyen](dev-itpro/adyen-connector.md)

Modulen för betalning innehåller betalningsinformationen som betjänas via Adyen i en HTML-infogad ram (iframe). Modulen för betalning interagerar med Commerce Scale Unit för att hämta Adyen betalningsinformation. Som en del av Commerce Scale Unit interaktionen kan betalningsmodulen tillåta att faktureringsadressinformation betjänas antingen i iframe eller som en separat modul. I temat Fabrikam visas faktureringsadressen i en separat modul. Detta ger större flexibilitet eftersom adress raderna kan återges så att de liknar raderna i leveransadressen.

I betalningsmodulen kan också kunder som är inloggade spara sina betalningsuppgifter. Betalningsinformationen och fakturerings adressen sparas och hanteras via Adyen betalningskoppling.

Betalningsmodulen täcker alla orderavgifter som inte redan omfattas av förmånspoäng eller presentkort. Om summan för en order helt täcks av förmånspoäng eller presentkortskrediter, döljs betalningsmodulen och kunden kan placera ordern utan den.

Adyen betalningskontakt stöder också stark kundautentisering (SCA). En del av Europeiska unionen (EU) direktiv om betalningstjänster 2.0 (PSD 2.0) kräver att online-shoppare autentiseras utanför deras online-erfarenhet när de använder en elektronisk betalningsmetod. Under kassaflödet omdirigeras kunderna till sin banks webbplats. Efter autentiseringen omdirigeras de tillbaka till Commerce-kassaflödet. Under denna omdirigering behålls den information som en kunden registrerats i kassaflödet (t.ex. leveransadress, leveransalternativ, presentkortsinformation och lojalitetsinformation). Innan du kan aktivera den här funktionen måste betalningskopplingen konfigureras för SCA i Commerce-administration. Mer information finns i [grundlig kundautentisering med hjälp av Adyen](adyen_redirect.md).

Följande bild visar ett exempel på moduler för presentkorts-, förmåns- och betalningsmoduler på en kassasida.

![Exempel på moduler för presentkorts-, förmåns- och betalningsmoduler på en kassasida](./media/ecommerce-payments.PNG)

## <a name="payment-module-properties"></a>Egenskaper för betalningsmodul

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Rubrik | Rubriktext | En valfri rubrik för betalningsmodul. |
| Höjd på iframe. | Pixlar | Höjdpunkter iframe i bildpunkter. Höjden kan dock justeras efter behov. |
| Visa faktureringsadress | **Sant** eller **falskt** | Om den här egenskapen har värdet **True** kommer faktureringsadressen att betjänas av Adyen inuti den inbäddade modulen för iframe. Om den har värdet **False** faktureringsadressen inte att betjänas av Adyen och en Commerce-användare måste konfigurera en modul för att visa faktureringsadressen på kassasidan. |
| Åsidosättning av betalningsformat | Kod för överlappande formatmallar (CSS) | Eftersom betalningsmodulen finns i en iframe finns det en begränsad format kapacitet. Du kan formatera formateringen genom att använda den här egenskapen. Om du vill åsidosätta webbplatsformat måste du klistra in CSS-koden som egenskapensvärde. Webbplatsskaparen CSS åsidosätter och stilar gäller inte för den här modulen. |

## <a name="billing-address"></a>Faktureringsadress

Betalningsmodulen erbjuder kunder en faktureringsadress för sina betalningsuppgifter. De kan också använda sina leveransadresser som faktureringsadress, för att göra kassaflödet enklare och snabbare. Om egenskapen **Visa faktureringsadress** är inställd på **False** ska betalningsmodulen konfigureras på betalningssidan.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Lägg till en betalningsmodul på en kassasida och ställa in de obligatoriska egenskaperna.

En betalningsmodul kan bara läggas till i en betalningsmodul. Mer information om hur du konfigurera en betalningsmodul för en kassasida, se [kassamodul](add-checkout-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för leveransadress](ship-address-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Presentkortsmodul](add-giftcard.md)

[Dynamics 365-betalningskoppling för Adyen](dev-itpro/adyen-connector.md)

[Stark kundautentisering med Adyen](adyen_redirect.md)
