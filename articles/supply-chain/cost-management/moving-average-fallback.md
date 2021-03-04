---
title: Rörligt genomsnitt, reservkostnadssekvens
description: Det här avsnittet innehåller information om reservkostnadssekvenser för beräkningar av rörligt genomsnitt i Microsoft Dynamics 365 Supply Chain Management.
author: AndersGirke
manager: tfehr
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 0538701588b9c71dff4c538711606913a359de6a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437855"
---
# <a name="moving-average-fallback-cost-sequence"></a>Rörligt genomsnitt, reservkostnadssekvens

Ett sätt att beräkna kostnaden för ditt lager är att använda ett _Rörligt genomsnitt_. Upp till tre kostnadsvärden kan kopplas till varje lagerartikel:

- **Senaste utleverans** – den senaste utleveranskostnaden som tilldelades innan lagret blev negativt
- **Aktiv kostnad** – den senaste kostnad som aktiverades i en kostnadsversion
- **Artikelpris** – den kostnad som angetts för den frisläppta produkten

För att avgöra vilka av dessa kostnadsvärden som ska användas vid beräkningar av rörligt genomsnitt använder systemet en _reservkostnadssekvens_ för att fastställa prioritetsordningen för värdena. Om det prioriterade kostnadsvärdet inte är tillgängligt använder systemet nästa önskade värde, och så vidare.

I tidigare versioner av Microsoft Dynamics 365 Supply Chain Management använde systemet en fast reservkostnadssekvens (_senaste utleverans – aktiv kostnad – artikelpris_). I version 10.0.11 är den här sekvensen fortfarande standardsekvensen. Du kan emellertid också aktivera en funktion som gör att du kan välja bland tre tillgängliga reservkostnadssekvenser. Den här funktionen kan vara särskilt användbar för organisationer som regelbundet använder negativa lagervärden.

Om du vill göra väljaren för den tillgängliga reservkostnadssekvenser måste du (eller en administratör) använda [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera funktionen med namnet _rörligt genomsnitt för reservkostnadssekvenser_.

Följ de här stegen om du vill välja en reservkostnadssekvenser för beräkning av rörligt genomsnitt.

1. Öppna sidan **Parametrar**.
2. På fliken **Lagerredovisning** i avsnittet **Rörligt genomsnitt** ange fältet **Reservkostnadssekvens** till ett av följande värden:

    - **Senaste utleverans – aktiv kostnad – artikelpris** – den här sekvensen är standardsekvens. Det är samma sekvens som används om funktionen för _Rörligt genomsnitt, reservkostnadssekvens_ inte är aktiverad.
    - **Aktiv kostnad – senaste utleverans**
    - **Aktiv kostnad – ett artikelpris** – organisationer kan uppleva prestandaproblem om de använder affärsprocesser där lagret regelbundet blir negativt och samtidigt är transaktionsvolymen hög. Den här inställningen kan hjälpa till att minska prestandaproblemen.

![Parametrarna lagerredovisning](media/inventory-accounting-parameters.png "Parametrarna lagerredovisning")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]