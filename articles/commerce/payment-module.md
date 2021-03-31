---
title: Betalningsmodul
description: Det här avsnittet handlar om betalningsmodul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: d9c0956e30d413f5ae695cf75b06fb58711b2944
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222512"
---
# <a name="payment-module"></a>Betalningsmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om betalningsmodul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.

Betalningsmodulen låter kunder betala för beställningar med kredit- eller betalkort. Betalningsintegration för den här modulen tillhandahålls av Dynamics 365-betalningskoppling för Adyen. För mer information om hur du konfigurerar och konfigurerar betalningskontakten, se [Dynamics 365 betalningsanslutning för Adyen](dev-itpro/adyen-connector.md)  

Från och med Commerce version 10.0.14 har betalningsmodulen också integrerats med Dynamics 365-betalningsanslutningen för PayPal i syfte att ge kunderna möjlighet att betala för beställningar med hjälp av PayPal. För mer information om hur du konfigurerar och konfigurerar Dynamics 365-betalningsanslutningen för PayPal, se [Dynamics 365-betalningsanslutning för PayPal](paypal.md). 

## <a name="dynamics-365-payment-connector-for-adyen"></a>Dynamics 365-betalningskoppling för Adyen 

Modulen för betalning innehåller betalningsinformationen som betjänas via Adyen i en HTML-infogad ram (iframe). Modulen för betalning interagerar med Commerce Scale Unit för att hämta Adyen betalningsinformation. Som en del av Commerce Scale Unit-interaktionen kan betalningsmodulen tillåta att faktureringsadressinformation betjänas antingen i iframe via Adyen eller som en separat modul. I Fabrikam-temat aktiveras faktureringsadressen i en separat modul. Detta ger större flexibilitet eftersom adress raderna kan återges så att de liknar raderna i leveransadressen.

I betalningsmodulen kan också kunder som är inloggade spara sina betalningsuppgifter. Betalningsinformationen och fakturerings adressen sparas och hanteras via Adyen betalningskoppling.

Betalningsmodulen täcker alla orderavgifter som inte redan omfattas av förmånspoäng eller presentkort. Om summan för en order helt täcks av förmånspoäng eller presentkortskrediter, döljs betalningsmodulen och kunden kan placera ordern utan den.

Adyen betalningskontakt stöder också stark kundautentisering (SCA). En del av den Europeiska Unionens (EU) reviderade direktiv om betalningstjänster (PSD2) kräver att online-shoppare autentiseras utanför sin online-upplevelse när de använder en elektronisk betalningsmetod. I samband med kassaflödet omdirigeras kunderna till sin bankwebbplats – efter autentisering omdirigeras de tillbaka till kassaflödet för Commerce. I samband med denna omdirigering behålls den information som en kund har angett i samband med kassaflödet (t.ex. leveransadress, leveransalternativ, presentkortsinformation och lojalitetsinformation). Innan du kan aktivera funktionen för Adyen-betalningsanslutning måste betalningsanslutningen konfigureras för SCA i Commerce-administrationen. Mer information finns i [grundlig kundautentisering med hjälp av Adyen](adyen_redirect.md). Denna funktion aktiverades i Commerce version 10.0.12.

> [!NOTE]
> För Adyen -betalningskoppling kan modulen iFrame i modulen betalning bara återges om du lägger till Adyen-URL i din webbplatslista över tillåtna. Du slutför det här steget genom att lägga till direktiven **\*.adyen.com** till **child-src**, **connect-src**, **img-src**, **script-src** och **style-src** för säkerhetspolicyn för din webbplats. Mer information finns i [hantera säkerhetsprinciper för innehåll](manage-csp.md). 

Följande bild visar ett exempel på moduler för presentkort, lojalitet och Adyen-betalning på en kassasida.

![Exempel på moduler för presentkort, lojalitet och Adyen-betalningsmoduler på en kassasida](./media/ecommerce-payments.PNG)

## <a name="dynamics-365-payment-connector-for-paypal"></a>Dynamics 365-betalningsanslutning för PayPal

Från och med Commerce version 10.0.14 är betalningsmodulen även integrerad i Dynamics 365-betalningsanslutningen för PayPal. För mer information om hur du konfigurerar denna betalningsanslutning, se [Dynamics 365-betalningsanslutning för PayPal](paypal.md).
 
På kassasidan kan du ha både Adyen- och PayPal-anslutningarna konfigurerade. Betalningsmodulen har förbättrats med ytterligare egenskaper för att hjälpa till att identifiera vilken anslutning den ska arbeta med. För information, se modulegenskaperna för **Offerttyper som stöds** och **Är primär betalning** i följande tabell.
  
När betalningsmodulen är konfigurerad för att använda PayPal-betalningsanslutningen visas en PayPal-knapp på kassasidan. När den åberopas av kunden skapar betalningsmodulen en iframe som innehåller PayPal-information. Kunden kan logga in och ange sin PayPal-information inom denna iframe för att slutföra sin transaktion. När en kund väljer att betala via PayPal debiteras det återstående saldot på beställningen via PayPal.

PayPal-betalningsanslutningen kräver ingen faktureringsadressmodul eftersom all faktureringsrelaterad information hanteras av PayPal inom dess iframe. Modulerna för leveransadress och -alternativ krävs dock.

