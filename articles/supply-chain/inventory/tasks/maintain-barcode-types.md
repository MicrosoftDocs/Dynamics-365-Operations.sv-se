---
title: Underhåll streckkodstyper
description: I den här proceduren visas hur du ställer in en ny streckkodsdefinition som sedan kan användas som en del av plocklistarapporten.
author: perlynne
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4102f8036c0aede7c8a2adcaa9b8799a71ac7ada
ms.sourcegitcommit: 696796ca5635863850ae9ef16fc1fb0fc46ce8f0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/28/2021
ms.locfileid: "7441299"
---
# <a name="maintain-bar-code-types"></a>Underhåll streckkodstyper

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du ställer in en ny streckkodsdefinition som sedan kan användas som en del av plocklistarapporten. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data. Om du använder USMF, kan du använda exempelvärdena som visas. Dessa uppgifter utförs vanligtvis av en lagerchef.

1. Gå till **Streckkoder**.
1. Välj **Ny**.
1. I fältet **Streckkodsinställningar** anger du ett värde.
1. I fältet **Beskrivning** anger du ett värde.
1. Välj ett alternativ i fältet **Streckkodstyp**.
    * Om du använder USMF kan du välja Code 39.
1. I fältet **Mask-ID** anger du streckkodsmaskens ID. Streckkodsmasker används för att skapa streckkoder och snabbt identifiera streckkoder som skannas till kassasystemet. Mer information finns [i Ställa in streckkodsmasker](../../../commerce/set-up-bar-code-masks.md).
1. Ange ett nummer i fältet **Storlek**.
1. Ange ett värde i fältet **Maximal längd**.
1. Välj **Spara**.
1. Stäng sidan.
1. Gå till **Parametrar oför lager- och lagerstyrning**.
1. I fältet **Streckkodsinställningar** anger du eller väljer ett värde.
    * Välj den streckkodskonfiguration du skapade tidigare, men tänk på att streckkodformatet måste matcha formatet för den unika identifieraren för posttypen som används i processen. För exempelvis plockflöden ska streckkodformatet matcha formatet för plockflödereferensen, som vanligtvis är en nummerserie.  
1. Välj **Spara**.
1. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
