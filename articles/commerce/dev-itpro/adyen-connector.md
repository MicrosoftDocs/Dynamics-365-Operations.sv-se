---
title: Dynamics 365 Payment Connector för Adyen – översikt
description: Den här artikeln innehåller en översikt över Microsoft Dynamics 365 Payment Connector för Adyen.
author: rassadi
ms.date: 11/16/2022
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2019-01-01
ms.openlocfilehash: 58d88e023b73ce19331bd6f54644a62d8f6f35af
ms.sourcegitcommit: 3aa3dedc3123cb079614762e2718841c2f7d7d35
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/30/2022
ms.locfileid: "9812097"
---
# <a name="dynamics-365-payment-connector-for-adyen-overview"></a>Dynamics 365 Payment Connector för Adyen – översikt

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller en översikt över Microsoft Dynamics 365 Payment Connector för Adyen och innehåller en omfattande lista över funktioner och funktioner som stöds. Relaterade artiklar täcker Adyen inloggning, konfiguration av kontakten, vanliga frågor och felsökningsvägledning för vissa vanliga problem.

## <a name="key-terms"></a>Nyckeltermer

| Villkor | Beskrivning |
|---|---|
| Betalningskoppling | Ett tillägg som underlättar kommunikationen mellan Microsoft Dynamics 365 Commerce (och associerade komponenter) och en betalningstjänst. Anslutningen som beskrivs i den här artikeln implementerades med hjälp av standard-SDK (Software Development Kit). |
| Kortet är tillgängligt | Refererar till betalningstransaktioner där ett fysiskt kort presenteras och används på ett anslutningsprogram till betalningsterminal som är ansluten till Dynamics 365 Point of Sale. |
| Kortet är inte tillgängligt | Refererar till betalningstransaktioner där ett fysiskt kort inte finns, till exempel e-handel eller kundtjänstscenarier. I dessa scenarier skrivs den betalningsrelaterade informationen in manuellt antingen på en e-handelswebbplats, ett kundtjänstflöde eller på försäljningsstället eller betalterminalen. |

## <a name="supported-features-functionality-versions-and-terminals"></a>Funktioner som stöds, funktioner, versioner och terminaler

I medföljande Dynamics 365 Payment Connector för Adyen används standardbetalnings-SDK. Därför har den inga speciella funktioner som inte även kan användas för andra betalningsanslutningar.

### <a name="supported-versions"></a>Versioner som stöds

#### <a name="microsoft-dynamics-365-supported-versions"></a>Microsoft Dynamics 365 versioner som stöds
Den första partens medföljande Dynamics 365 Payment Connector för Adyen stöds i Microsoft Dynamics 365 Finance version 8.1.3 (januari 2019) eller senare och i Microsoft Dynamics 365 Retail version 8.1.3 eller senare. Tredje parter kan dock fortfarande utveckla andra betalningsanslutningar för Adyen för tidigare versioner av Microsoft Dynamics 365.

#### <a name="supported-adyen-firmware-versions"></a>Stöds av Adyen versioner av inbyggd programvara

Listan nedan beskriver de minsta och högsta antal Adyen versioner av inbyggda programvara som stöds för varje version av Microsoft Dynamics 365 Retail POS.

---

# <a name="10025"></a>[10.0.25](#tab/10-0-25)
### <a name="dynamics-365-retail-pos-version-10025"></a>Dynamics 365 Retail POS version 10.0.25
| Minsta Adyen version av inbyggd programvara | Högsta Adyen version av inbyggd programvara |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_73p6 |

# <a name="10026"></a>[10.0.26](#tab/10-0-26)
### <a name="dynamics-365-retail-pos-version-10026"></a>Dynamics 365 Retail POS version 10.0.26
| Minsta Adyen version av inbyggd programvara | Högsta Adyen version av inbyggd programvara |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10027"></a>[10.0.27](#tab/10-0-27)
### <a name="dynamics-365-retail-pos-version-10027"></a>Dynamics 365 Retail POS version 10.0.27
| Minsta Adyen version av inbyggd programvara | Högsta Adyen version av inbyggd programvara |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10028"></a>[10.0.28](#tab/10-0-28)
### <a name="dynamics-365-retail-pos-version-10028"></a>Dynamics 365 Retail POS version 10.0.28
| Minsta Adyen version av inbyggd programvara | Högsta Adyen version av inbyggd programvara |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p22 |