I bilden nedan visas ett exempel på två betalningsmoduler på en kassasida, en konfigurerad med Adyen-betalningsanslutningen och den andra med PayPal-betalningsanslutningen.
![Exempel på moduler för Adyen- respektive PayPal-betalning på en kassasida](./media/ecommerce-paypal.png)

I bilden nedan visas ett exempel på den PayPal-iframe som åberopas med hjälp av PayPal-knappen. 
![Exempel på Paypal-iframe på en kassasida](./media/ecommerce-paypal-iframe.png)

## <a name="payment-module-properties"></a>Egenskaper för betalningsmodul

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Rubrik | Rubriktext | En valfri rubrik för betalningsmodul. |
| Höjd på iframe. | Pixlar | Höjdpunkter iframe i bildpunkter. Höjden kan dock justeras efter behov. |
| Visa faktureringsadress | **Sant** eller **falskt** | Om den här egenskapen har värdet **True** kommer faktureringsadressen att betjänas av Adyen inuti den inbäddade modulen för iframe. Om denna har värdet **False** kommer faktureringsadressen inte att betjänas av Adyen, och en Commerce-användare måste konfigurera en modul för att visa faktureringsadressen på kassasidan. Detta fält påverkar inte PayPal-betalningsanslutningen, detta eftersom faktureringsadressen hanteras helt inom PayPal. |
| Åsidosättning av betalningsformat | Kod för överlappande formatmallar (CSS) | Eftersom betalningsmodulen finns i en iframe finns det en begränsad format kapacitet. Du kan formatera formateringen genom att använda den här egenskapen. Om du vill åsidosätta webbplatsformat måste du klistra in CSS-koden som egenskapensvärde. Webbplatsskaparen CSS åsidosätter och stilar gäller inte för den här modulen. |
|Betalningsmedelstyper som stöds| Sträng| Om flera betalningsanslutningar har konfigurerats bör du tillhandahålla den sträng för betalningsmedel som stöds enligt definitionen i konfigurationen för betalningsanslutning för Commerce-administration (se följande bild). Om denna är tom kommer den att återställas till Adyen-betalningsanslutningen. Lades till i Commerce version 10.0.14.|
|Är primär betalning|  **Sant** eller **falskt** | Om **True** kommer eventuella felmeddelanden att genereras via den primära betalningsanslutningen på kassasidan. Om både Adyen- och PayPal-betalningsanslutningarna har konfigurerats anger du Adyen som **True**, som lades till i Commerce version 10.0.14.|

I bilden nedan visas ett exempel på värdet **Offerttyper som stöds** angivet som "PayPal" i konfigurationen av betalningsanslutning i Commerce-administrationen.
![Exempel på offerttyper som stöds i Commerces-administrationen](./media/ecommerce-paymenttendertypes.png)

## <a name="billing-address"></a>Faktureringsadress

En faktureringsadressmodul kan användas på kassasidan om faktureringsadressraderna för Adyen-betalningsanslutning inte tillräckligt matchar utseendet på resten av webbplatsen. 

Om du vill använda en faktureringsadressmodul på kassasidan när betalningsmodulen integrerats med Adyen-betalningsanslutningen anger du egenskapen **Visa faktureringsadress** som **False** så att en dedikerad faktureringsadressmodul kan användas istället för standardadressen för Adyen. I det här fallet bör webbplatsdesignern inkludera en modul för faktureringsadress på kassasidan. Med Adyen-betalningsanslutningen kan du också använda leveransadressen som faktureringsadress för att minimera antalet steg för webbplatsanvändaren.

På samma sätt som hos betalningsmodulerna har en egenskap för **Offerttyper som stöds** lagts till i modulen för faktureringsadress i Commerce version 10.0.14. Värdet för den här egenskapen ska vara identiskt med det värde som angetts i betalningsmodulen, detta för att säkerställa att de fungerar tillsammans. För Adyen-betalningsanslutningen måste både betalningsmodulen och modulen för faktureringsadress lämna det här värdet tomt (standardläge). För PayPal-anslutningen behövs ingen särskild modul för faktureringsadress. För andra typer av betalningsanslutningar ska strängen tillhandahållas som konfigurerad i Commerce-administrationen.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Lägg till en betalningsmodul på en kassasida och ställa in de obligatoriska egenskaperna.

En betalningsmodul kan bara läggas till i en betalningsmodul. Mer information om hur du konfigurera en betalningsmodul för en kassasida, se [kassamodul](add-checkout-module.md).

Om både Adyen- och PayPal-betalningsanslutningar behövs lägger du till båda modulerna i betalningsavsnittet. Se till att egenskapsvärdet **Offerttyper som stöds** är konfigurerat för PayPal, och lämna det tomt för Adyen. Ställ också in egenskapen **Är primär betalning** som **True** för Adyen.

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för leveransadress](ship-address-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Informationsmodul för upphämtning](pickup-info-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Presentkortsmodul](add-giftcard.md)

[Dynamics 365-betalningskoppling för Adyen](dev-itpro/adyen-connector.md)

[Dynamics 365-betalningsanslutning för PayPal](paypal.md)

[Stark kundautentisering med Adyen](adyen_redirect.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]