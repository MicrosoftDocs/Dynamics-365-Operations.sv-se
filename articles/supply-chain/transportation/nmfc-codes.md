---
title: National Motor Freight Classification (NMFC)-koder
description: I denna artikel beskrivs hur du arbetar med NMFC-koder (National Motor Freight Classification) i Microsoft Dynamics 365 Supply Chain Management
author: Weijiesa
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: c173057b8e1357790e780469c5806afb857be62a
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838346"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a>National Motor Freight Classification (NMFC)-koder

[!include [banner](../includes/banner.md)]

Med NMFC-koder (National Motor Freight Classification) kan du klassificera artiklar som kan levereras. NMFC-koden är en beteckning som används för att gruppera varor. Med den kan transportföretag utvärdera varor för leverans genom att klassificera artiklar utifrån hänsyn till exempelvis lastbilsegenskaper, lastningsproblem, hanteringsproblem och ömtålighet. Varor grupperas i en av 18 fraktklasser med ett intervall av värden mellan 50 och 500. Klassen som en vara grupperas i baseras på en utvärdering av fyra transportegenskaper: densitet, stuvbarhet, hantering och skuld. Tillsammans fastställer dessa egenskaper artikelns transportbarhet.

En NMFC-kod associeras med alla artiklar som är mindre än "truckload" (LTL). Till exempel kan en bärbar dator ha tilldelats ett NMFC-nummer som har klassen 2.5, medan eluttag kan tilldelas en NMFC-klass som är 65.

Denna funktion kan hjälpa medarbetare att använda NMFC-koder för att klassificera LTL-leveransartiklar. Nedan följer några exempel:

- Om ditt företag inkluderar en fraktbeskrivning på fraktsedeln (Bill of Lading, BOL), kommer transportföretaget att ha en uppfattning om vad frakten är. Frakt är en viktig klassificering eftersom många transportföretag bygger sin verksamhet på de typer av frakt man levererar.
- Denna klassificering kan vara viktig för ditt företag eftersom den används för att bestämma kostnaden för en viss last.
- Ditt företag kan identifiera lönsamhet i ett LTL-logistik- och transportföretag.

I denna artikel bekrivs hur du arbetar med NMFC-koder i Microsoft Dynamics 365 Supply Chain Management.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan skapa NMFC-koder måste du konfigurera alla LTL-fraktklasser som måste mappas till dem. LTL-fraktklasser representerar artikelkategorier, medan NMFC-koder rör specifika varor i var och en av de 18 fraktklasserna. Mer information om hur du arbetar med LTL-klasser finns i [Klasser som understiger truckload (LTL)](ltl-class.md).

## <a name="create-an-nmfc-code"></a>Skapa en NMFC-kod

Gör så här om du vill skapa en NMFC-kod:

1. Gör något av följande:

    - Gå till **Lagerstyrning \> Inställningar \> Lager \> NMFC-koder**.
    - Gå till **Transporthantering \> Inställningar \> Transportstandarder \> NMFC-koder**.

1. Välj **Ny** för att skapa en NMFC-kod. Ange sedan följande fält:

    - **NMFC-kod** – Ange NMFC-koden för varutypen.
    - **Namn** – Ange ett namn för NMFC-koden.
    - **LTL-klass** – Välj den LTL-klass som är associerad med NMFC-koden.
    - **Hanteringsenhet för BOL** – Definiera standardhanteringstyp för försändelsen.

## <a name="example-set-up-nmfc-codes"></a>Exempel: Konfigurera NMFC-koder

Följande exempel visar hur du konfigurerar två olika NMFC-koder som kan användas med olika produkter.

1. Gå till **Warehouse Management \> inställningar \> lager \> NMFC-koder** eller **transporthantering \> Setup \> transportstandarder \> NMFC-koder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ställ in följande värden på denna nya rad:

    - **NMFC-kod:** *92.5*
    - **Namn:** *Datorer*
    - **LTL-klass:** *92.5*
    - **Hanteringsenhet för BOL:** *Enhet*

1. Klicka på **Spara** i åtgärdsfönstret.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ställ in följande värden på denna nya rad:

    - **NMFC-kod:** *125*
    - **Namn:** *Telefoner*
    - **LTL-klass:** *125*
    - **Hanteringsenhet för BOL:** *Enhet*

1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="additional-resources"></a>Ytterligare resurser

- [Mindre än lastbilsklasser (LTL)](ltl-class.md)
- [Skapa en fraktsedel](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
