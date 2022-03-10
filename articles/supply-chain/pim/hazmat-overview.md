---
title: Översikt över farliga material
description: Det här ämnet innehåller en översikt över funktioner som är relaterade till hantering och dokumenterar farligt material vid hantering av produktinformation och lagerstyrning.
author: t-benebo
ms.date: 06/10/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: cfea2cd6a2699bdf2a14de72a8bdeb3e8cd32a17
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986286"
---
# <a name="hazardous-materials-overview"></a>Översikt över farliga material

[!include [banner](../includes/banner.md)]

För att fortsätta att följa sjöfarts- och transportbestämmelserna måste organisationer som skickar material som klassificeras som farligt gods inkludera ytterligare pappersarbete med sina transporter. Med hjälp av funktionen för farliga material kan kunderna lagra information som är relaterad till frisläppta artiklar. Denna information kan sedan användas för att förbereda leveransdokumentationen. En organisation som levererar farligt gods måste ha egna processer och procedurer för hantering av leveransprocessen. Microsoft Dynamics 365 Supply Chain Management är bara ett verktyg som kan hjälpa dig att skapa de dokument som krävs.

Följande diagram illustrerar de steg som behövs för att ställa in och använda funktionen för farliga material.

![Konfigurering och användning av funktionerna för farliga material.](media/hazmat-overview.png "Inställning och användning av funktionerna för farliga material")

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]