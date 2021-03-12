---
title: Översikt över kostnadsversioner
description: Det här avsnittet innehåller information om kostnadsversioner, hur du underhåller dem och datatyperna som du kan inkludera i dem. Det primära syftet med en kostnadsredovisningsversion är att den innehåller kostnadsposter om artiklar, kostnadskategorier och beräkningsformler för indirekta kostnader.
author: AndersGirke
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 54532
ms.assetid: cd239da5-f434-4d1b-8196-5414c888d76d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 287aabaa6a0b3de709dae8b16dbccc21dc349cf5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987639"
---
# <a name="costing-versions-overview"></a>Översikt över kostnadsversioner

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om kostnadsversioner, hur du underhåller dem och datatyperna som du kan inkludera i dem. Det primära syftet med en kostnadsredovisningsversion är att den innehåller kostnadsposter om artiklar, kostnadskategorier och beräkningsformler för indirekta kostnader.

En kostnadsredovisningsversion kan fylla ett eller flera syften beroende på data som finns i kostnadsredovisningsversionen. Det primära syftet med en kostnadsredovisningsversion är att den innehåller kostnadsposter om artiklar, kostnadskategorier och beräkningsformler för indirekta kostnader. En kostnadsversion kan innehålla en uppsättning standardkostnadsposter eller en uppsättning planerade kostnadsposter som baseras på kostnadstypen som tilldelas kostnadsversionen.

## <a name="costing-versions-for-standard-or-planned-costs"></a>Kostnadsredovisningsversioner för standard- eller planeringskostnader.
### <a name="standard-costs"></a>Standardkostnader

En kostnadsredovisningsversion kan stödja lagermodellen med standardkostnad, där kostnadsredovisningsversionen innehåller en uppsättning standardkostnadsposter om artiklar och tillverkningsprocesser. Kostnadsdata om tillverkningsprocesser uttrycks som kostnadskategorier för flödesoperationer och beräkningsformler för produktionsomkostnader.

### <a name="planned-costs"></a>Planerade kostnader

En kostnadsredovisningsversion kan innehålla en uppsättning planerade kostnadsposter om artiklar och tillverkningsprocesser. En kostnadsredovisningsversion med planerade kostnader används ofta för att ge stöd till kostnadsberäkningssimuleringar, till exempel för att simulera effekten av kostnadsändringar på inköpta material eller effekten som tillverkningsprocesser har på beräknade kostnader för tillverkade artiklar. Artikelkostnadsposter för planerade kostnader kan även användas som stöd för en lagermodell för faktisk kostnad, genom att tillhandahålla startvärden för artikelkostnader. Dessa värden omfattar beräkningen av planerade kostnader för tillverkade artiklar.

## <a name="entering-costs"></a>Ange kostnader
Dataunderhåll för kostnadsposter i en kostnadsversion inkluderar att ange kostnader för inköpta artiklar och för artiklar som överförs mellan platser. Annat dataunderhåll för tillverkare inkluderar att registrera kostnader för kostnadskategorier som associeras med flödesoperationer, ange beräkningsformler för indirekta kostnader som återspeglar produktionsomkostnader, samt beräkna kostnader för tillverkade artiklar. 

Artikelkostnadsdata i en kostnadsredovisningsversion består av en eller flera kostnadsposter för varje artikel. När en artikelkostnadspost först registreras har den status **Väntande** och ett avsett giltighetsdatum. När artikelkostnadsposten aktiveras uppdateras statusvärdet till **Aktiv** och giltighetsdatumet uppdateras till aktiveringsdatumet. Olika artikelkostnadsposter återspeglar olika platser, giltighetsdatum eller statusar. När du beräknar kostnader för tillverkade artiklar för ett framtida datum, använder beräkningen av strukturlistan (BOM) kostnadsposterna med relevant giltighetsdatum oavsett om status är **Väntande** eller **Aktiv**. En artikels aktuella aktiva kostnadspost används för uppskattning av tillverkningsorderkostnader och värdering av lagertransaktioner under en lagermodell för standardkostnad. Underhållet av kostnadsposter för kostnadskategorier och formler för indirekt kostnadsberäkning påminner om underhållet av artikelkostnadsposter. 

Två spärrningsprinciper för en kostnadsversion bestämmer om pågående kostnader kan underhållas och om pågående kostnader kan aktiveras. Använd spärrningsprinciperna när du vill tillåta dataunderhåll och sedan använda dem till att förhindra dataunderhåll för kostnadsposter i en kostnadsversion. 

En kostnadsversion kan också innehålla data om artikelförsäljningspriser eller inköpspriser för strukturlisteberäkning.

## <a name="item-sales-prices-for-bom-calculations"></a>Artikelförsäljningpriser för strukturlisteberäkningar
Huvudorsaken för att inkludera data om försäljningpriser är att bibehålla en tillverkad artikels beräknade försäljningpris. Det beräknade försäljningpriset kan sedan analyseras för att ange hur komponenter, flödesoperationer och omkostnader bidrar till kostnaden och försäljningpriset. 

En sekundär orsak till att ta med data om försäljningpriser är att definiera försäljningprisposterna för komponentartiklar. Dessa poster kan sedan användas för att beräkna försäljningpriset för tillverkade artiklar. Du definierar först försäljningsprismodellen som bäddas in i en strukturlisteberäkningsgrupp och tilldelar strukturlisteberäkningsgruppen till inköpta artiklar. Därefter när du utför strukturlisteberäkningar med planerade kostnader väljer du självkostnadsmodellen på strukturlistans beräkningsgrupp. 

I annat fall är försäljningsprisposterna för artiklar endast en referens, oavsett om posterna anges eller beräknas manuellt. Genom att aktivera en artikels försäljningprispost kan du uppdatera artikelns basförsäljningspris. Basförsäljningspriset är dock inte platsspecifikt och går att åsidosätta manuellt. Artikelns basförsäljningspris används som standardförsäljningspris på försäljningsorder och försäljningsofferter.

## <a name="item-purchase-prices-for-bom-calculations"></a>Artikelinköpspriser för strukturlisteberäkningar
Huvudsyftet med att aktivera inköpsprisdata är att definiera inköpsprisposter för komponentartiklar, som sedan kan användas för att beräkna kostnaderna för tillverkade artiklar. Artikelinköpsprisposterna måste registreras manuellt. 

Om du vill aktivera inköpsprisinnehåll definierar du först en strukturlisteberäkningsgrupp som innehåller en självkostnadsmodell för artikelns inköpspris och tilldelar strukturlisteberäkningsgruppen till inköpta artiklar. Du använder sedan en självkostnadsmodell för strukturlisteberäkningsgruppen när du utför strukturlisteberäkningar med planerade kostnader för att beräkna försäljningpriset för tillverkade artiklar. 

Inköpsprisposterna för artiklar används även som referensinformation. Genom att ändra status för en artikels inköpsprispost från **Väntande** till **Aktiv** går det att uppdatera artikelns basinköpspris. Basinköpspriset är dock inte platsspecifikt och går att åsidosätta manuellt. Artikelns basinköpspris används som standardinköpspris på inköpsorder.



