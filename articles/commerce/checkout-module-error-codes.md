---
title: Felreferenskoder för utcheckningsmodul
description: I den här artikeln beskrivs felreferenskoderna för utcheckningsmodulen som visas i användarinriktade felmeddelanden i Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 952cb932522b4e0bb91be985e4f8974cb6cd8bc0
ms.sourcegitcommit: 435e69160dbd7f9c61b37ac4440285a5df144622
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2022
ms.locfileid: "9728256"
---
# <a name="checkout-module-error-reference-codes"></a>Felreferenskoder för utcheckningsmodul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

I den här artikeln beskrivs felkoderna för utcheckningsmodulen som visas i användarinriktade felmeddelanden i Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce introducerade standardiserade felreferenser som ska inkluderas i onlinekanalutcheckningsfel som presenteras för onlinekunder. I Commerce version 10.0.31 och senare innehåller felmeddelanden i utcheckningsmodulen felkoder och visar inte onödiga information för onlinekunden. Felkoderna refererar till fel som finns detaljerade i den här artikeln.

Registret i den här artikeln innehåller följande information, beroende på vilket fel som uppstår:

- En beskrivning av villkoret som orsakade felet eller ytterligare information
- Information som ska beaktas i miljön eller i konfigurationer för betalningskoppling
- Information som kan refereras i ett supportärende om ytterligare hjälp krävs

## <a name="prerequisites"></a>Förutsättningar

För att aktivera kassamodulens felreferenskoder som anges nedan, i webbplatsbyggaren för din webbplats, gå till **Webbplatsinställningar \> Tillägg** och i avsnittet **Kundvagn och kassa** väljer du **Aktivera förbättrad onlinekanal felvisningsmeddelande**. 

## <a name="checkout-module-error-reference-codes"></a>Felreferenskoder för utcheckningsmodul

Använd följande tabell om du vill få mer information om felkodsreferenser som tillhandahålls av kunder eller upplevs i onlinebutiken. Rulla till höger om du vill visa kolumnen **Felbeskrivning**.

| Felkod | Dynamics-korrelerad felkod | Felbeskrivning |
| ---------- | ------------------------------ | ----------------- |
| CCR001     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardTypeMissingOrNotSupported | Betalningen kunde inte auktoriseras. Korttyp-ID i **TokenizedPaymentCard** saknas eller så stöds inte tillhandahållet korttyp-ID. |
| CCR002     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePayment | Nekat. Betalningen kunde inte auktoriseras. |
| CCR003     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardAdditionalContextRequired | Betalningen kunde inte auktoriseras. Ytterligare information krävs från kunden |
| CCR004     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToRetrieveCardPaymentAcceptResult | Något gick fel. Det gick inte att få fram ett godkänt resultat för kortbetalningen. Försök igen eller kontakta systemadministratören. |
| CCR005     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentRequiresMerchantProperties | Det går inte att göra betalningen på grund av att det saknas betalningsegenskaper för handlaren. Kontakta systemadministratören. |
| CCR006     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidPaymentRequest | Det gick inte att hämta betalningsmedel för åtgärden. Kontrollera betalningsmetodinställningarna för den valda betalningsmedelstypen. |
| CCR007     | Microsoft\_Dynamics\_Commerce\_Runtime\_MultipleCustomerAccountPaymentsNotAllowed | En kundkontobetalning har redan tillämpats. Enbart en betalning tillåts per transaktion. |
| CCR008     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountLimitSignDifferentFromAmountDue | Kundkontogränsen skiljer sig från beloppet som förfaller. Försök med en annan betalningsmetod eller kontakta kundtjänst om du vill ha hjälp. |
| CCR009     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsTotalAmountForCarryOutAndReturnItems | Kundkontobetalningen överskrider det totala antalet förfallna artiklar i listan. Försök igen senare eller kontakta kundsupport för hjälp. |
| CCR010     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentUsingUnauthorizedAccount | Kundkontobetalning kräver ett eget konto eller matchande fakturakonto på en betalningsmedelsrad. |
| CCR011     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsCustomerAccountFloorLimit | Det går just nu inte att bearbeta en kundkontobetalning – värdet för golvgränsen överskrids. |
| CCR012     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentForCustomerWithoutAllowOnAccount | Den här kunden har inte rätt att betala à conto. |
| CCR013     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToCancelPayment | Något gick fel. Betalningen kunde inte annulleras. Försök igen. |
| CCR014     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToReadCardTokenInfo | Ett fel uppstod när behandlingen för bearbetades. Försök igen senare. |
| CCR015     | Microsoft\_Dynamics\_Commerce\_Runtime\_NotEnoughRewardPoints | Förmånsbetalningsbeloppet överstiger det tillåtna beloppet för det här förmånskortet i den aktuella transaktionen. |
| CCR016     | Microsoft\_Dynamics\_Commerce\_Runtime\_RefundAmountMoreThanAllowed | Förmånsåterbetalningsbeloppet överstiger det tillåtna beloppet för det här förmånskortet i den aktuella transaktionen. |
| CCR017     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidLoyaltyCardNumber | Det gick inte att hitta förmånskortnumret. Aktivera antingen förmånskortnumret eller ange ett annat förmånskortnumret och försök sedan igen. |
| CCR018     | Microsoft\_Dynamics\_Commerce\_Runtime\_BlockedLoyaltyCard | Förmånskortnumret är inte tillgängligt. Ange ett annat kortnummer och försök sedan igen. |
| CCR019     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoTenderLoyaltyCard | Med det här förmånskortet är det inte möjligt att lösa in förmånspoäng för den här transaktionen. |
| CCR020     | Microsoft\_Dynamics\_Commerce\_Runtime\_GiftCardCurrencyMismatch | Presentkortsnumret påträffade ett fel. Försök med en annan presentkort eller kontakta kundtjänst om du vill ha hjälp. |
| CCR021     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAmountExceedsGiftBalance | Beloppet överstiger saldot på presentkortet. Ange ett annat belopp och försök sedan igen. |
| CCR022     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoMoreThanOneLoyaltyTender | Transaktionen får inte innehålla fler än en förmånsbetalningsrad. |
| CCR023     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAlreadyVoided | Betalningsinformationen saknar information eller är felaktig. Verifiera betalningsinformationen och försök sedan igen. |
| CCR024     | Microsoft\_Dynamics\_Commerce\_Runtime\_FraudRisk | Beställningen kan inte behandlas för närvarande. Försök igen senare. |
| CCR025     | Tidsgräns för klientdel för utcheckning av API | Klientdelåtgärden har en tidsgräns. Bekräfta om ordern har bearbetats i Dynamics 365 Commerce headquarters. |
| CCR026     | Ursprungligt auktoriserat belopp har ändrats | Orderbeloppet har ändrats från det ursprungliga auktoriseringsbeloppet som bearbetas med betalningsgatewayen. Detta kan bero på att en tidpunkt har gått ut på en kupong, ett erbjudande eller en försäljning. |
| CCR027     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidCartVersion | Ett fel uppstod när behandlingen för bearbetades. Referensen som tillhandahålls till vagn-API:t har en annan referens än förväntat (med hänsyn till potentiella inkonsekvenser under utcheckningsprocessen). |
| CCR028     | Microsoft\_Dynamics\_Commerce\_Runtime\_MissingRequiredCartTenderLines | Den betalningsmetod som försökts har stött på ett fel. Kontakta supporten om du vill granska dina kontoinställningar eller försöka igen med en annan betalningsmetod. |

## <a name="additional-resources"></a>Ytterligare resurser

[Vanliga frågor om betalningar](dev-itpro/payments-retail.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)
