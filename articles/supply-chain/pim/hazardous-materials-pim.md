---
title: Farliga material
description: Det här avsnittet innehåller information om dokument och information om farliga material som lagras i din miljö.
author: lachlancashMS
manager: AnnBe
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 443d2eb545b2b7592e27ae037009720db0a71997
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092555"
---
# <a name="hazardous-materials"></a>Farliga material

[!include [banner](../includes/banner.md)]

Information om farligt material ställs in i produktinformationshantering. Modulen innehåller också dokument som kan skrivas ut via lagerstyrning.

När du levererar material som klassificeras som farligt gods, måste ytterligare pappersarbete inkluderas i försändelserna. Med hjälp av funktionen för farliga material kan du informera kunder om klassificeringsinformation och relatera den till att frisläppa artiklar. Denna information kan sedan användas för att förbereda leveransdokumentationen.

> [!IMPORTANT]
> För att hantera transporter av farligt gods kan du med hjälp av Microsoft Dynamics 365 Supply Chain Management ställa in ytterligare referensinformation om produkter. Du kan också ställa in fler leveransdokument. Systemet följer dock inte automatiskt upp dina lands- eller regionsregler. I stället är det ett verktyg som kan hjälpa ditt övergripande program.

Innan du kan använda den här funktionen, krävs följande inställningar:

- **Produktinformationshantering:** Ställ in koder som kan användas för frisläppta produkter.
- **Lagerstyrning:** Använd ytterligare leveransdokument för att skriva ut leveransinformation.

## <a name="product-information-management"></a>Produktinformationshantering

I produktinformationshantering finns det ett intervall med inställningstabeller där du kan lägga till den referensinformation som finns i listor över farligt gods för väg-, flyg- och sjöfrakt.

Här är några av de regler som ofta hänvisas till:

- **ADR** – förordningar som rör internationell transport av farligt gods på väg
- **CFR 49** – förordningar i USA för transport av farligt gods
- **IMDG** – internationella koden för sjötransport av farligt gods (IMDG)
- **IATA** – reglerna för farligt gods i IATA (International Air Transport Association)

Var och en av dessa förordningar har en lista över farligt gods som omfattar referenskoder. Förteckningarna över varje transporttyp kombineras på delade internationella klassificeringar. Supply Chain Management innehåller en referens tabell för de delade koderna i listorna. Varje lista har också vissa unika koder som kan definieras.

Börja med att konfigurera den här informationen genom att skapa en regel som du kan använda för att konfigurera de ursprungliga parametrarna.

## <a name="warehouse-management"></a>Lagerstyrning

När en försändelse har förberetts kan flera nya rapporter skrivas ut. I dessa rapporter används den information som du ställer in i produktinformationshantering.
