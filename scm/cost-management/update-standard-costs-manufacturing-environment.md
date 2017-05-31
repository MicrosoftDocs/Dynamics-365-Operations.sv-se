---
title: "Uppdatera standardkostnader i en tillverkningsmiljö"
description: "Det här avsnittet ger vägledning om hur du uppdaterar standardkostnader i en tillverkningsmiljö."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 74ad59504d6bbea0c604e0f0b83e74c915e84019
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="update-standard-costs-in-a-manufacturing-environment"></a>Uppdatera standardkostnader i en tillverkningsmiljö

[!include[banner](../includes/banner.md)]


Det här avsnittet ger vägledning om hur du uppdaterar standardkostnader i en tillverkningsmiljö. 

Uppdateringar kan återspegla nya artiklar, kostnadskategorier eller beräkningsformler för indirekta kostnader. De kan också återspegla korrigeringar och kostnadsförändringar. Typen av uppdatering påverkar vilka steg som måste slutföras för att uppdatera standardkostnader, vilket visas i exemplen nedan.

-   Ange förväntade standardkostnadsändringar för inköpta artiklar och ändra sedan status för artikelkostnadsposterna till **Aktiv** på lämpligt datum. Du ska däremot inte beräkna om kostnaderna för tillverkade artiklar som använder de inköpta artiklarna.
-   Ange standardkostnader för en ny inköpt artikel, men beräkna inte om kostnaderna för tillverkade artiklar som har en strukturlisteversion (BOM) som innehåller den nya inköpta artikeln som en komponent.
-   Korrigera eller ändra kostnaden för en inköpt artikel eller ändra kostnadsgruppen som tilldelats en inköpt artikel och beräkna kostnaden för alla tillverkade artiklar som har en strukturlisteversion som innehåller den inköpta artikeln som en komponent.
-   Ändra kostnaden för en kostnadskategori och beräkna om kostnaden för alla tillverkade artiklar som har en flödesversion som innehåller flödesoperationer som använder den kostnadskategorin.
-   Ändra kostnadskategorierna som tilldelats till flödesåtgärderna eller den kostnadskalkylerade gruppen som tilldelats till kostnadskategorier. Beräkna sedan kostnaden för en alla tillverkade artiklar som har en flödesversion som innehåller flödesoperationer som använder den kostnadskategorin.
-   Ändra en beräkningsformel för indirekt kostnad, och beräkna kostnaden för alla tillverkade artiklar som påverkas av ändringen.
-   Ändra eller lägga till en tillverkningssite för en tillverkad artikel, och beräkna artikelns tillverkningskostnad för siten.
-   Beräkna (eller beräkna om) kostnaden för en tillverkad artikel och beräkna om kostnaden för alla tillverkade artiklar som har en strukturlisteversion som innehåller den tillverkade artikeln som en komponent.
-   Beräkna kostnader för en ny tillverkad artikel baserat på dess definierade, godkända och aktiva strukturlista och flödesinformation.

I varje fall bör du noggrant överväga hur du ska uppdatera standardkostnader.




