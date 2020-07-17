---
title: Översikt över sidor för kundvagn och kassa
description: Det här ämnet innehåller en översikt över sidor för kundvagn och kassa i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c879b90cf49dcab9cf069e4f3613602bd6673aa9
ms.sourcegitcommit: ce397c2759f642c595e30fef58a770b50360b2bd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527581"
---
# <a name="cart-and-checkout-pages-overview"></a>Översikt över sidor för kundvagn och kassa

[!include [banner](includes/banner.md)]

Det här ämnet innehåller en översikt över sidor för kundvagn och kassa i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

På sidan kundvagn på en näthandelsplats visas alla artiklar som kunden har lagt till i vagnen. Sidan kundvagn skapas med hjälp av modulen kundvagn. En kundvagnsmodul är en behållare som används för att vara värd för alla moduler som krävs för att visa upp artiklar i vagnen. I kundvagnsmodulen kan även använda andra moduler för att visa ordersammanfattningen och eventuella kampanjkoder som har tillämpats på kundordern.

På kassasida in en näthandelsplats visas ett steg-för-steg-flöde som kunderna följer för att ange all information som krävs för att göra en beställning. En kassamodul kan innehålla moduler som hanterar leveransadress, leveransmetoder, faktureringsinformation, ordersammanfattning och annan information som hör till en kundorder.

## <a name="cart-page"></a>Kundvagnssida

Kundvagnssidan fungerar som shoppingväskor och innehåller alla artiklar som har lagts till i vagnen.

Följande illustration visar ett exempel på en kundvagnssida som har skapats med hjälp av online-startpaketet och temat "Fabrikam".

![Exempel på en kundvagnssida](./media/cart2.PNG)

Huvudsakliga materialet på kundvagnssidan visar alla artiklar som kunden har lagt till i vagnen. Alla tillämpliga rabatter visas. Rabatterna inkluderar komplexa rabatter. Exempel på detta är "Köp 3 artiklar och få 10 % rabatt" eller "Köp en flaska och en ryggsäck för att få 10 % rabatt". Modulen ordersammanfattning visar det belopp som förfaller efter rabatt, leverans, moms och så vidare. Det finns också en modul för kampanjkod som gör att kunden kan använda eller ta bort kampanjkoder.

En kund kan handla anonymt eller som en inloggad användare. Om en kund är inloggad behålls artiklar i kundvagnen mellan sessionerna. På så sätt kan kunden fortsätta att handla från flera enheter.

Från kundvagnen kan kunden fortsätta till kassan. En kund kan initiera kassan som en gästanvändare eller som en inloggad användare.

Information om hur du redigerar en kundvagnssida finns i [lägga till en kundvagnsmodul på en sida](add-cart-module.md).

## <a name="checkout-page"></a>Kassasida

Kassasidan anger var kunden anger den information som behövs för att göra en beställning.

Följande illustration visar ett exempel på kassasidan som har skapats med hjälp av online startpaketet.

![Exempel på en kassasida](./media/Checkout.PNG)

Huvuddelen av kassasidan är där all orderinformation samlas in. Informationen omfattar leveransadress, leveransalternativ och betalningsinformation. Kassan har ett steg-för-steg-flöde, eftersom informationen måste anges i en specifik order för att kunna bearbetas. Leveransadressen måste t.ex. anges innan leveranskostnaderna kan beräknas och betalningen kan godkännas.

### <a name="shipping-address"></a>Leveransadress

En leveransadress måste anges om artiklar måste levereras. Formatet på leveransadresser för varje språkversion kan konfigureras i Dynamics 365 Commerce. Om till exempel artiklarna ska levereras till USA måste leveransadressen innehålla gatuadress, region och postnummer. En del grundläggande verifiering sker för leverans adressfält, t.ex. validering av alfanumeriska tecken, maximal längd och siffror. Även om giltigheten för själva adressen inte har verifierats kan den här verifieringen utföras med hjälp av anpassade tjänster från tredje part.

Leveransadressen används för alla artiklar i vagnen som alternativet "leverera" har valts för. Om du använder det kassaflöde som finns i online startpaketet kan enskilda kundvagnsartiklar inte levereras till olika adresser. Om du behöver den här funktionen kan den implementeras genom anpassningar av modulerna för utcheckning.

När leveransadressen har angetts visas de leveransmetoder som är tillgängliga från Dynamics 365 Commerce onlinebutiken. Leveransmetoderna och adresserna som stöds kan konfigureras i handel.

### <a name="payment"></a>Betalning

Nästa steg i kassaflödet är betalning. I e-handel kan flera betalningsmetoder användas för att placera order, t.ex. kreditkort, presentkort och förmånspoäng. En kombination av dessa betalningsmetoder kan också användas. Beroende på vilka betalningsmetoder som används kan ytterligare information krävas. En kreditkortsbetalning kräver t.ex. en faktureringsadress. Kreditkortsbetalningar bearbetas med hjälp av Adyen betalningskoppling.

#### <a name="loyalty-points"></a>Bonuspoäng

Under kassaflödet kan en kund som är medlem i ett förmånsprogram och som har periodiserade förmånspoäng lösa in förmånspoäng för en order. Modulen förmånspoäng visas bara om kunden har ett befintligt förmånsmedlemsskap. För icke-medlemmar och gästanvändare är modulen dold.

#### <a name="gift-cards"></a>Presentkort

Online startpaketet ska lösa in sina interna presentkort för en beställning. Om du vill använda ett internt presentkort måste kunden vara inloggad. Om du vill ha ytterligare säkerhet rekommenderar vi att du anpassar flödet med hjälp av en PIN-kod (personal Identification Number) för interna presentkort.

### <a name="signed-in-and-guest-users"></a>Inloggade och gästanvändare

En kund kan slutföra utcheckningsprocessen som en gästanvändare eller som en inloggad användare. Om kunden loggar in hämtas automatiskt kontoinformation som t.ex. sparade leveransadresser och sparade kreditkortsuppgifter.

### <a name="order-summary"></a>Orderöversikt

Kassan visar en sammanfattning av radartiklarna i kundvagnen, så att kunden kan verifiera ordern innan han eller hon placerar den. Radartiklarna kan inte redigeras under kassaflödet. En länk till kundvagnen tillhandahålls dock om användaren vill gå tillbaka och redigerar radartiklarna.

När kunden har angett leverans- och faktureringsinformation, visar ordersammanfattningen beloppet som förfaller efter förmånspoäng, presentkort och andra betalningar som har tillämpats.

### <a name="order-confirmation-and-email"></a>E-postmeddelande och orderbekräftelse

När kunden beställer en order lämnas ett bekräftelsenummer. Vid denna tidpunkt har betalningen auktoriserats men inte debiterats. Betalningen debiteras först när ordern är uppfylld (dvs. när den antingen har levererats eller hämtats).

När en order har skapats skickas en orderbekräftelse via e-post till kunden.

Mer information om hur du redigerar en kassasida finns i [lägga till en kassamodul på en sida](add-checkout-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startsidan](quick-tour-home-page.md)

[Översikt över sidor med produktinformation](quick-tour-pdp.md)

[Översikt över sidor för kontohantering](quick-tour-account-management.md)
