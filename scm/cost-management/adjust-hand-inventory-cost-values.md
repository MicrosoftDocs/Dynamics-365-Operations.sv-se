---
title: "Justera kostnadsvärden för lagerbehållning"
description: "Använd sidan Justering av lagerbehållning för att justera kostnadsvärdet för lagerbehållningskvantiteter efter att en lagerstängningsprocess har körts."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d1ef775c9783b975fd0f852dc7112506d3897605
ms.lasthandoff: 03/31/2017


---

# <a name="adjust-on-hand-inventory-cost-values"></a>Justera kostnadsvärden för lagerbehållning

[!include[banner](../includes/banner.md)]


Använd sidan Justering av lagerbehållning för att justera kostnadsvärdet för lagerbehållningskvantiteter efter att en lagerstängningsprocess har körts.

På sidan **Justering av lagerbehållning** kan du justera justera kostnadsvärdet för lagerbehållningskvantiteter när en lagerstängningsprocess körs. **Obs!** Om du vill öppna sidan **Justering av lagerbehållning** går du till sidan **Stängning och justering** och markerar posten för en slutförd lagerstängningsprocess. Klicka sedan på **Justering** &gt; **Behållning**. **Exempel:** Du har följande transaktioner i februari:

-   1 februari: en ekonomisk lagerinleverans för kvantiteten 2 till en kostnad av 100 SEK.
-   5 februari: en ekonomisk lagerinleverans för kvantiteten 1 till en kostnad av 130 SEK.
-   19 februari: en ekonomisk lagerutleverans för en kvantitet på 1 till en genomsnittlig driftskostnad på 110 SEK.

Denna artikel skapades med FIFO-lagermodellen (först in, först ut), och lagerstängningen genomfördes den 28 februari. Den ekonomiska utleveranstransaktionen på SEK 110,00 kommer att kvittas mot den ekonomiska inleveransen daterad den 1 februari, och en justering på SEK 10,00 kommer att göras. Följande lagerinleveranser kommer därefter att innehålla öppna lagerkvantiteter:

-   1 februari: en kvantitet på 1 till en kostnad av 100 SEK.
-   5 februari: en kvantitet på 1 till en kostnad av 130 SEK.

Ange kostnaden för dessa två artiklar till SEK 150,00 med hjälp av alternativet för justering av lagerbehållning så att de öppna behållningarna justeras per den sista lagerstängningsperioden. **Obs!** Bokföringsdatumet för transaktionen för behållningsjustering är datumet för den senaste lagerstängningen. Datumet går inte att ändra.




