---
title: Översikt över farliga material
description: Det här ämnet innehåller en översikt över funktioner som är relaterade till hantering och dokumenterar farligt material vid hantering av produktinformation och lagerstyrning.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 227111f4703d9dc381270382dcb796874d7de937
ms.sourcegitcommit: c009ec75f53872272f11c92a1ce81a391e3845a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/18/2020
ms.locfileid: "3699661"
---
# <a name="hazardous-materials-overview"></a>Översikt över farliga material

[!include [banner](../includes/banner.md)]

För att fortsätta att följa sjöfarts- och transportbestämmelserna måste organisationer som skickar material som klassificeras som farligt gods inkludera ytterligare pappersarbete med sina transporter. Med hjälp av funktionen för farliga material kan kunderna lagra information som är relaterad till frisläppta artiklar. Denna information kan sedan användas för att förbereda leveransdokumentationen. En organisation som levererar farligt gods måste ha egna processer och procedurer för hantering av leveransprocessen. Microsoft Dynamics 365 Supply Chain Management är bara ett verktyg som kan hjälpa dig att skapa de dokument som krävs.

Följande diagram illustrerar de steg som behövs för att ställa in och använda funktionen för farliga material.

![Inställning och användning av funktionerna för farliga material](media/hazmat-overview.png "Inställning och användning av funktionerna för farliga material")

Funktionen för farliga material ställs in i produktinformationshantering och innehåller dokument som kan skrivas ut genom lagerstyrning. Därför är dessa områden i stort sett de två huvudområdena där du kommer att granska, ställa in och använda funktionens funktion:

- **Produktinformationshantering** – Ställ in koder som kan användas för frisläppta produkter.
- **Lagerstyrning** – arbeta med ytterligare leveransdokument som ska skrivas ut för försändelser.

> [!IMPORTANT]
> Funktionerna för farliga material i Supply Chain Management tillhandahåller en samling användbara produktinformationsfält och tillhörande funktioner som kan hjälpa dig att registrera och referera till information som rör dina farliga produkter. Dessa funktioner kan också hjälpa dig att utforma och skriva ut leveransdokument som innehåller en del av samma information om något farligt material som du levererar. Systemet gör dock inte att du automatiskt följer alla tillämpliga regler i ditt land eller din region. Även om dessa verktyg är avsedda att hjälpa dig att följa gemensamma regler är de varken tillräckliga i sig eller garanterat. Organisationen är ansvarig för att vara medveten om alla tillämpliga regler och vidta alla nödvändiga åtgärder för att följa dem.

## <a name="product-information-management"></a>Produktinformationshantering

I produktinformationshantering finns det ett intervall med inställningstabeller där du kan lägga till den referensinformation som finns i listor över farligt gods för väg-, flyg- och sjöfrakt.

Följande gemensamma förordningar refererades när denna funktion utvecklades:

- **ADR** – förordningar som rör internationell transport av farligt gods på väg
- **CFR 49** – förordningar i USA för transport av farligt gods
- **IMDG** – internationella koden för sjötransport av farligt gods (IMDG)
- **IATA** – reglerna för farligt gods i IATA (International Air Transport Association)

Varje uppsättning regler innehåller standardiserade listor över farligt gods och referenskoder. Supply Chain Management innehåller därför en referens tabell för de vanliga koderna i listorna. Varje lista har också vissa unika koder som kan definieras.

Mer information om hur du ställer in regler och värden för farliga material och hur du tilldelar värden till relevanta produkter finns i följande avsnitt:

- [Ställa in farliga material](hazmat-setup.md)
- [Farliga material i produkter, order, leveranser och laster](hazmat-items.md)

## <a name="warehouse-management"></a>Lagerstyrning

När du förbereder en leverans i lagerstyrning kommer du att kunna skriva ut flera nya rapporter som använder informationen som du ställer in i produktinformationshantering. Mer information om tillgängliga rapporter och hur du använder dem finns i [frågor och rapporter om farliga material](hazmat-reports.md).
