---
title: Förbrukningsavskrivning
description: Den här avsnittet innehåller en översikt över förbrukningsmetoden för avskrivning.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e78e2481724aede93ecb997d95a0ef8032618bbd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989037"
---
# <a name="consumption-depreciation"></a>Förbrukningsavskrivning

[!include [banner](../includes/banner.md)]

Den här avsnittet innehåller en översikt över förbrukningsmetoden för avskrivning.

Om du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **Förbrukning** i fältet **Metod** på sidan **Avskrivningsprofiler** tilldelas anläggningstillgångar till avskrivningsprofilen utifrån deras användning. Det är inte nödvändigt att ställa in procenttal och intervaller på sidan **Avskrivningsprofiler**. När du har skapat en avskrivningsprofil som använder förbrukningsmetoden kan du ställa in metoden på olika sätt.

## <a name="set-up-and-use-consumption-depreciation"></a>Ställa in och använda förbrukningsavskrivning
1.  Skapa avskrivningsprofilen på sidan **Avskrivningsprofiler**. För förbrukningsberäkningar måste avskrivningsprofilen ha ett ID och ett namn, och **Förbrukning** måste väljas i fältet **Metod**.
2.  På sidan **Förbrukningsfaktorer** ställer du in förbrukningsfaktorer. Varje förbrukningsfaktor måste ha ett ID och ett namn och en förbrukningsfaktor som anges som antingen en kvantitet eller ett procenttal.
3.  På sidan **Förbrukningsenheter** ställer du in förbrukningsenheter. Varje förbrukningsenhet måste ha ett ID och ett namn. Avskrivningsenheter används för att beräkna förbrukningsavskrivningen på sidan **Förbrukningsavskrivning**. Exempel på enheter är kilometer (km), kilo (kg) och timme.
4.  På sidan **Anläggningstillgångar** ställer du in enskilda anläggningstillgångar. För varje anläggningstillgång väljer du värdemodeller och avskrivningsregler som har avskrivningsprofiler. Du måste ställa in värdemodeller och avskrivningsregler för förbrukningsavskrivning om vissa av dina anläggningstillgångar använder avskrivningsprofiler som baseras på förbrukningsmetoden. Den här inställningen görs antingen på fliken **Avskrivning** på sidan **Värdemodeller** eller på snabbfliken **Allmänt** på sidan **Avskrivningsprofil**. Du kan använda samma värdemodell för flera anläggningstillgångar. Avskrivningsprofiler är en del av värdemodellen eller avskrivningsregeln som du väljer för varje anläggningstillgång. Du kan inte lägga till eller ändra avskrivningsprofiler direkt på sidan **Anläggningstillgångar**. Du kan endast ändra avskrivningsprofiler på sidan **Avskrivningsregler**.
5.  Ange information i följande fält på sidan **Värdemodeller** eller sidan **Avskrivningsregler**, i fältgruppen **Förbrukningsavskrivning**:
    -   Förbrukningsfaktor
    -   Enhet
    -   Enhetsavskrivning
    -   Uppskattad förbrukning

    Fältet **Bokförd förbrukning** visar förbrukningsavskrivningen, i enheter, som redan har bokförts antingen för kombinationen av anläggningstillgången och värdemodellen eller för avskrivningsregeln. Du kan inte att uppdatera värdet i det här fältet.

## <a name="examples"></a>Exempel
### <a name="example-1"></a>Exempel 1

Följande förbrukningsfaktor är inställd för 31 januari:

-   Kvantiteten är 1 000.
-   Enhetsavskrivningspriset som anges för anläggningstillgången är 1,5.

Avskrivningsförslaget den 31 januari är som följer: Kvantitet × Enhetsavskrivning 1 000 × 1,5 = 1 500 Om faktorn som anges för anläggningstillgången är en procentfaktor, multipliceras kvantiteten som beräknas i fältet **Uppskattad förbrukning** för värdemodellen för anläggningstillgång med procenttalet som har ställts in för det valda slutdatumet. Den resulterande kvantiteten föreslås sedan som avskrivningskvantitet för perioden.

### <a name="example-2"></a>Exempel 2

Följande faktor för förbrukningsavskrivning är inställd för 31 januari:

-   Procenttalet är 10 procent.
-   Enhetsavskrivningspriset som anges för anläggningstillgången är 1,5.
-   Den uppskattade kvantiteten för anläggningstillgången är 2 000.

Avskrivningsförslaget den 31 januari är som följer: Beräknad kvantitet × Procent × Enhetsavskrivning 2 000 × 0,10 × 1,5 = 300





[!INCLUDE[footer-include](../../includes/footer-banner.md)]