# <a name="10029"></a>[10.0.29](#tab/10-0-29)
### <a name="dynamics-365-retail-pos-version-10029"></a>Dynamics 365 Retail POS version 10.0.29
| Minsta Adyen version av inbyggd programvara | Högsta Adyen version av inbyggd programvara |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

# <a name="10030"></a>[10.0.30](#tab/10-0-30)
### <a name="dynamics-365-retail-pos-version-10030"></a>Dynamics 365 Retail POS version 10.0.30
| Minsta Adyen version av inbyggd programvara | Högsta Adyen version av inbyggd programvara |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

---

> [!NOTE]
> Adyen kan frisläppa mindre versionsuppdateringar när Microsoft har testat huvudversionen. Så länge en större version stöds är det ok att ha mindre versionsuppdateringar inom samma huvudversion. Dessa uppdateringar är normalt mycket målinriktad korrigering och uppfyller inte fältet för fullständig omtestning så länge samma större version av inbyggd programvara har testats tidigare. Uppdateringar bör inte överskrida den maximala Adyen version av inbyggd programvara som anges i dokumentationen. 
>
> För att migrera från en Adyen version av inbyggd programvara som är tidigare än version 53 till version 53 krävs POS KB **4577957** för månatliga uppdateringar av Commerce, version 10.0.11 till 10.0.14. Om en av dessa versioner används och inte inkluderar snabbkorrigeringen tillåter efteruppgraderingen av betalningsterminalen endast betalningar via NFC. Det här problemet löses genom att snabbkorrigeringen tillämpas i POS. Om POS-versionen är äldre än version 10.0.11 bör du skicka en supportbegäran och ta reda på att en korrigering för KB **4577957** krävs för en MPOS ur bruk.
> 
> För Adyen version av inbyggd programvara 59p7 till 62p9 begär åtgärden **inlösen av presentkort** inmatning av PIN två gånger i scenarier där presentkortet läggs in manuellt. Det här problemet återskapas inte när presentkortet dras. Adyen undersöker. 

### <a name="supported-payment-terminals"></a>Betalningsterminaler som stöds
Dynamics 365 Payment Connector för Adyen använder sig av enhetsoberoende [API för Adyen betalningsterminal](https://www.adyen.com/blog/introducing-the-terminal-api). Det stöder alla betalningsterminaler som detta API (Application Programming Interface) har stöd för. En fullständig lista över betalningsterminaler som stöds finns på sidan [Adyen-kassaterminaler](https://www.adyen.com/pos-payments/terminals).

I följande video beskrivs kapaciteten hos betalningsterminalen Adyen Castles SE1 Android.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5bKeM]

### <a name="supported-payment-instruments"></a>Betalningmedel som stöds

#### <a name="supported-debit-and-credit-cards"></a>Debet- och kreditkort som stöds

| Varumärke | Variant | Kortet är tillgängligt | E-handel | Kundtjänst |
|---|---|:-:|:-:|:-:|
| MasterCard | Kredit | ✔ | ✔ | ✔ |
| MasterCard | Debet | ✔ | ✔ | ✔ |
| MasterCard | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| MasterCard | Apple Pay | ✔ |  |  |
| MasterCard | Samsung Pay | ✔ |  |  |
| MasterCard | Maestro | ✔ | ✔ | ✔ |
| MasterCard | Maestro Samsung Pay | ✔ |  |  |
| MasterCard | Maestro UK | ✔ | ✔ | ✔ |
| VISA | Kredit | ✔ | ✔ | ✔ |
| VISA | Debet | ✔ | ✔ | ✔ |
| VISA | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| VISA | Android Pay | ✔ |  |  |
| VISA | Apple Pay | ✔ |  |  |
| VISA | Samsung Pay | ✔ |  |  |
| VISA | VISA Checkout | ✔ | ✔ | ✔ |
| VISA | VISA Dankort | ✔ | ✔ | ✔ |
| VISA | VISA Hipotecario | ✔ | ✔ | ✔ |
| VISA | VISA Aravia Card | ✔ | ✔ | ✔ |
| AMEX | Kredit | ✔ | ✔ | ✔ |
| AMEX | Debet | ✔ | ✔ | ✔ |
| AMEX | Android Pay | ✔ |  |  |
| AMEX | Apple Pay | ✔ |  |  |
| AMEX | Samsung Pay | ✔ |  |  |
| AMEX | AMEX Commercial | ✔ | ✔ | ✔ |
| AMEX | AMEX Consumer | ✔ | ✔ | ✔ |
| AMEX | AMEX Corporate | ✔ | ✔ | ✔ |
| AMEX | AMEX småföretag | ✔ | ✔ | ✔ |
| Identifiera | Standard | ✔ | ✔ | ✔ |
| Identifiera | Android Pay | ✔ |  |  |
| Identifiera | Apple Pay | ✔ |  |  |
| Identifiera | Samsung Pay | ✔ |  |  |
| Diners   | Standard | ✔ | ✔ | ✔ |
| Dineromail | Standard | ✔ | ✔ | ✔ |
| JCB | Standard | ✔ | ✔ | ✔ |
| Union Pay\* | Standard | ✔ |  |  |
| Interac Debet\* | Standard | ✔ |  |  |

