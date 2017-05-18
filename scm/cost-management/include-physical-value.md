---
title: "Inkludera fysiskt värde"
description: "Du använder kryssrutan Inkludera fysiskt värde på snabbfliken Lagermodell på sidan Artikelmodellgrupper för att ange om fysiskt uppdaterade transaktioner ska beaktas vid beräkningen av den löpande genomsnittliga självkostnaden för en artikel."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d3efa701e13a6b1593576082499decc439cf0d29
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="include-physical-value"></a>Inkludera fysiskt värde

[!include[banner](../includes/banner.md)]


Du använder kryssrutan Inkludera fysiskt värde på snabbfliken Lagermodell på sidan Artikelmodellgrupper för att ange om fysiskt uppdaterade transaktioner ska beaktas vid beräkningen av den löpande genomsnittliga självkostnaden för en artikel.

Kryssrutan **Inkludera fysiskt värde** har följande värden.

| Värde    | Resultat                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| Markerad | Både fysiskt och ekonomiskt uppdaterade transaktioner används för att beräkna löpande genomsnittlig självkostnad. |
| Reglerat  | Endast ekonomiskt uppdaterade transaktioner används för att beräkna löpande genomsnittlig självkostnad.                                     |

Kryssrutan har något olika effekter, beroende på vilken lagermodell som du använder.

-   Om du markerar **Inkludera fysiskt värde**-kryssrutan när du använder FIFO (först in, först ut), LIFO (sist in, först ut) eller LIFO-datumlagermodellen, lagerstängningen också justerar fysiskt uppdaterade transaktioner.
-   Om du inte markerar kryssrutan **Inkludera fysiskt värde** när du använder dessa lagermodeller, lagerstängningen skapar kvittningar enbart för transaktioner som är ekonomiskt uppdaterade.
-   När du använder lagermodellen för viktat medelvärde eller viktat genomsnittligt datum kvittar lagerstängningen bara ekonomiskt uppdaterade transaktioner oavsett om du markerar kryssrutan **Inkludera fysiskt värde** eller inte.

**Exempel 1** Du har markerat **Inkludera fysiskt värde**-kryssrutan och får följande inköpsorder:

-   En inköpsorder för kvantiteten 2 och en självkostnad på 100,00 kronor som har följesedelsuppdaterats
-   En inköpsorder för kvantiteten 2 och en självkostnad på 120,00 kronor som har fakturauppdaterats

I det här fallet blir den genomsnittliga självkostnaden 112,00 kronor eftersom både fysiskt och ekonomiskt uppdaterade transaktioner används för att beräkna självkostnaden. **Exempel 2** Du har inte markerat **Inkludera fysiskt värde**-kryssrutan och självkostnaden för artikelns inställningar är 100,00 kronor. Du tar emot en inköpsorder för kvantiteten 20 och en självkostnad på 120,00 kronor som har följesedelsuppdaterats. När en försäljningsorder bokförs, bokförs beloppet 100,00 kronor eftersom den genomsnittliga självkostnaden inte inkluderar fysiskt bokförda transaktioner. **Obs!** Jämfört med, om du markerar **Inkludera fysiskt värde**-kryssrutan för den här artikeln, när en försäljningsorder bokförs, det bokförda kostnadsbeloppet är 120,00 kronor.




