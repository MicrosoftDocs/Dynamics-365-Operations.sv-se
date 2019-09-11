---
title: Ställa in nummerserier med hjälp av en guide
description: I det här avsnittet förklaras hur du ställer in alla nödvändiga nummerserier samtidigt, med hjälp av en guide.
author: sericks007
manager: AnnBe
ms.date: 07/18/2019
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
ms.openlocfilehash: f97c4cd6cdb117ebdd67a155478bb6f8d1703541
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867401"
---
# <a name="set-up-number-sequences-using-a-wizard"></a>Ställa in nummerserier med hjälp av en guide

[!include [task guide banner](../../includes/task-guide-banner.md)]

Nummerserier används för att generera läsliga, unika identifierare för huvuddataposter och transaktionsposter och som kräver dem. En huvuddata eller en transaktionpost som kräver en identifierare, kallas för en referens. Innan du kan skapa nya poster för en referens, måste du ställa in en nummerserie och koppla den till referensen. I det här avsnittet förklaras hur du ställer in alla nödvändiga nummerserier samtidigt, med hjälp av en guide. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till **Navigering > Moduler > Organisationsadministration > Nummerserier > Nummerserier**.
2. Välj **Generera**.
3. Välj **Nästa**.

   - På den här sidan kan du ändra identifieringskoden, det lägsta värdet och det högsta värdet. Dessutom kan du ange om nummerserien måste vara löpande.   
   - Välj inte alternativet **Kontinuerlig** om du måste förallokera nummer för nummerserien. Om du vill lägga till ett omfångsegment till formatet för en nummerserie väljer du formatet i listan och väljer **Inkludera område i format**. Om du vill ta bort ett omfångsegment från formatet för en nummerserie väljer du formatet i listan och väljer **Ta bort område från format**. Om du vill utesluta en nummerserie i den automatiska genereringen väljer du nummerserien i listan och väljer **Ta bort**.  

4. Välj **Nästa**.
5. Välj **Slutför**.

