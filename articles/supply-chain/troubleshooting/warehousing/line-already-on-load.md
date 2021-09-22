---
title: En av raderna finns redan i en last
description: På den här sidan förklaras varför du får felmeddelandet "En av raderna finns redan i en last. Det gick inte att frisläppa till lagret", och hur problemet ska lösas.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0bdfaed005b9c58f7bd5f87dd6dffe648de47261
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477682"
---
# <a name="one-of-the-lines-is-already-on-a-load"></a>En av raderna finns redan i en last

## <a name="symptoms"></a>Symtom

När du arbetar med att skapa och leverera laster kan följande felmeddelande visas:

> En av raderna finns redan i en last. Det gick inte att frisläppa till lagret.

Om du manuellt skapar beläggningar eller om du ställer in processen så att lasten redan har skapats innan försäljningsorderrad har angetts, är antagandet att den efterföljande frisläppningen utförs manuellt och att flödet och värderingen från last kommer att användas.

I ett annat scenario försöker du göra en automatisk frisläppning till lagerstället, men påfyllnadsprocessen kunde inte skapa arbete. Därför skapas fortfarande en öppen leverans eller last. Den här öppna försändelsen eller lasten spärrar sedan de efterföljande försöken att automatiskt frisläppa ordern tills du antingen tar bort den öppna försändelsen eller lasten, eller manuellt ombearbetar påfyllning.

## <a name="resolution"></a>Lösning

Du kan frisläppa från sidan försäljningsorder, eller automatisk frisläppning kan göras från sidan Frisläpp försäljningsorder, endast om det inte finns någon last före frisläppandet till lagerstället. Lasten skapas automatiskt när påfyllnad har bearbetats.
