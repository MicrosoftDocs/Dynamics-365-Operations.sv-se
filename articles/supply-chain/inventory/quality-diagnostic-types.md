---
title: Diagnostyper för avvikelser
description: I det här ämnet beskrivs hur du använder och skapar diagnostyper som kan användas med avvikelser.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: edaa3a8b5c6446f039f33589166d832dcd9d0b9a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580946"
---
# <a name="diagnostic-types-for-nonconformances"></a>Diagnostyper för avvikelser

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du använder och skapar diagnostyper som kan användas med avvikelser.

Du kan använda sidan **Diagnostyper** för att definiera klassificeringen av diagnosåtgärder. När du sedan skapar en korrigering för en avvikelse väljer du en diagnos. En korrigering specificerar vilken typ av diagnosåtgärd som ska vidtas vid en godkänd avvikelse, och vem som ska genomföra åtgärden. Även det begärda slutförandedatumet och det planerade slutförandedatumet anges.

## <a name="examples-of-diagnostic-types"></a>Exempel på diagnostyper

Du arbetar för ett tillverkningsföretag, och flera artiklar har misslyckats i kvalitetstester. Artiklarna flyttas till ett karantänområde och markeras som avvikelseprodukter. En avvikelsepost skapas i Microsoft Dynamics 365 Supply Chain Management i syfte att spåra informationen genom ut ärendelösning.

I det här fallet uppstår kvalitetsproblemen eftersom lager i maskinen som paketerar artiklarna har drabbats av slitage och överhettas. Korrigeringen av det här problemet är att byta ut delarna i maskinen.

När du konfigurerar diagnostyperna kan du skapa flera poster som vardera representerar olika typer av problem som maskinen kan ha. Du kan också skapa en allmän diagnostyp som representerar maskinreparationer.

## <a name="create-a-diagnostic-type"></a>Skapa en diagnostyp

1. Gåtill **Lagerhantering \> Inställningar \> Kvalitetshantering \> Diagnostyper**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Diagnos** – Ange ett unikt ID eller namn för diagnostypen.
    - **Beskrivning** – Ange en detaljerad beskrivning av diagnostypen.

1. Stäng sidan.

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvalitetshantering – översikt](quality-management-processes.md)
- [Aktivera kvalitets- och avvikelsehantering](enable-quality-management.md)
- [Medarbetare som ansvarar för godkännande av avvikelser](quality-responsible-workers.md)
- [Karantänzoner för avvikelser](quality-quarantine-zones.md)
- [Problemtyper för avvikelser](quality-problem-types.md)
- [Kvalitetsavgifter för avvikelser](quality-charges.md)
- [Funktioner för avvikelser](quality-operations.md)
- [Kvalitetsstyrning för lagerprocesser](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
