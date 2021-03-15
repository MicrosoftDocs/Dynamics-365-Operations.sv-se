---
title: Inkludera behållarens vikt och volym vid lastning
description: Detta avsnitt beskriver hur du konfigurerar och tillämpar olika funktioner för att inkludera containervikt och -volym på olika laster.
author: pjacobse
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b8fb40a0fe1606b856f58f5bc517c7f1aff85e4d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977523"
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