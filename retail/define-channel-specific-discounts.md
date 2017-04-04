---
title: Definiera kanalspecifika rabatter
description: "Återförsäljare ställer ofta in olika rabatter i olika kanaler. Det här avsnittet behandlar de koncept du behöver känna till för att skapa en rabatt för en viss kanal."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: b2f59db59ea49925c3bb5e1d75beee95191220d0
ms.lasthandoff: 03/31/2017


---

# <a name="define-channel-specific-discounts"></a>Definiera kanalspecifika rabatter

Återförsäljare ställer ofta in olika rabatter i olika kanaler. Det här avsnittet behandlar de koncept du behöver känna till för att skapa en rabatt för en viss kanal. 

<a name="channel-specific-discounts"></a>Kanalspecifika rabatter
--------------------------

Återförsäljare ger ofta olika rabatter i olika kanaler. Detta är göras till adressen lokala marknadsvillkor eller hantera konkurrerande återförsäljare.

Butik och handel i Microsoft Dynamics 365 för operationer för prisgrupper definierar kanalspecifika. Prisgrupper kan tilldelas till en eller flera av följande enheter: kanaler, kataloger, anknytningar och bonusprogram. Den här artikeln diskuterar kanaler, men samma koncept gäller för katalograbatter, anknytningsrabatter och lojalitetsrabatter.

## <a name="price-groups"></a>Prisgrupper
\[Rubrik-id = "bilaga\_256084" justera = "alignnone" width = "640"\][![uppdatering grupper](./media/price-groups-1024x608.png)](./media/price-groups.png) pris gruppera länkar för Retail\[/beskrivning\]

Diagrammet ovan visar relationen mellan entiteter som kan göras på en transaktion (kanal, katalog, anknytning, kund, förmånskort) och olika rabattyper som kan konfigureras. Alla transaktioner som uppstår i en kanal så att kanalen garanterat finns i en transaktion. De återstående enheterna är valfria. På varje huvuddatasida finns en länk till en relaterad prisgruppssida där du kan visa och lägga till prisgrupper efter behov. En prisgrupp för handelsavtal, prisjusteringar och rabatter rör fyra typer av enheter. Vi rekommenderar att du planerar en strategi för hur du namnger en prisgrupper för att hålla ordning på dem. Ett alternativ är att använda ett brev eller prefix eller suffix för att skilja mellan de olika typerna. Exempelvis 1-xxxxx prisgrupper och 2-xxxxx för katalogen prisgrupper. Det finns fyra förfrågningssidor som fokuserar på var och en av återförsäljarenheterna som kan ha associerade rabatter.

-   **Prisgrupper för butikskanal **– På den här sidan visas en lista med kanaler och rabatter som är länkade för varje prisgrupp.
-   **Katalogprisgrupper **– På den här sidan visas en lista med kataloger och rabatter som är länkade för varje prisgrupp.
-   **Bonusprisgrupper **– På den här sidan visas en lista med bonusprogram och rabatter som är länkade för varje prisgrupp.
-   **Anknytningsprisgrupper **– På den här sidan visas en lista med anknytningar och rabatter som är länkade för varje prisgrupp.

## <a name="example-channel-discount-set-up"></a>Inställningar för exempelkanalrabatt
Följande exempel illustrerar uppgifterna som ingår i konfigurationen av en kanalrabatt.

1.  För det här exemplet har du en kanal kallad **Houston**, och du ska skapa en ny rabatt kallad **Back-to-School**.
2.  Eftersom prissättnings- och rabattstrategin inkluderar möjligheten till kanalrabatter skapar du alltid en kanalspecifik prisgrupp när du skapar en kanal.
3.  Du har prisgruppen **Houston-PG** och den är tilldelad kanalen **Houston**.
4.  När du har skapat den nya rabatten **Back-to-School** måste du klicka på **Prisgrupper** längst upp på sidan **Rabatt**. Sidan **Rabattprisgrupper** öppnas. Välj **Nytt** och välj prisgruppen **Houston-PG**.
5.  Nu kan du aktivera rabatten och flytta den till kanalen.

 

<a name="see-also"></a>Se även
--------

[Price adjustments and discounts](price-adjustments-discounts.md)


