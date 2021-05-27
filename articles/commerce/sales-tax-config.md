---
title: Konfigurera moms för onlinebeställningar
description: Det här ämnet ger en översikt över momsgruppsval för olika typer av onlinebeställning i Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: fff4f39703a146412b460dacc3805fde097ab756
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021450"
---
# <a name="configure-sales-tax-for-online-orders"></a>Konfigurera moms för onlinebeställningar

[!include [banner](includes/banner.md)]

Detta ämne ger en översikt över momsgruppsurval för olika onlineordertyper med hjälp av antingen destinationsbaserade eller kundkontobaserade skatteinställningar. 

Det kan vara en god idé att låta näthandelskanal stödja alternativ som leverans eller upphämtning för onlinebeställningar. Momstillämpbarheten baseras på det alternativ som valts av dina onlinekunder. 

## <a name="destination-based-taxes-for-online-orders"></a>Målbaserade skatter för onlineorder

I allmänhet definieras skatter för onlineorder som levereras till kundadresser av målet. Varje momsgrupp har en konfiguration för målbaserad skattekonfiguration där ditt företag kan definiera destinationsinformation som exempelvis land eller region, delstat, region och ort i ett hierarkiskt formulär.

### <a name="orders-delivered-to-customer-address"></a>Order som levereras till en kundadress

När en onlineorder har lagts använder skattemotorn för Commerce leveransadressen för respektive radartikel i ordern och söker efter momsgrupper med matchande destinationsbaserade skattekriterier. För en onlinebeställning med en leveransadress för en radartikel till San Francisco, Kalifornien, kommer skattemotorn att hitta momsgrupp och momskod för Kalifornien och sedan beräkna skatten för respektive radartikel därefter.

### <a name="order-pick-up-in-store"></a>Orderupphämtning i butik

För orderrader med upphämtning i butik eller drive in-upphämtning anges skattegruppen från den valda upphämtningsbutiken. Mer information om hur du konfigurerar moms för en viss butik finns i [Ställa in andra skattealternativ för butiker](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

## <a name="customer-account-based-taxes-for-online-orders"></a>Kundkonto-baserade skatter för onlineorder

Det kan finnas ett affärsscenario där du vill konfigurera en momsgrupp för ett visst kundkonto i Commerce Headquarters. Det finns två platser i huvudkontoret där du kan konfigurera moms på ett kundkonto. För att komma åt dessa måste du först gå till en kundinformationssida genom att gå till **Butik och handel \> Kunder \> Alla kunder** och välja en kund.

De två platser där du kan konfigurera moms för ett kundkonto är följande:

- **Momsgruppen** på snabbfliken **Faktura och leveran** på kundinformationssidan. 
- **Moms** på snabbfliken **Allmänt** på sidan **Hantera adresser**. Du kommer dit från sidan Kundinformation genom att välja en specifik adress under snabbfliken **Adresser** och sedan **Avancerat**.

> [!TIP]
> Om du endast vill tillämpa målbaserade skatter och undvika kundkontobaserade skatter på online-kundorder måste du kontrollera att fältet **Momsgrupp** är tomt på snabbfliken **Faktura och leverans** på sidan för kundinformation. Om du vill vara säker på att nya kunder som registrerar sig via onlinekanalen inte ärver momsgruppsinställningarna från standardinställningarna för kund eller kundgrupp, måste du se till att fältet **Momsgrupp** är tomt även för onlinekanalinställningarna för standardkund och kundgruppsinställningar (**Butik och handel \> Kunder \> Kundgrupper**).

## <a name="determine-destination-based-tax-or-customer-account-based-tax-applicability"></a>Fastställa målbaserad skatt eller kundkontobaserad tillämpbarhet för skatt 

I följande tabell beskrivs huruvida målbaserade skatter eller kundkontobaserade skatter används för onlineorder. 

| Kundtyp | Transportadress                   | Kund > Faktura och leverans > Momsgrupp? | Adress för kundkonto i administrationen? | Kundadress > Avancerat > Allmänt > Momsgrupp?                                              | Tillämpad momsgrupp      |
|---------------|------------------------------------|-----------------------------------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------------|------------------------------|
| Gäst         | Manhattan, NY                      | Nej (tom)                                                | Nej (tom)                              | Nej (tom)                                                                                                   | NY (målbaserade skatter) |
| Inloggad     | Austin, TX                          | Nej (tom)                                             | Ja                               | None<br/><br/>Ny adress som läggs till via online-kanal.                                                            | TX (målbaserade skatter) |
| Inloggad     | San Francisco, CA (upphämtning i butik) | Ja (NY)                                            | Inte aktuellt                              | Inte aktuellt                                                                                                    | CA (målbaserade skatter) |
| Inloggad     | Houston, TX                         | Ja (NY)                                            | Ja                               | Ja (NY)<br/><br/>Ny adress som läggs till via online-kanal och momsgrupp ärvd från kundkonto. | NY (kundkontobaserade skatter)  |
| Inloggad     | Austin, TX                          | Ja (NY)                                            | Ja                               | Ja (NY)<br/><br/>Ny adress som läggs till via online-kanal och momsgrupp ärvd från kundkonto. | NY (kundkontobaserade skatter)  |
| Inloggad     | Sarasota, FL                       | Ja (NY)                                            | Ja                               | Ja (WA)<br/><br/>Manuellt inställt på WA.                                                                          | WA (kundkontobaserade skatter)  |
| Inloggad     | Sarasota, FL                       | Nej (tom)                                                | Ja                               | Ja (WA)<br/><br/>Manuellt inställt på WA.                                                                          | WA (kundkontobaserade skatter)  |

## <a name="additional-resources"></a>Ytterligare resurser

[Ställ in skatter för onlinebutiker baserat på destination](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination)

[Momsöversikt](../finance/general-ledger/indirect-taxes-overview.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Momsberäkningsmetoder i fältet Ursprung](../finance/general-ledger/sales-tax-calculation-methods-origin-field.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Momstilldelning och åsidosättningar](../supply-chain/procurement/tasks/sales-tax-assignment-overrides.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Beräkningsalternativ för hela beloppet och intervall för momskoder](../finance/general-ledger/whole-amount-interval-options-sales-tax-codes.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Beräkning av skattebefrielse](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]