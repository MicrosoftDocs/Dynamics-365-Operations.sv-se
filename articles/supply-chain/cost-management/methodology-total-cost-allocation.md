---
title: Metod för total kostnadsallokering
description: Den här ämnet ger riktlinjer för att använda total kostnadsallokering (TCA). TCA är en metod för att beräkna kostnaden mellan den huvudsakliga receptartikeln för en batchorder och samprodukterna som definieras för receptet.
author: AndersGirke
manager: tfehr
ms.date: 04/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, PmfFormulaCoBy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 83852
ms.assetid: 7c14c3e5-9476-4a79-a210-e77fc91cc7fc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 758015c566e39df7306e1b34b8d3b42f1f1eba79
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437422"
---
# <a name="total-cost-allocation-method"></a>Metod för total kostnadsallokering

[!include [banner](../includes/banner.md)]

Total kostnadsallokering (TCA) är en metod för att beräkna kostnaden mellan den huvudsakliga receptartikeln för en batchorder och samprodukterna som definieras för receptet. Den här metoden är dynamisk. Den beräknar kostnaden som ett viktat medelvärde mellan kvantiteterna som rapporteras som avslutade för receptartikel och samprodukterna. När TCA används behöver du inte granska kostnadsallokeringarna för varje batchorder. Om TCA inte används använder receptberäkningen befintliga funktioner.

## <a name="using-tca-for-coproducts"></a>Använda TCA för samprodukter
Nedan följer några av riktlinjerna för att använda TCA för samprodukter:

-   Om du ställer in skjutreglaget för **Total kostnadsallokering** till **Ja** för en receptversion, samprodukter måste ha en självkostnad som är större än 0 (noll). Värdet kan hämtas från den aktiva kostnadsversionen för samma plats eller för den första platsen för en formel som inte är platsspecifik. Det här villkoret valideras när formeln är godkänd.

    -   Du behöver inte manuellt ange kostnadsallokering i procent för samprodukter I stället skapas automatiskt kostnadsallokering i procent som medelvärdet av aktiva självkostnader för samprodukter. 
    -   Du behöver inte ange en standardkostnad för icke-standardkostnadsartiklar som är samprodukter Det finns två typer av kostnadsversioner i systemet: standardkostnad och planerad kostnad 
    -   Om en artikel inte värderas med värderingsmetoden för standardkostnad, rekommenderar vi att du använder ett aktivt självkostnadspris i den planerade kostnadsredovisningsversionen. Priset används för kostnadsuppskattning, strukturlisteberäkning, t.ex. uppskattning av produktionskostnader och reservpris i lagervärderingsprocessen. 

-   Om du ställer in skjutreglaget för **Total kostnadsallokering** till **Ja** för receptversionen och följande villkor stämmer är metoden för kostnadsallokering **TCA** och procentsatsen för kostnadsallokering oförändrad:
    -   Du lade till samprodukter.
    -   Du använde en annan metod för kostnadsallokering för samprodukterna.
-   Om du ställer in skjutreglaget för **Total kostnadsallokering** till **Nej** för receptversionen och följande villkor stämmer ändras metoden för kostnadsallokering till **Manuell** och procentsatsen för kostnadsallokering är oförändrad:
    -   Du lade till samprodukter.
    -   Den procentandel av kostnadsallokeringen som är större än 0 (noll).
-   Innan du kan utföra en receptberäkning, måste du beräkna procentsatserna för kostnadsallokeringen. Du kan avsluta det här steget antingen manuellt eller genom att använda **Uppskatta kostnad** på **Samprodukter** sidan. **Obs!** Alternativet **Uppskatta kostnad** är endast tillgängligt om **Total kostnadsallokering** skjutreglaget för receptversionen är inställt på **Ja**. Du kan visa den förväntade allokeringen om batchorderkvantiteterna som rapporteras som färdiga matchar kvantiteterna som visas för formeln.
-   När en batchorder skapas manuellt, eller en planerad batchorder som har bekräftats, kopieras värdet för skjutreglaget **Total kostnadsallokering** för receptversionen till batchordern. Du kan dock ändra den här inställningen på batchordern. Om **Total kostnadsallokering** skjutreglaget anges till **Nej** för receptversionen och sedan ändras till **Ja** för batchordern ändras metoden för kostnadsallokeringen för varje rad som angavs till **Manuell** till **TCA**. En kostnadsallokering av **Ingen** är oförändrad. Om **Total kostnadsallokering** skjutreglaget anges till **Ja** för receptversionen och sedan ändras till **Nej** för batchordern ändras metoden för kostnadsallokeringen för varje samprodukt för typen **Produktion** till **Manuell**. Alla uppskattade procentandelar av kostnadsallokeringen är oförändrade.
-   Sidan **Kostnadsallokering för samprodukt** visar den beräknade kostnadsallokeringsprocenten. Du kan öppna den här sidan från sidan **Batchorder**. Denna information är användbar när produkterna och kvantiteterna som rapporteras skiljer sig från de schemalagda eller startade kvantiteterna för batchordern. När kostnaden är färdig, visas de nya procentsatsallokeringarna från TCA på **Kostnadsallokering för samprodukt** sidan.

## <a name="calculating-the-burden-for-byproducts"></a>Beräkna bördan för biprodukter
Fältet **Kostnadsallokering för biprodukt** på sidan **Samprodukter** är ett uppräknarfält som används endast för biprodukter. För samprodukter är värdet för detta fält alltid **Ingen**. För biproduktrader det här fältet avgör hur kostnadsbeloppet för biproduktraden läggs till den totala kostnaden för produktionen. Följande alternativ är tillgängliga:

-   **Ingen** – Inget belopp anges till den totala kostnaden för produktionen för den här biproduktraden.
-   **Procent** – Kostnadsbeloppet beräknas som en procentandel av den totala kostnaden för råmaterial som förbrukas i produktionen. Procentvärdet som används för beräkningen anges i fältet.
-   **Per serie** – Kostnadsbeloppet beräknas som ett belopp per standardbatchstorlek för tillverkningsordern. Detta belopp är oberoende av den rapporterade kvantiteten i produktionen. Beloppet som används för beräkningen anges i fältet.
-   **Per kvantitet** – Kostnadsbeloppet beräknas som ett belopp per kvantitet för den rapporterade receptartikeln i produktionen. Beloppet som används för beräkningen anges i fältet.




