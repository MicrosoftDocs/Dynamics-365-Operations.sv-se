---
title: Definiera kanalspecifika rabatter
description: Återförsäljare ställer ofta in olika rabatter i olika kanaler. Denna artikel behandlar de koncept du behöver känna till för att skapa en rabatt för en viss kanal.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.industry: Retail
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
ms.openlocfilehash: f426503a6897a73010b77082f4277b65545bfcc3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273565"
---
# <a name="define-channel-specific-discounts"></a>Definiera kanalspecifika rabatter

[!include [banner](includes/banner.md)]

Denna artikel behandlar de koncept du behöver känna till för att skapa en rabatt för en viss kanal.

## <a name="channel-specific-discounts"></a>Kanalspecifika rabatter

Återförsäljare erbjuder ofta olika rabatter i olika kanaler. Detta kan bero på att man vill adressera lokala marknadsvillkor eller hantera konkurrerande återförsäljare.

Commerce använder prisgrupper för att definiera kanalspecifika rabatter. Prisgrupper kan tilldelas till en eller flera av följande enheter: kanaler, kataloger, anknytningar och bonusprogram. Den här artikeln diskuterar kanaler, men samma koncept gäller för katalograbatter, anknytningsrabatter och lojalitetsrabatter.

## <a name="price-groups"></a>Prisgrupper

[![Prisgrupper.](./media/price-groups-1024x608.png)](./media/price-groups.png)

Diagrammet ovan visar relationen mellan enheter som kan göras för en transaktion (kanal, katalog, anknytning, kund, bonuskort) och de olika rabattyper som kan konfigureras. Alla transaktioner uppstår i en kanal, varför kanalen garanterat finns med i en transaktion. De återstående enheterna är valfria. På varje huvuddatasida finns en länk till en relaterad prisgruppssida där du kan visa och lägga till prisgrupper efter behov. En prisgrupp används för koppling av fyra olika typer av enheter till rabatter, prisjusteringar och handelsavtal. Vi rekommenderar att du planerar en strategi för hur du ska namnge dina prisgrupper för att hålla ordning på dem. Ett alternativ är att använda ett bokstavs- eller sifferprefix/-suffix för att skilja mellan de olika typerna. Exempelvis 1-xxxxx för kanal prisgrupper och 2-xxxxx för katalogprisgrupper. Det finns fyra förfrågningssidor som fokuserar på var och en av handelsenheterna som kan ha associerade rabatter.

- **Prisgrupper för kanal** – På den här sidan visas en lista med kanaler och rabatter som är länkade för varje prisgrupp.
- **Katalogprisgrupper** – På den här sidan visas en lista med kataloger och rabatter som är länkade för varje prisgrupp.
- **Bonusprisgrupper** – På den här sidan visas en lista med bonusprogram och rabatter som är länkade för varje prisgrupp.
- **Anknytningsprisgrupper** – På den här sidan visas en lista med anknytningar och rabatter som är länkade för varje prisgrupp.

## <a name="example-channel-discount-set-up"></a>Inställningar för exempelkanalrabatt

Följande exempel illustrerar uppgifterna som ingår i konfigurationen av en kanalrabatt.

1. För det här exemplet har du en kanal kallad **Houston**, och du ska skapa en ny rabatt kallad **Back-to-School**.
2. Eftersom prissättnings- och rabattstrategin inkluderar möjligheten till kanalrabatter skapar du alltid en kanalspecifik prisgrupp när du skapar en kanal.
3. Du har prisgruppen **Houston-PG** och den är tilldelad kanalen **Houston**.
4. När du har skapat den nya rabatten **Back-to-School** måste du klicka på **Prisgrupper** längst upp på sidan **Rabatt**. Sidan **Rabattprisgrupper** öppnas. Välj **Nytt** och välj prisgruppen **Houston-PG**.
5. Nu kan du aktivera rabatten och flytta den till kanalen.

## <a name="additional-resources"></a>Ytterligare resurser

[Prisjusteringar och rabatter](price-adjustments-discounts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
