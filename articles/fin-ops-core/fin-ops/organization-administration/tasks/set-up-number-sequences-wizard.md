---
title: Ställa in nummerserier med hjälp av en guide
description: I den här artikeln förklaras hur du ställer in alla nödvändiga nummerserier samtidigt, med hjälp av en guide.
author: SunilGarg
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cae739aad1166eee1abebe3c0adc7939bca55bc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847075"
---
# <a name="set-up-number-sequences-using-a-wizard"></a>Ställa in nummerserier med hjälp av en guide

[!include [banner](../../includes/banner.md)]

Nummerserier används för att generera läsliga, unika identifierare för huvuddataposter och transaktionsposter och som kräver dem. En huvuddata eller en transaktionpost som kräver en identifierare, kallas för en referens. Innan du kan skapa nya poster för en referens, måste du ställa in en nummerserie och koppla den till referensen. I den här artikeln förklaras hur du ställer in alla nödvändiga nummerserier samtidigt, med hjälp av en guide. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till **Navigering > Moduler > Organisationsadministration > Nummerserier > Nummerserier**.
2. Välj **Generera**.
3. Välj **Nästa**.

   - På den här sidan kan du ändra identifieringskoden, det lägsta värdet och det högsta värdet. Dessutom kan du ange om nummerserien måste vara löpande.   
   - Välj inte alternativet **Kontinuerlig** om du måste förallokera nummer för nummerserien. Om du vill lägga till ett omfångsegment till formatet för en nummerserie väljer du formatet i listan och väljer **Inkludera område i format**. Om du vill ta bort ett omfångsegment från formatet för en nummerserie väljer du formatet i listan och väljer **Ta bort område från format**. Om du vill utesluta en nummerserie i den automatiska genereringen väljer du nummerserien i listan och väljer **Ta bort**.  

4. Välj **Nästa**.
5. Välj **Slutför**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
