---
title: Funktioner för avvikelser
description: I detta ämne beskrivs hur du skapar och använder funktioner för avvikelser.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fda4aaadd5a2d9e6093b767d83a9187a970bf14c60f089f43b1b98a26cf0ac76
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739836"
---
# <a name="operations-for-nonconformances"></a>Funktioner för avvikelser

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du skapar och använder funktioner för avvikelser.

Du kan använda sidan **Funktioner** för att definiera klassificeringen av det arbete som kan utföras för en godkänd avvikelse. När en relaterad funktion tilldelas till en avvikelse kan du definiera detaljerad information om tillhörande material, arbetstid och avgifter som krävs för att funktionen ska kunna genomföras. Systemet använder denna information för att beräkna en uppskattad kostnad för funktionen. Den detaljerade informationen och de uppskattade kostnaderna anges i referenssyfte. Relaterade kvalitetsoperationer skiljer sig från de operationer som kan definieras för ett produktionsflöde.

> [!NOTE]
> Även om du kan spåra kostnader, tid och artiklar som används i en funktion som hör till en avvikelse är de data som du anger bara information. Datan integreras inte automatiskt med redovisningen, lagerredovisningen eller modulen **Tid och närvaro**.

## <a name="examples-of-operations"></a>Exempel på funktioner

Du arbetar för ett tillverkningsföretag. En avvikelse har skapats och godkänts för artiklar som misslyckats i ett kvalitetstest. En korrigering har skapats för att visa att problemet berodde på ett trasigt lager på en maskin. Flera steg krävs för att ersätta lagret, och ansvarsområdet för varje funktion spåras. Följande steg kan till exempel krävas:

1. Produktionsraden stoppas och rensningsrutinen utförs.
1. Underhållspersonal ersätter lagret.
1. Kvalitetssäkringspersonal inspekterar maskinen innan den återaktiveras.

I det här exemplet kan följande funktioner skapas i syfte att representera det arbete som måste utföras:

- Stoppa produktionsraden.
- Rensa produktionsraden.
- Utföra maskinunderhåll.
- Inspektera maskinen.

## <a name="create-an-operation"></a>Skapa en funktion

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetshantering \> Funktioner**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Funktion** – Ange ett unikt ID eller namn för funktionen.
    - **Beskrivning** – Ange en detaljerad beskrivning av funktionen.
    - **Typ** – Om åtgärden bara kan användas för avvikelser som är relaterade till en viss ordertyp väljer du ordertypen (*inköpsorder* eller *försäljningsorder*).

1. Stäng sidan.

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvalitetshantering – översikt](quality-management-processes.md)
- [Aktivera kvalitets- och avvikelsehantering](enable-quality-management.md)
- [Skapa och bearbeta avvikelser](tasks/create-process-non-conformance.md)
- [Medarbetare som ansvarar för godkännande av avvikelser](quality-responsible-workers.md)
- [Karantänzoner för avvikelser](quality-quarantine-zones.md)
- [Diagnostyper för avvikelser](quality-diagnostic-types.md)
- [Kvalitetsavgifter för avvikelser](quality-charges.md)
- [Problemtyper för avvikelser](quality-operations.md)
- [Kvalitetsstyrning för lagerprocesser](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
