---
title: Inkludera behållarens vikt och volym vid lastning
description: Denna artikel beskriver hur du konfigurerar och tillämpar olika funktioner för att inkludera behållarvikt och -volym på olika laster.
author: Weijiesa
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66dc84171f8b175476f37f736489d3d83cacfe57
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897412"
---
# <a name="include-container-weight-and-volume-on-load"></a>Inkludera behållarens vikt och volym vid lastning

[!include [banner](../includes/banner.md)]

Funktionen för att inkludera containervikt och -volym på en last ger en tydlig uppfattning om totalvikt och totalvolym för containers och varor som ska ingå i en last.

En last innehåller en enda leverans eller flera leveranser, och dessa leveranser innehåller specifika varor som tillhör en enda försäljningsorder eller flera försäljningsorder. Varorna förvaras i en container, och containrarna lastas på en last. Varor utanför en container lan också ingå i en last. Baserat på dessa villkor beräknar systemet värden för vikt och volym på lasten, detta genom att bedöma vikt och volym för såväl container som varor.

Om beräknade värden inte är exakta kan du justera dem genom att ange faktiska värden för lastens vikt och volym. Värden för vikt och volym används inom processerna för transporthantering. Värdena används exempelvis i arbetsstationen för avgiftsvägar, där de hjälper till att definiera avgifter och väg för laster, och de används också för distributörer och inloggning av förare.

## <a name="where-it-applies"></a>Tillämpning

Funktionen för att inkludera containervikt och -volym på en last gäller i processer för transporthantering, exempelvis arbetsstationen för avgiftsväg, distributörer och inloggning av förare.

## <a name="how-it-is-set-up"></a>Inställningar

Antalet containrar som bör övervägas för en last beräknas baserat på containerns vikt och volym, samt på den procentandel av containern som används.

-   Klicka på **Lagerhantering** \> **Inställningar** \> **Container** \> **Containertyper** om du vill ange vikt och volym för en container.

-   Klicka på **Lagerhantering** \> **Inställningar** \> **Containrar** \> **Behållargrupper** och ange sedan ett värde i fältet **Nyttjandedel av behållare i procent** om du vill ange nyttjandeandelen för en behållare.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]