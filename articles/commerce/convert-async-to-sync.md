---
title: Konvertera asynkrona kunder till synkrona kunder
description: I denna artikel beskrivs hur du konverterar asynkrona kunder till synkrona kunder i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: b442bfc0685706359771e4d9e2729565d3652a60
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278203"
---
# <a name="convert-asynchronous-customers-to-synchronous-customers"></a>Konvertera asynkrona kunder till synkrona kunder

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du konverterar asynkrona kunder till synkrona kunder i Microsoft Dynamics 365 Commerce.

För att konvertera asynkrona kunder till synkrona kunder följer du stegen nedan.

1. I Commerce headquarters kör du **P-jobbet** för att skicka de asynkrona kunderna till Commerce headquarters.
1. Kör jobbet **Synkronisera kunder och affärspartners från asynkrona läge** för att skapa kundkonto-ID. (Det här jobbet hette tidigare **Synkronisera kunder och affärspartner från asynkront läge**.)
1. Kör **1010** jobbet om du vill synkronisera de nya kundkonto-ID till kanalerna.

Om en order refererar till en asynkron kund eller adress som ännu inte har synkroniserats med Commerce headquarters synkroniseras kunden eller adressen som en del av batchjobbet **Synkronisera order**. Om en hämtköpstransaktion refererar till en asynkron kund eller adress, synkroniseras kunden eller adressen innan bokföring i slutet av dagen (EOD).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundhantering i butiker](customer-mgmt-stores.md)

[Skapningsläge asynkron kund](async-customer-mode.md)

[Kundattribut](dev-itpro/customer-attributes.md)

[Offline uteslutande av data](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
