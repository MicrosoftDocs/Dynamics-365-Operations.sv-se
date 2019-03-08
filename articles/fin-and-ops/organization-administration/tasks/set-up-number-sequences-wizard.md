---
title: Ställa in nummerserier med hjälp av en guide
description: Nummerserier används för att generera läsliga, unika identifierare för huvuddataposter och transaktionsposter och som kräver dem.
author: sericks007
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1808ab9240ab291f9d203893a634bd390f16e2e7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "328250"
---
# <a name="set-up-number-sequences-by-using-a-wizard"></a>Ställa in nummerserier med hjälp av en guide

[!include [task guide banner](../../includes/task-guide-banner.md)]

Nummerserier används för att generera läsliga, unika identifierare för huvuddataposter och transaktionsposter och som kräver dem. En huvuddata eller en transaktionpost som kräver en identifierare, kallas för en referens. Innan du kan skapa nya poster för en referens, måste du ställa in en nummerserie och koppla den till referensen. I den här proceduren förklaras hur du ställer in alla nödvändiga nummerserier samtidigt, med hjälp av en guide. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till Organisationsadministration > Nummerserier > Nummerserier.
2. Klicka på Generera.
3. Klicka på Nästa.
    * På den här sidan kan du ändra identifieringskoden, det lägsta värdet och det högsta värdet. Dessutom kan du ange om nummerserien måste vara löpande.   
    * Välj inte alternativet Kontinuerlig om du måste förallokera nummer för nummerserien.     Om du vill lägga till ett omfångsegment till formatet för en nummerserie väljer du formatet i listan och klickar på Inkludera område i format.     Om du vill ta bort ett omfångsegment från formatet för en nummerserie väljer du formatet i listan och klickar på Ta bort område från format.     Om du vill utesluta en nummerserie i den automatiska genereringen väljer du nummerserien i listan och klickar på Ta bort.  
4. Klicka på Nästa.
5. Klicka på Avsluta.