\*Interac- och Union Pay-återkommande korttoken tillhandahålls inte av Adyen, så de kan inte stöds för kort som inte finns i några transaktioner.

#### <a name="supported-gift-cards"></a>Presentkort som stöds
| Schema | Kortet är tillgängligt | Kortet är inte tillgängligt |
|---|:-:|---|
| Givex | ✔ | ✔ |
| SVS | ✔ | ✔ |

Som ett stöd för dessa externa presentkortsscheman via Dynamics 365 Payment Connector för Adyen måste du utföra ytterligare steg. Mer information finns i [Stöd för externa presentkort](/dynamics365/unified-operations/retail/dev-itpro/gift-card).

#### <a name="supported-wallets"></a>Plånböcker som stöds

| Schema | Kortet är tillgängligt | Kortet är inte tillgängligt |
|---|---|---|
| Alipay | Stöd läggs till i framtida versioner. | Nej |
| WeChat | Stöd läggs till i framtida versioner. | Nej |

#### <a name="supported-card-present-input-methods"></a>Kort som stöds ger inmatningsmetoder
| Inmatningsmetod | Stöds | Anteckningar |
|---|:-:|---|
| Dragning | ✔ | |
| Dra | ✔ | |
| Tryck | ✔ | |
| Manuell inmatning via POS-användargränssnitt. |  | Detta stöds inte för tillfället |
| Manuell registrering via betalningsterminalen. | ✔ | Stöder manuell inmatning av kredit-, debet- och presentkort med PIN-inmatning. | 


#### <a name="supported-card-present-countries"></a>Kort som stöds i länder

Följande länder har tillgängliga handelskomponenter och kort som ger stöd från Adyen. För aktuell internationell tillgänglighet för Commerce, besök [sidan Internationell tillgänglighet](/dynamics365/get-started/availability).

| Land | Stöds |
| --- | :-: |
| Australien | ✔ |
| Österrike | ✔ |
| Belgien | ✔ |
| Kanada | ✔ |
| Tjeckien | ✔ |
| Danmark | ✔ |
| Estland | ✔ |
| Finland | ✔ |
| Frankrike | ✔ |
| Tyskland | ✔ |
| Hongkong | ✔ |
| Ungern | ✔ |
| Island | ✔ |
| Irland | ✔ |
| Italien | ✔ |
| Japan | Framtida version |
| Lettland | ✔ |
| Litauen | ✔ |
| Malaysia | ✔ |
| Nederländerna | ✔ |
| Nya Zeeland | ✔ |
| Norge | ✔ |
| Polen | ✔ |
| Singapore | ✔ |
| Schweiz | ✔ |
| Spanien | ✔ |
| Sverige | ✔ |
| Schweiz | ✔ |
| Storbritannien | ✔ |
| USA | ✔ |
| Brasilien | Framtida version |

#### <a name="supported-card-not-present-countries"></a>Kort som inte stöds i länder

