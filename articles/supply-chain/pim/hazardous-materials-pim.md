---
title: Farliga material
description: Det här avsnittet innehåller information om dokument och information om farliga material som lagras i din miljö.
author: lachlancashMS
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: d27ec5b65cc607c22d97c1dc44bb573bc2772611
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243187"
---
# <a name="hazardous-materials"></a>Farliga material

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Information om farligt material ställs in i produktinformationshantering. Modulen innehåller också dokument som kan skrivas ut via lagerstyrning.

När du levererar material som klassificeras som farligt gods, måste ytterligare pappersarbete inkluderas i försändelserna. Med hjälp av funktionen för farliga material kan du informera kunder om klassificeringsinformation och relatera den till att frisläppa artiklar. Denna information kan sedan användas för att förbereda leveransdokumentationen.

> [!IMPORTANT]
> Funktionerna för farliga material i Microsoft Dynamics 365 Supply Chain Management tillhandahåller en samling användbara produktinformationsfält och tillhörande funktioner som kan hjälpa dig att registrera och referera till information som rör dina farliga produkter. Dessa funktioner kan också hjälpa dig att utforma och skriva ut leveransdokument som innehåller en del av samma information om något farligt material som du levererar. Systemet gör dock inte att du automatiskt följer alla tillämpliga regler i ditt land eller din region. Även om dessa verktyg är avsedda att hjälpa dig att följa gemensamma regler är de varken tillräckliga i sig eller garanterat. Organisationen är ansvarig för att vara medveten om alla tillämpliga regler och vidta alla nödvändiga åtgärder för att följa dem.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]