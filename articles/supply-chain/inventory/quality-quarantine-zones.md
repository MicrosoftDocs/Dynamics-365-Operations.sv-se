---
title: Karantänzoner för avvikelser
description: I detta ämne beskrivs hur du skapar och använder karantänzoner för avvikelser.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80f4b9dfc7882af4570bf1908784b8d114396402
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021814"
---
# <a name="quarantine-zones-for-nonconformances"></a>Karantänzoner för avvikelser

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du skapar och använder karantänzoner för avvikelser.

Du använder sidan **Karantänzoner** för att definiera zoner som kan tilldelas avvikelser. När du skapar en avvikelse kan du ange fälten **Karantänzon** och **Karantänzon** på fliken **Allmänt** på sidan **Avvikelser**. Fältet **Karantänzon** anger vanligtvis området eller platsen där artikeln finns. I fältet **Karantäntyp** definieras artikeln som antingen *Begränsad användning* eller *Oanvändbar*.

När du skriver ut en avvikelse- eller korrigeringsrapport för en avvikelse kan du visa karantänzonen där artikeln finns.

Du kan även skriva ut en avvikelsetagg för en avvikelse. Denna rapport anger tilldelad karantänzon samt information om användning i syfte att ge vägledning om hur defekta material bör hanteras. Karantänzonerna kan överensstämma med lagerplatser eller funktionsresurser.

## <a name="examples-of-quarantine-zones"></a>Exempel på karantänzoner

### <a name="example-1"></a>Exempel 1

Du arbetar på ett tillverkningsföretag för elektronik som producerar och distribuerar TV-apparater, högtalare och mediaspelare. I detta fall kan du konfigurera en karantänzon som representerar varje typ av produkt.

### <a name="example-2"></a>Exempel 2

Tre behållare och två ställ används för att lagra artiklar som är avvikelser. I det här fallet kan du konfigurera fem karantänzoner, en för respektive behållare och ställ.

## <a name="create-a-quarantine-zone"></a>Skapa en karantänzon

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetshantering \> Karantänzoner**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Karantänzon** – Ange ett unikt ID eller namn för karantänzonen.
    - **Beskrivning** – Ange en detaljerad beskrivning av karantänzonen.

1. Stäng sidan.

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvalitetshantering – översikt](quality-management-processes.md)
- [Aktivera kvalitets- och avvikelsehantering](enable-quality-management.md)
- [Medarbetare som ansvarar för godkännande av avvikelser](quality-responsible-workers.md)
- [Problemtyper för avvikelser](quality-quarantine-zones.md)
- [Diagnostyper för avvikelser](quality-diagnostic-types.md)
- [Kvalitetsavgifter för avvikelser](quality-charges.md)
- [Funktioner för avvikelser](quality-operations.md)
- [Kvalitetsstyrning för lagerprocesser](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
