---
title: Problemtyper för avvikelser
description: I detta ämne beskrivs hur du skapar och använder problemtyper för avvikelser.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 742edec8570610efe41a2c627efd1df586e0733e
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022166"
---
# <a name="problem-types-for-nonconformances"></a>Problemtyper för avvikelser

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du skapar och använder problemtyper för avvikelser.

Du använder sidan **Problemtyper** för att definiera en klassificering av de kvalitetsproblem som kan uppstå i de olika avvikelsetyperna. För varje problemtyp som du skapar måste du ange vilka typer av avvikelser som problemtypen kan användas med. Du kan ställa in följande avvikelsetyper:

- **Intern** – Avvikelser av den här typen är relaterade till lagerbehållning (till exempel kvalitetsorder eller karantänorder).
- **Kund** – Avvikelseer av den här typen är relaterade till försäljningsorder.
- **Leverantör** – Avvikelser av den här typen är relaterade till inköpsorder.
- **Servicebegäran** – Avvikelser av den här typen är relaterade till serviceorder.
- **Produktion** – Avvikelser av den här typen är relaterade till batch- eller produktionsorder.
- **Framställning av samprodukt** – Avvikelser av den här typen är relaterade till batchorder för samprodukter.

När du skapar en ny problemtyp väljer du **Avvikelsetyper** i åtgärdsfönstret om du vill skapa en lista över en eller flera avvikelsetyper som är behöriga för problemtypen. Till exempel kan en problemtyp som är relaterad till en defektkod gälla för alla avvikelsetyper. En problemtyp som rör kundklagomål kan dock endast gälla avvikelsetyperna **Kund** och **Serviceförfrågan**.

## <a name="examples-of-problem-types"></a>Exempel på problemtyper

Här följer några exempel på scenarier för problemtyper som kan användas med de olika avvikelsetyperna:

- **Kund:** En kund har lämnat in ett klagomål, en kund har lämnat in en retur eller också har kvalitetsspecifikationer inte uppfyllts.
- **Leverantör:** Produkten har skadats, kvalitetsspecifikationerna har inte uppfyllts, eller också har fel produkt inkommit.
- **Serviceförfrågan:** Kvalitetsspecifikationer har inte uppfyllts, en kund har lämnat in ett klagomål, eller maskinunderhåll krävs.
- **Produktion:** Kvalitetsspecifikationer har inte uppfyllts, maskinunderhåll krävs eller produkten har skadats.
- **Framställning av samprodukt:** Kvalitetsspecifikationer har inte uppfyllts, maskinunderhåll krävs eller produkten har skadats.

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a>Skapa en problemtyp och tilldela den till avvikelsetyper

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetshantering \> Problemtyper**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Problemtyp** – Ange ett unikt ID eller namn för problemtypen.
    - **Beskrivning** – Ange en detaljerad beskrivning av problemtypen.

1. Välj **Avvikelsetyper** i åtgärdsfönstret när den nya raden är vald.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ställ sedan in fältet **Avvikelsetyp** för den nya raden till den avvikelsetyp som du vill tillåta för problemtypen.
1. Upprepa föregående steg för varje ytterligare avvikelsetyp som du vill auktorisera för problemtypen.
1. Stäng sidorna.

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
