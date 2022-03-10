---
title: Avgifter för avvikelsefunktioner
description: I det här ämnet beskrivs hur du skapar kvalitetsavgifter som kan användas med funktioner för en avvikelse.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac3306f3f9215ab03f408b8026f335dcf496515a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580970"
---
# <a name="charges-for-nonconformance-operations"></a>Avgifter för avvikelsefunktioner

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du skapar kvalitetsavgifter som kan användas med funktioner för en avvikelse.

Du kan använda sidan **Kvalitetsavgifter** för att definiera de avgiftstyper som kan läggas till funktionerna för en avvikelse. Med avgifter kan du spåra detaljer om avgifter som du är skyldig en kund för avvikelseprodukter, eller som en leverantör är skyldig dig för avvikelseprodukter som du har fått. Du kan också använda avgifter för att spåra kostnader som krävs för att externa leverantörer eller tjänster ska utföra en funktion.

## <a name="examples-of-quality-charges"></a>Exempel på kvalitetsavgifter

Du arbetar för ett tillverkningsföretag. Ditt företag har kontrakt med flera leverantörer. Dessa kontrakt beskriver standarder för leverans i tid, skador och produktkvalitet för artiklar. På samma sätt har flera av dina kunder kontrakt med ditt företag om returer, skador och produktkvalitet.

En avgiftsstruktur definieras för varje situation och anges i kontraktet. Du kan konfigurera kvalitetsavgifter för att beskriva de olika typerna av avgifter, till exempel *Skador*, *Sen leverans* och *Kvalitet*. När du sedan skapar en avvikelse lägger du till en eller flera funktioner. För varje funktion väljer du **Tillägg** om du vill definiera detaljer om avgifterna.

## <a name="create-a-quality-charge"></a>Skapa en kvalitetsavgift

1. Gå till **Lagrhantering \> Inställningar \> Kvalitetshantering \> Kvalitetsavgifter**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Avgiftskod** – Ange ett unikt ID eller namn för kvalitetsavgiften.
    - **Beskrivning** – Ange en detaljerad beskrivning av kvalitetsavgiften.

1. Stäng sidan.

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a>Lägga till en kvalitetsavgift för en åtgärd för en avvikelse

Mer information om hur du lägger till funktioner för en avvikelse och tillämpar avgifter på dem finns i [Funktioner för avvikelser](quality-operations.md).

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvalitetshantering – översikt](quality-management-processes.md)
- [Aktivera kvalitets- och avvikelsehantering](enable-quality-management.md)
- [Medarbetare som ansvarar för godkännande av avvikelser](quality-responsible-workers.md)
- [Karantänzoner för avvikelser](quality-quarantine-zones.md)
- [Diagnostyper för avvikelser](quality-diagnostic-types.md)
- [Kvalitetsavgifter för avvikelser](quality-charges.md)
- [Funktioner för avvikelser](quality-operations.md)
- [Kvalitetsstyrning för lagerprocesser](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
