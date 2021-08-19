---
title: Inkludera fysiskt värde
description: Du använder kryssrutan Inkludera fysiskt värde på snabbfliken Lagermodell på sidan Artikelmodellgrupper för att ange om fysiskt uppdaterade transaktioner ska beaktas vid beräkningen av den löpande genomsnittliga självkostnaden för en artikel.
author: AndersGirke
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 711c30376c4f1ecc5c1a747c675e6438a867c51ed066b6c15cdace6a071f7cfd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751132"
---
# <a name="include-physical-value"></a>Inkludera fysiskt värde

[!include [banner](../includes/banner.md)]

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

-   En inköpsorder för kvantiteten 2 och en självkostnad på 100,00 kronor som har följesedelsuppdaterats.
-   En inköpsorder för kvantiteten 3 och en självkostnad på 120,00 kronor som har fakturauppdaterats.

I det här fallet blir den genomsnittliga självkostnaden 112,00 kronor = (2x10+3x12)/(2+3) eftersom både fysiskt och ekonomiskt uppdaterade transaktioner används för att beräkna självkostnaden. 

**Exempel 2** Du har inte markerat **Inkludera fysiskt värde**-kryssrutan och självkostnaden för artikelns inställningar är 100,00 kronor. 

-   Du tar emot en inköpsorder för kvantiteten 20 och en självkostnad på 120,00 kronor som har följesedelsuppdaterats.

När en försäljningsorder bokförs, bokförs beloppet 100,00 kronor eftersom den genomsnittliga självkostnaden inte inkluderar fysiskt bokförda transaktioner. 

> [!NOTE]
> Jämfört med, om du markerar **Inkludera fysiskt värde**-kryssrutan för den här artikeln, när en försäljningsorder bokförs, det bokförda kostnadsbeloppet är 120,00 kronor.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]