Följande länder stöds av Adyen för kort som inte är aktuella transaktioner. [Kontakta Adyen](https://www.adyen.com/contact/sales) för mer information om support för ett specifikt land. För aktuell internationell tillgänglighet för Commerce, besök [sidan Internationell tillgänglighet](/dynamics365/get-started/availability).

| Land | 
| --- |
| Argentina |
| Armenien |
| Australien |
| Österrike |
| Bahrain |
| Belgien |
| Brasilien |
| Bulgarien |
| Kanada |
| Chile |
| Kina |
| Colombia |
| Kroatien |
| Cypern |
| Tjeckien  |
| Danmark |
| Egypten |
| Estland |
| Finland |
| Frankrike |
| Georgien |
| Tyskland |
| Gibraltar |
| Grekland |
| Guernsey |
| Hongkong |
| Ungern |
| Island |
| Indien |
| Indonesien |
| Irland |
| Isle of Man |
| Israel |
| Italien |
| Japan |
| Jersey |
| Korea |
| Kuwait |
| Lettland |
| Litauen |
| Luxemburg |
| Malaysia |
| Malta |
| Mexiko |
| Marocko |
| Nederländerna |
| Nya Zeeland |
| Norge |
| Peru |
| Polen |
| Portugal |
| Qatar |
| Rumänien |
| Saudiarabien |
| Serbien |
| Singapore |
| Slovakien |
| Slovenien |
| Sydafrika |
| Spanien |
| Sverige |
| Schweiz |
| Taiwan |
| Tanzania |
| Thailand |
| Türkiye |
| Förenade Arabemiraten (UAE) |
| Storbritannien |
| USA, inklusive Puerto Rico  |

#### <a name="supported-dynamics-365-payment-features"></a>Betalningsfunktioner som stöds i Dynamics 365

I följande tabell visas de funktioner som Dynamics 365 Payment Connector för Adyen har stöd för. De här funktionerna använder förbättringar som finns i betalnings-SDK och vissa komponenter i december 2018. De är inte exklusiva för Dynamics 365 Payment Connector för Adyen. Mer information om hur du gör de här förbättringarna för en annan betalningsanslutning finns i [Skapa en integration av komplett betalning för en betalningsterminal](/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension).

| Schema | Kortet är tillgängligt | Kortet är inte tillgängligt |
|---|:-:|:-:|
| [Lösa in presentkortets saldo](/dynamics365/unified-operations/retail/dev-itpro/gift-card-cash-out) | ✔ | |
| [Skydda mot dubblettbetalningar](/dynamics365/unified-operations/retail/duplicate-payment-protection) | ✔ | |
| Tokenisering i flera kanaler | ✔ | ✔ |
| Länkade återbetalningar | ✔<br>(Börjar med 10.0.1) | ✔<br>(Börjar med 10.0.1) |
| [Spara onlinebetalningar](../dev-itpro/adyen-connector-listPI.md) | | ✔<br>(Börjar med 10.0.2) | 
| [Externa presentkort för kundtjänst och e-handel](./gift-card.md) | ✔<br>(Börjar med 10.0.10) | 
| [Omdirigering av SCA-betalning](../adyen_redirect.md) | | ✔<br>(Börjar med 10.0.12) |
| [Dedikerade betalningsterminaler och fråga om skrivare och kassalåda](../pos-multi-hws.md) | ✔<br>(Börjar med 10.0.12) | |
| [Stöd för dricks på SDK-nivå via Adyen anslutningsprogram](tipping.md) | ✔<br>(Börjar med 10.0.14) | |
| [Inkrementell registrering för orderfakturering](incremental-capture.md) |  | ✔<br>(Börjar med 10.0.18) |
| [Plånboksbetalningar](../wallets.md) |  | ✔<br>(Börjar med 10.0.20) |
| [Google Pay med Adyen](google-pay-adyen.md) |  | ✔<br>(Börjar med 10.0.27) |

## <a name="next-steps"></a>Nästa steg

För information om hur du registrerar dig för och konfigurerar Dynamics 365 Payment Connector för Adyen finns i [inställningar Dynamics 365 Payment Connector för Adyen](adyen-connector-setup.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera Dynamics 365 Payment Connector för Adyen](adyen-connector-setup.md)

[Vanliga frågor och svar om Dynamics 365 Payment Connector för Adyen](adyen-connector-faq.md)

[Felsök Dynamics 365 Payment Connector för Adyen](adyen-connector-troubleshoot.md)

[Vanliga frågor om betalningar](/dynamics365/unified-operations/retail/dev-itpro/payments-retail)

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
