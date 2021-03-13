---
title: Konfigurera moms för onlinebeställningar
description: Det här ämnet ger en översikt över momsgruppsval för olika typer av onlinebeställning i Dynamics 365 Commerce.
author: gvrmohanreddy
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 56621bb9658b71551c7312aa47812903914bc888
ms.sourcegitcommit: da17648c296b22d517eadb2f71c7803672e5648d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/19/2021
ms.locfileid: "5031799"
---
# <a name="configure-sales-tax-for-online-orders"></a>Konfigurera moms för onlinebeställningar

[!include [banner](includes/banner.md)]

Det här ämnet ger en översikt över momsgruppsval för olika typer av onlinebeställning. 

Din näthandelskanal kanske vill stödja alternativ som leverans eller upphämtning för onlinebeställningar. Momstillämpbarheten baseras på det alternativ som valts av dina onlineanvändare. När en webbplatskund väljer att köpa en artikel online och får den levererad till en adress bestäms momsen utifrån kundens inställning för momsgrupp för leveransadress. När en kund väljer att hämta en inköpt artikel i en butik bestäms momsen baserat på upphämtningsbutikens inställning för momsgrupp. 

## <a name="orders-shipped-to-a-customer-address"></a>Order som levereras till en kundadress 

I allmänhet definieras moms för onlineorder som levereras till kundadresser av målet. Varje momsgrupp har en konfiguration för målbaserad momskonfiguration där ditt företag kan definiera destinationsinformation som exempelvis land/region, delstat, region och ort i ett hierarkiskt formulär. När en onlineorder har lagts använder skattemotorn för Commerce leveransadressen för respektive radartikel i ordern och söker efter momsgrupper med matchande destinationsbaserade momskriterier. För en onlinebeställning med en leveransadress för en radartikel till San Francisco, Kalifornien, kommer skattemotorn att hitta momsgrupp och momskod för Kalifornien och sedan beräkna momsen för respektive radartikel därefter.  

## <a name="customer-based-tax-groups"></a>Kundbaserade momsgrupper

I Commerce-administrationen finns två platser där kundmomsgrupper konfigureras:

- **Kundprofil**
- **Kundens leveransadress**

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a>Om en kundprofil har en momsgrupp konfigurerad

En kunds profilpost i administrationen kan ha en konfigurerad momsgrupp, men för onlinebeställningar kan momsgruppen som konfigurerats i en kundprofil inte användas av skattemotorn. 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a>Om en kunds leveransadress har en momsgrupp konfigurerad

Om en kunds leveransadresspost har en konfigurerad momsgrupp och en onlinebeställning (eller radartikel) levereras till kundens leveransadress, används den momsgrupp som konfigurerats i kundens adresspost av skattemotorn för momsberäkningar.

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a>Konfigurera en momsgrupp för en kunds leveransadresspost

Om du vill konfigurera en momsgrupp för en kunds leveransadresspost i Commerce-administrationen följer du stegen nedan.

1. Gå till **Alla kunder** och välj önskad kund. 
1. I snabbfliken **Adresser** väljer du önskad adress och sedan **Fler alternativ \> Avancerat**. 
1. Under fliken **Allmänt** på sidan **Hantera adresser** anger du önskat momsvärde.

> [!NOTE]
> Momsgruppen definieras med hjälp av leveransadressen för orderraden, och de målbaserade momssatserna konfigureras i själva momsgruppen. Mer information finns i [Konfigurera moms för onlinebutiker baserat på destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="order-pickup-in-store"></a>Orderupphämtning i butik

För orderrader med upphämtning i butik eller drive in-upphämtning anges momsgruppen från den valda upphämtningsbutiken. Mer information om hur du konfigurerar momsgruppen för en viss butik finns i [Ställa in andra momsalternativ för butiker](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

> [!NOTE]
> När en orderrad hämtas i en butik ignoreras skatteinställningarna för kundens adress (om dessa ställts in) av skattemotorn, och upphämtningsbutikens skattekonfiguration tillämpas. 

## <a name="additional-resources"></a>Ytterligare resurser

[Momsöversikt](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[Momsberäkningsmetoder i fältet Ursprung](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[Momstilldelning och åsidosättningar](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[Beräkningsalternativ för hela beloppet och intervall för momskoder](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[Beräkning av momsbefrielse](tax-exempt-price-inclusive.md) 

