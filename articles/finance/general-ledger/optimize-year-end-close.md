---
title: Optimering av årsbokslut
description: I den här artikeln beskrivs tillägget Optimera årsbokslutstjänst som är tillgängligt för årsslutsprocessen i redovisningen.
author: moaamer
ms.date: 11/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2022-11-28
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 41d0c2975341cf3d612cc36be348326e24e94f1b
ms.sourcegitcommit: 707957bb7bcd98faf2600eff1c98067901a0fb73
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750017"
---
# <a name="optimize-year-end-close"></a>Optimering av årsbokslut

Tillägget Optimera årsbokslutstjänst för Microsoft Dynamics 365 Finance gör det möjligt att köra årsbokslutet utanför instansen Programobjektserver (AOS) för Dynamics 365 Finance-resurser. Det använder mikrotjänstteknik. De fördelar som är kopplade till funktionerna för Optimering av årsbokslut omfattar förbättrad prestanda och minimal inverkan på SQL-databasen under årsbokslutet.

Om du vill använda funktionen Optimering av årsbokslut måste du utföra följande uppgifter:

1. Installera tillägget Optimering av årsbokslut från projektet i Microsoft Dynamics Lifecycle Service.
2. Aktivera funktionen **Optimering av årsbokslut** i Funktionshantering.

> [!NOTE]
> Du kan fortfarande använda den aktuella stängningsfunktionen för ekonomiresurser genom att inaktivera funktionen **Optimering av årsbokslut** i Funktionshantering.

## <a name="improved-performance"></a>Förbättrad prestanda

Funktionen **Optimering av årsbokslut** har utformats för att snabbare bearbeta årsbokslutet, särskilt för kunder som har stora datamängder. När årsbokslutet körs för en tjänst, avlastas den tunga bearbetningen från ekonomiresurser för att hjälpa till att minska bearbetningstiden och frigöra de resurser som kan påverka andra användares dagliga verksamhet.

Funktionen **Optimering av årsbokslut** kan hjälpa dig att uppnå följande mål:

- Förbättra prestandan för årsbokslutet genom att minska körtiden.
- Minska påverkan på andra processer under körningen av årsbokslut.
- Förbättra rapporteringen och justeringarna för årsbokslutsresultat, eftersom körningen av årsbokslut tar mindre tid.

## <a name="new-options-and-visibility"></a>Nya alternativ och synlighet

När funktionen **Optimering av årsbokslut** aktiveras läggs två nya kolumner **Resultat** och **Status** till på följande platser:

- På sidan **årsbokslut**
- I dialogrutan **Årsbokslutsresultat**
- I alternativen **Överföring av ekonomisk dimension i balansräkning** på sidan **Mall för årsbokslut**

I följande bild visas ett exempel på kolumnerna **Resultat** och **Status** på sidan **Årsbokslut**. Du kan välja länken **Visa resultat** i kolumnen **Resultat** för att öppna resultatet av årsbokslutet. Kolumnen **Status** visar aktuellt status för årsbokslutprocessen. De nya kolumnerna ger därför insyn i förloppet för stängningsprocessen vid årsbokslut.

[![Resultat och statuskolumner på sidan Årsbokslut.](./media/Yearendclose.jpg)](./media/Yearendclose.jpg)

När funktionen **Optimering av årsbokslut** är arkiverad blir snabbfliken **Ekonomiska dimensioner för balansräkning** tillgänglig på sidan **Mall för årsbokslut**. Du kan använda den här snabbfliken för att ange ekonomiska dimensioner för balansräkning i detalj vid årsbokslutet. Den här kapaciteten är parallell till den kapacitet som redan finns tillgänglig för vinst- och förlustkonton.

## <a name="architecture-and-data-flow"></a>Arkitektur och dataflöde

Om du vill använda funktionen **Optimering av årsbokslut** och kör årsbokslutet på en mikrotjänst måste du installera tillägget Optimering av årsbokslut från Lifecycle Services och aktivera funktionen **Optimering av årsbokslut** i Funktionshantering.

Som illustrationen visar verifierar stängningen av året att tillägget är installerat och att funktionen är aktiverad. Om båda förutsättningar uppfylls körs årsbokslutet för mikrotjänst.

[![Diagram för uppgiftsflöde.](./media/Lifecycle-services.jpg)](./media/Lifecycle-services.jpg)

## <a name="high-level-flow-for-year-end-close-processing"></a>Flöde på hög nivå för bearbetning av årsbokslutet

1. Årsbokslutprocess börjar i Ekonomi **Redovisning \> Periodstängning \> Årsbokslut**. Processen skapar batchjobb för stängning och uppgifter för de juridiska personer som stängs.
2. Årsbokslut avgör om årsboksluten ska köras på mikrotjänsten eller på den aktuella bokslutslogiken.

    - Om funktionen Optimering av årsbokslut är installerad i Lifecycle Services och funktionen **Optimering av årsbokslut** är aktiverad i funktionshantering, kommer årsbokslutet att köras på mikrotjänsten.

        1. Funktionen Optimering av årsbokslut skapar ett servicejobb vid årsslut för varje juridisk person som stängs och kör sedan logiken för årsbokslut. Mikrotjänsten genomför årsbokslut.
        2. Ekonomi lyssnar på årsbokslut på mikrotjänsten för att avgöra när mikrotjänsten har avslutats. Resultaten för årets slut uppdateras sedan på sidan **Årsbokslut** i Ekonomi.

    - I annat fall körs årsbokslutet på den aktuella bokslutslogiken.
